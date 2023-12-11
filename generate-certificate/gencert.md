# gencert.sh for LogicalDOC

Generate a self-signed x509v3 certificate for use with multiple URLs / IPs.

## Generate Certificates

### Default values

```bash
CRT_CN="client.com" CRT_SAN="DNS.1:www.client.com,DNS.2:admin.client.com,IP.1:192.168.1.10,IP.2:10.0.0.234" gencert.sh
```

### Custom values

You may change the `CRT_CN` and `CRT_SAN` values of the above command based on your needs.

Additionally you may use any of the following environment variables :
 - `CRT_C` : Country value
 - `CRT_L` : Locality value
 - `CRT_O` : Organization value
 - `CRT_OU` : Organizational Unit value
 - `CRT_CN` : Common Name value
 - `CRT_SAN` : SubjectAltName value

### Result

The command will generate two files:
 - pkcs#8 private key : `logicaldoc-x509.key`
 - x509v3 certificate : `logicaldoc-x509.cer`

You can confirm the certificate content by using the following standard `x509` command:

```bash
openssl x509 -in mattermost-x509.cer -noout -text
```
