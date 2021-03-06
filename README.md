This repository contains a Docker Compose definition to set up the authorization server required for OAuth2. It relies on [Ory Hydra](https://github.com/ory/hydra).

# Requirements
* Docker

# Set up
1. Copy .env.example to .env
2. In .env:
	* Set `SECRETS_SYSTEM` and `OIDC_SUBJECT_IDENTIFIERS_PAIRWISE_SALT` to random and secure strings
	* If you use a test environment without HTTPS, set `SERVE_PARAMS=--dangerous-force-http`
	* If you use HTTP for last mile, set `TLS_ALLOW_TERMINATION_FROM` to the SSL server's subnet
	* Set `SC_FRONTEND` to the client's URL
	* Set Postgres credentials and update them inside `DSN`
3. If not running, start your external network
4. Set or disable the network in docker-compose.yml
5. Run `docker-compose up`