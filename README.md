Civo module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with Civo.

## Caddy module name

```
dns.providers.civo
```

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
				"name": "civo",
				"api_token": "{env.CIVO_TOKEN}"
			}
		}
	}
}
```

or with the Caddyfile:

```
tls {
	dns civo {
		api_token {env.CIVO_TOKEN}
	}
}
```


## Authenticating

See [the associated README in the libdns package](https://github.com/libdns/civo) for important information about credentials.
