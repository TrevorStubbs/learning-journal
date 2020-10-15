# Day 42
## Web Security

## HTTPS
### Privatcy
- No unauthorized parties can eavesdrop
### Integrity
- The state of the data is not changed during data transfer
    - Man in the Middle attacks
### Identification
- Who is sending the data?
- Digital signatures
- Certificate Aurthoriteis

### Encryption
- turn code into a cypher 
- Keys
    - Symmetric Key
        - one key to both encrypt and decrypt
        - not easy to share
        - anyone with the key can decrypt
    - Asymmetric Key
        - 2 keys 1- public 1 - private
        - keys work together
        - only the holder of the private key can decrypt

### Protocls
- HTTPs 
    - hypertext transfer protocol
- SSL
    - Secure Socket Layer
- TLS
    - Transport Layer Security

- TLS is upgraded version of SSL

### Certificate Authorities
- Domain Val
- Organization Val
- Extended Val

### OWASP
- Open Web Application Security Project
    - Top Ten
        - SQL Injection
            - 
        - Broken Authentication / Account Managment
            - Password Hashing 
                - do not save passwords in plain text.
            - Users must have their own salt.
        - Sensitive Data Exposure
        - XML External Entities (XXE)
            - 
        - Broken Access Control
        - Security Misconfiguration
        - Cross-Site Scripting XSS
            - don't have a script tag on the front end
            - don't have a style tag
        - Insecure Deserialization
        - Using Components with Known Vulnerabilities
        - Insufficient Logging & Monitoring
        - Cross-origin resource sharing (CORS)
            - .Net has UseCors()
        - Unauthorized directory traversals