# Oficina — Infraestrutura Kubernetes

Infraestrutura AWS e componentes de plataforma Kubernetes do sistema da oficina.

## Responsabilidades planejadas

- redes, subnets e recursos compartilhados necessários ao cluster;
- Amazon EKS e seus node groups;
- Amazon ECR;
- Kong API Gateway;
- observabilidade da plataforma;
- ambientes isolados de homologação e produção.

## Ambientes e branches

| Branch | Ambiente | Diretório Terraform |
|---|---|---|
| `staging` | Homologação | `terraform/environments/staging` |
| `main` | Produção | `terraform/environments/production` |

Cada ambiente deverá possuir recursos e Terraform state independentes. A branch
`main` não deverá receber commits diretos; a promoção ocorrerá por Pull Request.

## Limites deste repositório

Não pertencem a este repositório:

- código e manifests específicos da API;
- Amazon RDS e modelagem do banco;
- código da função serverless de autenticação.

## Estrutura inicial

```text
.
├── .github/workflows/
├── docs/
├── platform/
│   ├── kong/
│   └── observability/
└── terraform/
    ├── environments/
    │   ├── staging/
    │   └── production/
    └── modules/
```

## Status

Estrutura inicial. Terraform, CI/CD e recursos cloud ainda não foram implementados.
