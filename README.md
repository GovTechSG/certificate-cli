## Setup

```
yarn
```

## Issuing Certificates

This command process all certificates in the input directory and issue all of them in a single batch. It will then add the signature to the individual certificates. 

```
node index -i <PathToUnsignedCertificates> -o <PathToSignedCertificates>
```

Example:
```
node index -i ./certificates/raw-certificates/ -o ./certificates/processed-certificates/

============================== Issuing certificates ==============================

Batch Certificate Root:
458a80232eda8a816972be8ac731feb50727149aff6287d70142821ae160caf7

===================================================================================
```

## Verifying Signed Certificate

This command verifies that the certificate (and all it's evidence) is valid and is part of the certificate batch. However, it does not verify that the batch's merkle root is stored on the blockchain. User will need to verify that the certificate has indeed been issued by checking with the issuer's smart contract. 

```
node index -V <PathToCertificate>
```

Example:
```
node index -V ./certificates/processed-certificates/03zuc9yjvt1b.json

============================== Verifying certificate ==============================

Certificate's signature is valid!

Warning: Please verify this certificate on the blockchain with the issuer's certificate store.

===================================================================================
```

## TBD

- Generate sample certificates which conforms to schema v1.0
- Refactor allow this to be used as a npm module