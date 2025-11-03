
Transport Layer Security. It is a cryptographic protocol that secures communication over the internet. The TLS handshake is the initial process that happens when a client connects to a sever before any sensitive data is exchanged.

# Purpose of the TLS handshake
- Authenticate the server and optionally the client.
- Agree on encryption algorithms (cipher suites).
- Generate session keys to encrypt/decrypt data during the session.




# TLS handshake
**TLS 1.2**
1. Client Hello:
	1. Browser sends a list of supported TLS versions, cipher suites and a random number.
2. Server Hello:
	1. Server chooses TLS version + cipher suite, sends its digital certificate (contains its public key), and another random number.
3. Certificate Verification:
	1. Client verifies the server's certificate using a trusted [[Certificate Authority]] ([[CA]]).
4. Key exchange:
	1. Client generates a pre-master secret, encrypts it with the server's public key and sends it to the server.
	2. Both sides then derive the same session key.
5. Finished Messages:
	1. Both client and server send encrypted "Finished" messages to confirm everything is good.

After all this, all data is encrypted with the shared session key.

**TLS 1.3**
- Combines many steps into one round trip.
- Uses stronger, forward-secure key exchange (via Diffie-Hellman).
- No support for outdated algorithms like RSA key exchange.
- No need to send the server's full certificate chain every time.