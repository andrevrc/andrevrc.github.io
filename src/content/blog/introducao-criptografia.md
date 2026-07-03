---
title: "Introdução a criptografia aplicada"
description: "O que todo dev deveria saber sobre crypto."
date: 2026-01-08
category: "security"
readTime: "15 min"
image: "/images/blog/crypto.jpg"
---

Criptografia não é magica — é matemática. E todo desenvolvedor deveria entender pelo menos o básico para não cometer erros críticos.

## Hashing vs Encryption

Essa é a confusão mais comum.

**Hashing** é unidirecional. Não dá pra reverter. Use para senhas e integridade.

**Encryption** é bidirecional. Dá pra decriptar com a chave certa. Use para dados em trânsito e repouso.

## Práticas recomendadas

- Use bcrypt ou argon2 para senhas (nunca MD5 ou SHA1)
- Use HTTPS sempre (nunca HTTP plano)
- Use TLS 1.3 quando possível
- Nunca implemente seu próprio algoritmo criptográfico

## O que evitar

- Rolagens próprias de crypto
- Armazenar senhas em texto plano
- Usar ECB mode para encryption de blocos
- Ignorar certificados SSL inválidos

A segurança de um sistema é tão forte quanto seu elo mais fraco. Não deixe a criptografia ser esse elo.
