# Verifier API definition

Swagger that defines how the verifier in the credential issuer should behave.

## Generate NodeJS server

```
docker run \
  --rm -v ${PWD}:/local \
  swaggerapi/swagger-codegen-cli \
  generate -i /local/swagger.yaml -l nodejs-server -o /local/out
```

After running the previous command a new generated server should be created under the `out` directory.
