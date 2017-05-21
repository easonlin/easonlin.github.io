# Tor design documents
Tor is a anonymous communication service

https://svn.torproject.org/svn/projects/design-paper/tor-design.pdf

## Topic
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

## Design

### Message Transition
<img src="https://raw.githubusercontent.com/easonlin/easonlin.github.io/master/_posts/tor_message.png" 
alt="IMAGE ALT TEXT HERE" width="240" height="60" border="0" />

1. Client encrypt message and external service by red key as red encrypted data, 
encrypt red encrypted data and exit node router by green key as green encrypted data, 
and encrypt green encrypted data and second onion router by blue key as blue encrypted data.
1. Client send blue encrypted data to first onion router.
1. First onion router decrypt blue encrypted data to green encrypted data and send it to second onion router.
1. Second onion router decrypt green encrypted data to red encrypted data and send it to exit node.
1. Exit node router decrypt red encrypted data to message and send it to external service.

### Circuit Creation
<img src="https://raw.githubusercontent.com/easonlin/easonlin.github.io/master/_posts/2017-05-21-tor-design-document-read-experience-create-circuit.png" 
alt="IMAGE ALT TEXT HERE" width="240" height="60" border="0" />


### Onion Proxy
Privoxy is a non-caching web proxy with advanced filtering capabilities for enhancing privacy, modifying web page data and HTTP headers, controlling access, and removing ads and other obnoxious Internet junk.

