
# SSL

## Recommended ciphers

- EECDH+AESGCM
- EDH+AESGCM
- AES256+EECDH
- AES256+EDH

## Protocols

### SSLv1

Original SSL version, never released. 1995. Extremely vulnerable.

No sequence numbers means replay attacks are possible.
Only using RC4 allows you to predict changes to plaintext results.

### SSLv2

Based on SSLv1, fixed some security issues. Still vulnerable.

### SSLv3

Complete rewrite and redesign of the SSL protocol.

Vulnerable to _POODLE_ - see vuln section.

Officially deprecated in *June 2015*.

### TLSv1

Very similar to SSLv3 with a few fixes/changes.

Allows downgrading connection to SSLv3, thus enabling more attacks.

Fixes potential MAC vulns by replacing them with HMACs.

### TLSv1.1

Minor upgrade to *v1*.

Certificate format changed to PKCS1, allows existing sessions to be re-used if a connection is dropped.

### TLSv1.2

Changed to *TLS_RSA_WITH_AES_128_CBC_SHA* by default, which *was* more secure, at the time. (It has now been deprecated)

Lots of other little changes.

## Vulnerabilities

### POODLE

POODLE allows MITM decryption of all intercepted traffic using a _padding oracle attack_.

Basically by bruteforcing, you can decrypt connection data byte-by-byte. You need an average of _256_ HTTP requests per byte.

### BEAST

Allows decryption by manipulating and comparing 2 different encryption streams. No practical exploits have been released.

## Logjam

Is a downgrade attack that forces connections back to using (easily exploitable) 512 bit diffie-hellman groups.

## Heartbleed

Not a protocol vulnerability, but an implementation one. OpenSSL was vulnerable to leaking memory of the host system.
Allowed compromisation of private keys and other sensitive data. Required re-issue of majority of SSL certificates on the internet
