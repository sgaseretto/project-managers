# Redmine Project - Setup Files

This project contains a:

- `docker-compose` file to mount redmine
- `redmine-plugins` plugins to make redmine work
- `redmine-themes` themes for redmine

## Generar Certificados autofirmados
Generation of self-signed SSL certificates involves a simple 3 step procedure.
La generacion de certificados SSL consiste en 3 simples pasos

PASO 1: Crear la clave privada del server
```
openssl genrsa -out redmine.key 2048
```

PASO 2: Crear el certificate signing request (CSR)
```
openssl req -new -key redmine.key -out redmine.csr
```

PASO 3: Firmar el certificado usando la clave privada y el CSR
```
openssl x509 -req -days 365 -in redmine.csr -signkey redmine.key -out redmine.crt
```

## Disclaimer

Only the `docker-compose.yml` file was defined by me