# openBIS application stack for Kubernetes on Wodby

Deploy openBIS, the lab notebook and inventory manager for research data, on Kubernetes with Wodby.

This repository defines the Wodby stack manifest and default service composition for openBIS.

<!-- wodby:generated:start -->

## Stack contract

- [openBIS stack on Wodby](https://wodby.com/stacks/openbis)
- [Browse Wodby application stacks](https://wodby.com/stacks)
- [Wodby stack documentation](https://wodby.com/docs/2.0/stacks/)
- [Stack manifest reference](https://wodby.com/docs/2.0/stacks/template/)

## Service definitions

- [openBIS service](https://github.com/wodby/service-openbis)
- [openBIS Nginx service](https://github.com/wodby/service-openbis-nginx)
- [PostgreSQL service](https://github.com/wodby/service-postgres)
- [OpenSMTPD service](https://github.com/wodby/service-opensmtpd)

## What's included

| Component / service | Default configuration |
| --- | --- |
| openBIS<br>`openbis` | required; enabled by default; volumes: `data` 20 GB; links: `postgres` → `postgres`, `sendmail` → `opensmtpd` |
| Nginx<br>`nginx` | required; enabled by default; main; links: `backend` → `openbis` |
| PostgreSQL<br>`postgres` | required; enabled by default; volumes: `data` 10 GB; prepared transactions on |
| OpenSMTPD<br>`opensmtpd` | optional; disabled by default |

Enabled optional services are selected by default but can be excluded when an
app is created. Disabled optional services are available but not selected by
default. Required services cannot be excluded.

## Validate the stack manifest

```bash
wodby stack validate-manifest stack.yml --org <org-id>
```

<!-- wodby:generated:end -->
