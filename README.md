# 💳 Gateway de Pagamento - Imersão Full Cycle

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![License](https://img.shields.io/badge/license-MIT-blue.svg)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)
![Made with Go](https://img.shields.io/badge/backend-Go-blue?logo=go)
![Made with Next.js](https://img.shields.io/badge/frontend-Next.js-black?logo=next.js)
![Kafka](https://img.shields.io/badge/message%20broker-Kafka-231F20?logo=apachekafka)

---

## 📌 Sobre o Projeto

Este projeto foi desenvolvido durante a **Imersão Full Stack & Full Cycle**, com o objetivo de construir um **Gateway de Pagamento** completo utilizando **arquitetura de microsserviços**.

A proposta é demonstrar a construção de um sistema distribuído moderno, com:

- Separação clara de responsabilidades
- Comunicação assíncrona entre serviços
- Análise de fraudes em tempo real
- Escalabilidade e desempenho

---

## 🧱 Arquitetura

> 🔗 **Visualize a arquitetura completa aqui**  
> *(adicione um link para imagem ou diagrama)*

O sistema é dividido em múltiplos serviços independentes, que se comunicam entre si de forma assíncrona através do **Apache Kafka**.

---

## 🧩 Componentes do Sistema

### 🖥️ Frontend (Next.js)
- Interface do usuário para gerenciamento de contas e processamento de pagamentos
- Desenvolvido com **Next.js**, garantindo performance e uma boa experiência de uso

### 🔐 Gateway (Go)
- Sistema principal de **processamento de pagamentos**
- Gerencia contas, transações e coordena o fluxo de pagamentos
- Publica eventos de transações no Kafka para análise de fraude

### 🔁 Apache Kafka
- Responsável pela **comunicação assíncrona** entre o Gateway e o serviço de Antifraude
- Garante confiabilidade na troca de mensagens
- Utiliza tópicos específicos para transações e resultados de análise

### 🛡️ Antifraude (Nest.js)
- Consome eventos de transação enviados pelo Kafka
- Realiza **análise de fraudes em tempo real**
- Publica os resultados da análise de volta no Kafka

---

## 🔄 Fluxo de Comunicação

1. O **Frontend** realiza requisições REST para o **Gateway**
2. O **Gateway** processa as requisições e publica eventos de transação no **Kafka**
3. O serviço de **Antifraude** consome os eventos e realiza a análise
4. Os resultados da análise são publicados novamente no **Kafka**
5. O **Gateway** consome os resultados e finaliza o processamento da transação

---

## 🚀 Tecnologias Utilizadas

- **Next.js** (Frontend)
- **Go** (API Gateway)
- **Nest.js** (Antifraude)
- **Apache Kafka** (Mensageria)
- **Docker & Docker Compose** (Ambiente de desenvolvimento)

---

## 📂 Como executar o projeto

> Em breve: instruções de execução local com Docker Compose ou instalação manual de cada serviço.

---

## 📣 Créditos

Projeto desenvolvido durante a **Imersão Full Cycle**, promovida por [Full Cycle](https://fullcycle.com.br).

---

