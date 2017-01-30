# V5: Network Communication Requirements

## Control Objective

The purpose of this control is to ensure the confidentiality and integrity of information exchanged between the mobile app and remote service endpoints. At the very least, a mobile app must set up a secure, encrypted channel for network communication using the TLS protocol with appropriate settings. For level two or higher, additional defense-in-depth measure such as SSL pinning are required.

## Security Verification Requirements

| # | Description | 1 | 2 |
| --- | --- | --- | --- |
| **5.1** | Data is encrypted on the network using TLS. The secure channel is used consistently throughout the app. | ✓ | ✓ |
| **5.2** | The TLS settings are in line with current best practices, as far as they are supported by the mobile operating system. | ✓ | ✓ |
| **5.3** | The app verifies the X.509 certificate of the remote endpoint when the secure channel is established. Only certificates signed by a valid CA are accepted. | ✓ | ✓ |
| **5.4** | The app either uses its own certificate store, or pins the endpoint certificate or public key, and subsequently does not establish connections with endpoints that offer a different certificate or key, even if signed by a trusted CA. |   | ✓ |
| **5.5** | The app doesn't rely on a single insecure communication channel (email or SMS) for critical operations, such as enrollments and account recovery. |  | ✓ |

## References

The OWASP Mobile Security Testing Guide provides detailed instructions for verifying the requirements listed in this section, as well as best practices by mobile operating system:

(...TODO... link this to v1.0 instead of master once tagged).

- Android - https://github.com/OWASP/owasp-mstg/blob/master/Document/Testcases/0x01d_OMTG-NET_Android.md
- iOS - https://github.com/OWASP/owasp-mstg/blob/master/Document/Testcases/0x01d_OMTG-NET_iOS.md

For more information, see also:

- OWASP Mobile Top 10:  M3 - Insecure Communication
- CWE: https://cwe.mitre.org/data/definitions/319.html
- CWE: https://cwe.mitre.org/data/definitions/295.html