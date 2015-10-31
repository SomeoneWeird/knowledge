
# Cryptography

## CBC vs ECB Mode

TLDR: *never never never ever* use ECB for encryption.

ECB encrypts each block separately, allowing you do to analysis on the output and potentially detect patterns.

CBC on the otherhand, encrypts each block one at a time, and chains them.
Each block (bar the first one) is XOR'd with the result of the last block.

ECB is also vulnerable to other attacks:
* IV reuse attacks (SSL BEAST vuln)
