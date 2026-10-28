# Metrobi Receiver Platform
### Product Role Challenge Submission

Protótipo funcional criado para explorar a evolução da Receiver Platform da Metrobi.

## Demo

🔗 https://wesleyzilva.github.io/transport/

---

# Executive Summary

Metrobi opera um marketplace logístico B2B2C conectando:

- Shippers (empresas)
- Drivers (motoristas independentes)
- Receivers (destinatários finais)

Hoje o recebedor possui visibilidade limitada sobre o processo de entrega.

Este projeto explora uma Receiver Platform mobile-first baseada em Magic Link que reduz ansiedade, diminui solicitações de suporte e melhora a comunicação durante o ciclo de entrega.

---

# The Problem

Atualmente o recebedor:

- Não acompanha a entrega em tempo real
- Não sabe exatamente quando o motorista chegará
- Não possui um canal seguro de comunicação
- Tem dificuldade para informar códigos de acesso
- Não possui autonomia para acompanhar ocorrências

Impactos:

- aumento de chamadas WISMO ("Where is my order?")
- entregas perdidas
- retrabalho operacional
- pressão sobre o suporte do shipper

---

# Product Vision

Criar uma experiência de acompanhamento de entrega:

✅ sem login

✅ sem instalação de aplicativo

✅ mobile-first

✅ orientada por eventos em tempo real

✅ integrada ao modelo B2B2C da Metrobi

---

# Core Design Principles

## 1. Zero Friction

Recebedores não devem:

- criar conta
- lembrar senha
- baixar aplicativo

A entrada acontece via:

```text
SMS
 ↓
Magic Link
 ↓
Tracking Dashboard
```

---

## 2. Shipper First

O cliente da Metrobi não é o recebedor.

O cliente é o Shipper.

Por isso:

✅ adicionar código do portão → imediato

✅ adicionar observação → imediato

⚠️ alterar endereço → aprovação

⚠️ alterar horário → aprovação

---

## 3. Operational Reality

As funcionalidades precisam funcionar no mundo real.

O motorista:

- dirige
- possui múltiplas entregas
- segue rota otimizada

Por isso o produto evita dar controle operacional direto ao recebedor.

---

# Ecosystem

## Shipper

Responsável por:

- criar entregas
- definir preço
- definir horários
- selecionar motoristas
- aprovar exceções

---

## Driver

Responsável por:

- aceitar a rota
- coletar mercadorias
- executar o transporte
- registrar POD

---

## Receiver

Responsável por:

- acompanhar a entrega
- receber notificações
- enviar instruções
- avaliar a experiência

---

# User Journey

## Scheduled

```text
Delivery Created
 ↓
SMS Sent
 ↓
Receiver Opens Link
```

---

## In Transit

```text
Live Tracking
 ↓
ETA
 ↓
Map View
 ↓
Driver Information
```

---

## Delivery Management

```text
Update Notes
 ↓
Gate Code
 ↓
Drop-off Instructions
```

---

## Delivery Completed

```text
Proof of Delivery
 ↓
Photo
 ↓
Timestamp
 ↓
Driver Rating
```

---

# Prototype Features

## Receiver Platform

### Tracking Dashboard

- ETA
- live map
- driver card
- delivery timeline

### Driver Contact

- masked phone calls
- predefined quick replies
- direct messaging

### Delivery Updates

- gate access code
- delivery instructions

### Change Requests

- new address request
- delivery window request
- shipper approval workflow

### Proof of Delivery

- delivery photo
- timestamp
- driver notes

### Driver Rating

- 1-5 star rating
- incident reporting
- conditional feedback flow

---

# Product Decisions

## Why Magic Link?

Receivers are low-frequency users.

Requiring:

- signup
- password creation
- app installation

would increase abandonment dramatically.

---

## Why Approval Based Changes?

Changing:

- destination
- delivery window

impacts:

- route optimization
- marketplace pricing
- driver compensation

Therefore these actions become requests instead of direct actions.

---

# Business Impact

Expected outcomes:

| Metric | Goal |
|----------|----------|
| WISMO Reduction | ↓ |
| Support Contacts | ↓ |
| First Attempt Delivery Rate | ↑ |
| Receiver Confidence | ↑ |
| Driver Feedback Volume | ↑ |

---

# Product Hypotheses

## H1

If receivers can see ETA and driver location in real time,
then support requests will decrease.

---

## H2

If receivers can send access information proactively,
then successful first-attempt deliveries will increase.

---

## H3

If POD is immediately visible after delivery,
then trust and rating participation will increase.

---

# Edge Cases Considered

### GPS Offline

Display:

```text
Last known location
Updated 5 minutes ago
```

---

### Driver Cancellation

Display:

```text
Looking for a replacement driver
```

---

### Expired Link

Display:

```text
Tracking session expired
```

after 24h.

---

# Future Roadmap

## V1

Current scope

- Tracking
- ETA
- POD
- Ratings

---

## V2

- Tips
- Push notifications
- Delivery history

---

## V3

- White-label experience
- Branded tracking pages
- Premium dynamic route changes

---

# Technical Stack

Frontend:

- HTML
- CSS
- JavaScript

Future Architecture:

- Angular
- BFF Pattern
- Event Driven Services
- Marketplace APIs
- Tracking APIs
- Communication APIs
- Billing APIs

---

# Author

Wesley Silva

Product Role Challenge
Metrobi Receiver Platform