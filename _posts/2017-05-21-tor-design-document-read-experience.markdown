# Tor design documents
Tor is a anonymous communication service

https://svn.torproject.org/svn/projects/design-paper/tor-design.pdf

## Keywords
1. Forward Secrecy
    1. Onion Proxy
    1. Onion Router
    1. Directory service
    1. Configurable exit policies
1. Location-hidden services
    1. Hidden services
    1. Rendezvous point
1. Traffic Quality
    1. Congesion control
    1. Integrity checking

## Goals
Frustrate attackers from linking communication partners.

### Considerations
1. Deployability
1. Usability
1. Flexibility
1. Simple design

### Non-Goals
1. Not peer-to-peer
1. Not secure against end-to-end attacks
1. No protocol normalization
1. Not steganographic

## Design for hidden clients

### Message Transition
<img src="https://raw.githubusercontent.com/easonlin/easonlin.github.io/master/_posts/tor_message.png" 
alt="IMAGE ALT TEXT HERE" width="240" height="60" border="0" />

1. Client encrypt message with external service by red key as red encrypted data, 
encrypt red encrypted data with exit node router by green key as green encrypted data, 
and encrypt green encrypted data with second onion router by blue key as blue encrypted data.
1. Client send blue encrypted data to first onion router.
1. First onion router decrypt blue encrypted data to green encrypted data and send it to second onion router.
1. Second onion router decrypt green encrypted data to red encrypted data and send it to exit node.
1. Exit node router decrypt red encrypted data to message and send it to external service.

### Circuit Creation
<img src="https://raw.githubusercontent.com/easonlin/easonlin.github.io/master/_posts/2017-05-21-tor-design-document-read-experience-create-circuit.png" 
alt="IMAGE ALT TEXT HERE" width="480" height="240" border="0" />

Client send create and extend message by "Message Transition" to specific onion router.

1. Client request key from first onion router.
1. Client decrypt key response message by RSA to blue key.
1. Client encrypt key request message with second onion router by blue key as blue encrypted data, 
and send it to first onion router.
1. First onion router decrypt blue encrypted data and request key from second onion router.
1. First onion router encrypt key response message as blue encrypted data and send it to client.
1. Client decrypt blue encrypted data to key response message and decrypt it by RSA to green key.
1. Loop

### Circuit Destruction
Client send destroy or truncat message by "Message Transition" to the specific onion router.

### DNS query
1. For http, Tor is like a proxy, 
client could identify external service by hostname and port (www.exmple.com:80)
exit node do the DNS resolving.
1. Tor also provided remote hostname lookup on onion router. 
Client could request onion router to query DNS.

### Directory Servers
- A small group of redundant, well-known onion routers as directory servers.
- Onion routers periodically publish signed statements of their state to each directory server.
- Client fetch current network state and router lists from directory servers.

## Design for hidden services

### Considerations
1. Access-control
1. Robustness
1. Smear-resistance
1. Application-transparency

### Circuit Creation
1. Server choose some onion routers as its introduction points, 
create circuit to them and advertise them.
1. Client choose one onion router as its redezvous point and create circuit to it.
1. Client choose one introduction point, 
create circuit to it and inform server of the redezvous point via this circuit.
1. Server create circuit to the redezvous point.
1. Client/Server transmit data via the redezvous point circuit.

## Integration with user applications

### Onion Proxy
Privoxy is a non-caching web proxy with advanced filtering capabilities for enhancing privacy, modifying web page data and HTTP headers, controlling access, and removing ads and other obnoxious Internet junk.

