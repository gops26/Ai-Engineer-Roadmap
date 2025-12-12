**SSL (Secure Sockets Layer)** is a cryptographic protocol that was designed to provide secure communication over a computer network. Although the term “SSL” is still widely used, the actual protocol that is in use today is **TLS (Transport Layer Security)**, which is the successor to SSL.

Below is a concise overview of SSL/TLS:

| Aspect | What It Does | Why It Matters |
|--------|--------------|----------------|
| **Encryption** | Encrypts data so that eavesdroppers cannot read it. | Protects sensitive information (e.g., passwords, credit card numbers). |
| **Authentication** | Uses certificates to prove that the server is who it claims to be. | Prevents “man‑in‑the‑middle” attacks. |
| **Integrity** | Ensures that data has not been altered in transit. | Maintains trust in the data transmitted. |
| **Handshake** | A series of messages that establish encryption keys and agreement on cipher suites. | Sets up a secure session between client and server. |
| **TLS 1.3** (current standard) | Provides faster handshakes and better security than older TLS/SSL versions. | Modern browsers and servers use TLS 1.3 whenever possible. |   

### How SSL/TLS Works (High‑Level)

1. **Client Hello** – The browser (client) sends a message listing supported TLS versions, cipher suites, and a random number.
2. **Server Hello & Certificate** – The server responds with its chosen TLS version, cipher suite, random number, and its digital certificate (issued by a Certificate Authority).
3. **Key Exchange** – Both parties compute a **pre‑master secret**, which is used to generate the session keys for encrypting data.
   - Modern TLS uses Diffie‑Hellman or Elliptic‑Curve Diffie‑Hellman, making the key exchange *forward‑secrecy*.
4. **Certificate Verification** – The client verifies the server’s certificate against trusted root CAs. If valid, the handshake continues.
5. **Session Established** – Both sides have shared secrets and exchange a Finished message that confirms integrity.
   The connection is now fully encrypted.

### Where SSL/TLS Is Used

* **HTTPS** – Web pages and APIs over HTTP.
* **IMAP/POP3/SMTP** – Secure email protocols.
* **FTP, SSH, VPNs, VoIP** – Many other internet protocols also rely on it.
* **Software updates, cloud storage, IoT devices** all use TLS for secure communication.

### Common Terms

| Term | Meaning |
|------|---------|
| **Cipher Suite** | Combination of encryption, authentication, and hashing algorithms used during a TLS session. |
| **Certificate Authority (CA)** | Trusted organization that issues digital certificates. |
| **PKI (Public Key Infrastructure)** | System of CAs, certificates, and revocation lists that enable secure identity verification. |
| **ALPN (Application‑Layer Protocol Negotiation)** | Allows the application (e.g., HTTP/2) to be negotiated during the TLS handshake. |
| **OCSP / CRL** | Methods for checking whether a certificate has been revoked. |       

### Historical Note

| Version | Date | Key Points |
|---------|------|------------|
| SSL 1.0 | 1995 (internal) | Never released publicly. |
| SSL 2.0 | 1995 | Suffered from many security flaws; withdrawn. |
| SSL 3.0 | 1996 | First widely deployed version. Still in use on legacy systems (vulnerable to POODLE). |
| TLS 1.0 | 1999 | Renamed from SSL 3.0, addressed many SSL bugs. |
| TLS 1.1 | 2006 | Minor security improvements. |
| TLS 1.2 | 2008 | Introduced AEAD ciphers like GCM. |
| TLS 1.3 | 2018 | Major rewrite: 1‑round‑trip handshake, only AEAD ciphers, no RSA key exchange. |

> **TL;DR:** SSL was the original protocol for secure internet communication, now replaced by TLS. It encrypts data, authenticates servers, and ensures integrity, making it essential for everything from HTTPS to email and beyond
