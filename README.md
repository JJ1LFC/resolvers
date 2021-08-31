# resolvers

Docker containers of major DNS full service resolvers' implementations.

Currently these implementations are supported.
- Unbound
- BIND9
- Knot Resolver

## Requirements
- Docker
- Docker compose

## Restrictions
- Currently runs only with IPv4.

## How to use
1. `docker-compose up -d` to build, create, and run containers.
2. listening interfaces is listed below.

***Host ports are opened to the outside of the host.***

example (Linux):
```
drill -D -o RD NS jj1lfc.dev. @172.53.0.2
```

example (OS X):
```
drill -D -o RD -p 18053 NS jj1lfc.dev. @127.0.0.1
```

Because of restrictions of Docker for Mac, you cannot connect to containers directly from your Mac.


| Implementation | Container IP addr.  | Host port  |
| -------------- | ------------------- | ------ --- |
| Unbound        | 172.53.0.2          | 18053      |
| BIND           | 172.53.0.3          | 18153      |
| Knot Resolver  | 172.53.0.4          | 18253      |

You can also run `drill` inside the containers.

