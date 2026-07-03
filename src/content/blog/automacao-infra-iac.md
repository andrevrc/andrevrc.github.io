---
title: "Automação de infraestrutura com IaC"
description: "Terraform, Pulumi e o que aprendi na prática."
date: 2026-03-05
category: "tech"
readTime: "10 min"
image: "/images/blog/infra.jpg"
---

Infraestrutura como código deixou de ser opcional. Se você não automatiza o provisionamento, está perdendo tempo e aumentando risco.

## Terraform vs Pulumi

Ambos resolvem o mesmo problema, mas com abordagens diferentes.

**Terraform** usa HCL, uma linguagem declarativa própria. É maduro, tem ecossistema enorme, mas a sintaxe pode ser verbosa.

**Pulumi** usa linguagens de programação reais (TypeScript, Python, Go). Isso permite loops, condicionais, e reuso de código de forma muito mais natural.

## O que aprendi

Na prática, a escolha entre Terraform e Pulumi importa menos que ter boas práticas:

- Modularize seus componentes
- Use state locking (sempre)
- Teste alterações em ambientes isolados
- Documente o que cada módulo faz
