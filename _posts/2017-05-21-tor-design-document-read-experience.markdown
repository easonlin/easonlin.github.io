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

### Onion Proxy
Privoxy is a non-caching web proxy with advanced filtering capabilities for enhancing privacy, modifying web page data and HTTP headers, controlling access, and removing ads and other obnoxious Internet junk.

