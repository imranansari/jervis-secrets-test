# Jervis Secrets Test

Automatically loading secrets from a repository into Jenkins.  Based on
[repository-secrets][rs].

Keys were generated with:

    openssl genrsa -out ./id_rsa 1024
    openssl rsa -in ./id_rsa -pubout -outform pem -out ./id_rsa.pub

Create credentials in a Jenkins folder and give it the credentials ID
`jervis-secrets-test`.

Secret generated with:

    echo -n 'plaintext' | openssl rsautl -encrypt -inkey ./id_rsa.pub -pubin | base64 -w0

Support added in [jervis#64][jervis#64].

[jervis#64]: https://github.com/samrocketman/jervis/issues/64
[rs]: https://github.com/samrocketman/repository-secrets/blob/master/docs/proof_of_concept.md
