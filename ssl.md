
# SSL

## Protocols

### SSLv1

Original SSL version, never released. 1995. Extremely vulnerable.

No sequence numbers means replay attacks are possible.
Only using RC4 allows you to predict changes to plaintext results.

### SSLv2

Based on SSLv1, fixed some security issues. Still vulnerable.

### SSLv3

Complete rewrite and redesign of the SSL protocol.

Vulnerable to _POODLE_ - allows MITM decryption of all intercepted traffic using a _padding oracle attack_.

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
