# x509-parser
Simple Python (only supports Python3) utility to help parse X509 certificates. This utility will allow the parsing of x509 certificates via:
1. Directly from a web server.
2. From a text file containing the X509 certificate
3. From the command line.

Usage of the tool is as follows:

#### For parsing a X509 certificate from a web server:

To use the default port of 443:
`python x509_parser.py -i <host>` or `python x509_parser.py --host <host>`

To use a custom port:
`python x509_parser.py -i <host> -p <port>` or `python x509_parser.py --host <host> --port <port>`

#### For parsing a x509 certificate from a text file:

`python x509_parser.py -f <filename>` or `python x509_parser.py -file <filename>`

#### For parsing a x509 certificate from the command line:

`python x509_parser.py -d` or `python x509_parser.py --dump`

#### Example

~~~~
swright@swright-XPS-13-9360:~/workspace/x509-parser$ python x509_parser.py -i www.google.com
{
    "subject": {
        "C": "US",
        "ST": "California",
        "L": "Mountain View",
        "O": "Google LLC",
        "CN": "www.google.com"
    },
    "issuer": {
        "C": "US",
        "O": "Google Trust Services",
        "CN": "Google Internet Authority G3"
    },
    "has-expired": false,
    "not-after": "2019-07-30 10:55:00",
    "not-before": "2019-05-07 11:32:17",
    "extensions": {
        "extendedKeyUsage": "TLS Web Server Authentication",
        "keyUsage": "Digital Signature",
        "subjectAltName": "DNS:www.google.com",
        "authorityInfoAccess": "CA Issuers - URI:http://pki.goog/gsr2/GTSGIAG3.crt\nOCSP - URI:http://ocsp.pki.goog/GTSGIAG3\n",
        "subjectKeyIdentifier": "82:4A:FB:FA:18:7D:37:BA:5A:41:AC:A2:BF:77:34:47:50:D7:55:FE",
        "basicConstraints": "CA:FALSE",
        "authorityKeyIdentifier": "keyid:77:C2:B8:50:9A:67:76:76:B1:2D:C2:86:D0:83:A0:7E:A6:7E:BA:4B\n",
        "certificatePolicies": "Policy: 1.3.6.1.4.1.11129.2.5.3\nPolicy: 2.23.140.1.2.2\n",
        "crlDistributionPoints": "\nFull Name:\n  URI:http://crl.pki.goog/GTSGIAG3.crl\n"
    },
    "serial-number": 20737766121738423495711577062012920074,
    "serial-number(hex)": "0xf99f2cf47e903a4abc638ae2a54a10a",
    "signature-algorithm": "sha256WithRSAEncryption",
    "version": 2,
    "pulic-key-length": 256
}
~~~~
