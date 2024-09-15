# Installation

Prerequisites,

```bash
sudo apt install apache2-utils
```

```
git clone https://github.com/atareao/self-hosted.git
cd self-hosted/traefik
```

Change `FQDN` for your server in `.env`,

```bash
cp sample.env .env
```

Change permissions for `acme.json`,

```bash
chmod 600 ./acme.json
```

Generate credentials for your user,

```bash
htpasswd -nb usuario contrasenia >> users.txt
```

Change the email for letsencrypt,

```bash
sed -i "s/tu@correo.es/<tu-correo>/g" traefik.yml
```

```bash
docker network create proxy
docker-compose up -d
docker-compose logs -f
```