# Verifier API definition

Swagger that defines how the verifier in the credential issuer should behave.

This is an API definition, it's done with a sample request for developing purposes, each instance of a Credential Issuer should implement their own logic to decide who should issue the credential.

The api is very simple, a complete verifier should do the following:
- If the data is valid, we should return `{"ok": true, "error": ""}`
- If not, `{"ok": false, "error": "Not valid user"}`

## Build and start NodeJS server with Docker

Build the Docker image:

```
docker build -t verifier-api .
```

Start the generated server:

```
docker run --rm -ti -p 8080:8080 verifier-api
```

## Checking that it works

```
curl -X POST \
  http://localhost:8080/verify \
  -H 'Content-Type: application/json' \
  -d '{
	"dni": "12345678A"
}'
```

The response should be:

```
{
  "ok": true,
  "error": ""
}
```
