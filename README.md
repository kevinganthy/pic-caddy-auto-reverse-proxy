# POC caddy auto reverse proxy

Basé sur le projet [caddy-docker-proxy](https://github.com/lucaslorentz/caddy-docker-proxy).

## Utilisation

Créer un réseau docker pour les conteneurs à exposer.

```bash
docker network create caddy
```

Lancer le compose principal contenant le reverse proxy.

```bash
docker-compose up -d
```

Url accessible à partir de ce point :

- <http://localhost>

Lancer le compose secondaire contenant les services à exposer à la volée.

```bash
docker-compose -f compose.sec.yml up -d
```

Url accessible à partir de ce point :

- <http://localhost>
- <http://static_response.localhost>
- <http://front.localhost>
- <http://pocket.localhost>
  - <http://pocket.localhost/_/>
  - <http://pocket.localhost/api/helloworld>
- <http://static_files.localhost>
