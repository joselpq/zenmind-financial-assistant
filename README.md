# ZenMind - Assistente Financeiro 🇧🇷

Uma plataforma completa de assistente financeiro via WhatsApp que ajuda brasileiros a gerenciar suas finanças através de inteligência artificial conversacional.

## 🎯 Missão

Democratizar o planejamento financeiro para brasileiros de todas as classes sociais, fornecendo conselhos financeiros personalizados através do WhatsApp - a plataforma que já fazem parte do dia a dia.

## 📋 Visão Geral do Projeto

O ZenMind Financial Assistant é um monorepo contendo múltiplos componentes integrados que trabalham juntos para fornecer uma experiência perfeita de gestão financeira via WhatsApp.

### 🏗️ Arquitetura

```
┌─────────────────┐         ┌──────────────────┐         ┌─────────────────┐
│                 │         │                  │         │                 │
│  Site ZenMind   │────────▶│  Integração      │────────▶│   PostgreSQL    │
│   (Next.js)     │         │   WhatsApp       │         │    Database     │
│                 │         │   (Express.js)   │         │                 │
└─────────────────┘         └──────────────────┘         └─────────────────┘
     Vercel                      Railway                      Railway
       │                           │
       │                           │
       ▼                           ▼
┌─────────────────┐         ┌──────────────────┐
│                 │         │                  │
│    Usuários     │         │  WhatsApp Users  │
│   (Website)     │         │   (+55 11...)    │
│                 │         │                  │
└─────────────────┘         └──────────────────┘
```

### 📁 Componentes

- **`zenmind-website/`** - Site de marketing e landing page em Next.js
- **`whatsapp-integration/`** - Serviço de webhook da API do WhatsApp Business para processamento de mensagens

## 🚀 Início Rápido

### Pré-requisitos

- Node.js 18+ e npm
- Conta do WhatsApp Business
- Conta Meta Developer
- Conta Vercel (para deploy do website)
- Conta Railway (para deploy do serviço webhook)

### Desenvolvimento Local

1. **Clone o repositório:**
```bash
git clone https://github.com/joselpq/zenmind-financial-assistant.git
cd zenmind-financial-assistant
```

2. **Instale as dependências para todos os componentes:**
```bash
# Instalar dependências do website
cd zenmind-website
npm install

# Instalar dependências da integração WhatsApp
cd ../whatsapp-integration
npm install
```

3. **Configure as variáveis de ambiente:**

Para `zenmind-website/`:
- Não há variáveis de ambiente necessárias para configuração básica

Para `whatsapp-integration/`:
Crie um arquivo `.env` com:
```env
WHATSAPP_BUSINESS_ACCOUNT_ID=your_business_account_id
META_APP_SECRET=your_app_secret
TEST_PHONE_NUMBER_ID=your_phone_number_id
TEST_ACCESS_TOKEN=your_access_token
WEBHOOK_VERIFY_TOKEN=your_verify_token
PORT=3000
```

4. **Execute os serviços:**

```bash
# Terminal 1 - Website
cd zenmind-website
npm run dev

# Terminal 2 - Integração WhatsApp
cd whatsapp-integration
npm start
```

## 🌐 Deploy

### Deploy do Website (Vercel)

1. Instale a CLI do Vercel: `npm i -g vercel`
2. Do diretório `zenmind-website/`: `vercel`
3. Siga as instruções para fazer o deploy
4. Configure o domínio customizado no dashboard do Vercel

### Deploy da Integração WhatsApp (Railway)

1. Conecte seu repositório GitHub ao Railway
2. Configure as variáveis de ambiente no dashboard do Railway
3. Faça o deploy da branch main

## ✨ Funcionalidades

### Funcionalidades Atuais
- ✅ Landing page profissional com informações dos serviços
- ✅ Integração webhook WhatsApp
- ✅ Recebimento e armazenamento de mensagens
- ✅ Rastreamento da janela de conversação (regra de 24 horas)
- ✅ Verificação de assinatura do webhook
- ✅ Respostas automáticas básicas do Arnaldo

### Funcionalidades Planejadas

#### Fase 1: Construtor de Confiança (Meses 1-2)
- 🔄 Calculadora de orçamento de emergência
- 🔄 Rastreamento simples de gastos via WhatsApp
- 🔄 Alertas de gastos diários
- 🔄 Desafios básicos de economia

#### Fase 2: Saúde Financeira (Meses 3-4)
- 🔄 Rastreamento e categorização de renda
- 🔄 Lembretes e gestão de contas
- 🔄 Insights e tendências de gastos
- 🔄 Comparação com pares (anonimizada)
- 🔄 Primeiras funcionalidades premium

#### Fase 3: Conquista de Objetivos (Meses 5-6)
- 🔄 Assistente de definição de metas (casa, carro, educação)
- 🔄 Calculadora de plano de poupança
- 🔄 Acompanhamento de progresso
- 🔄 Sistema de motivação
- 🔄 Compartilhamento social de metas

#### Fase 4: Recomendações Inteligentes (Meses 7-9)
- 🔄 Recomendações de cartão de crédito
- 🔄 Comparações de contas bancárias
- 🔄 Análise empréstimo vs poupança
- 🔄 Orientação básica de investimentos
- 🔄 Integração com produtos parceiros

#### Fase 5: Consultor de Investimentos (Meses 10-12)
- 🔄 Avaliação de perfil de risco
- 🔄 Recomendações de portfólio de investimentos
- 🔄 Planejamento de aposentadoria
- 🔄 Otimização fiscal
- 🔄 Projeções financeiras avançadas

## 💰 Modelo de Negócio

### Planos Freemium

**Plano Grátis (Mercado de Massa)**
- ✅ Controle básico de orçamento e gastos
- ✅ Educação financeira geral
- ✅ Dicas simples de economia
- ✅ Definição básica de metas
- ✅ Funcionalidades da comunidade (comparar com pares)

**Plano Premium (R$9,90/mês)**
- ✅ Conselhos de investimento personalizados
- ✅ Planejamento avançado de metas com projeções
- ✅ Dicas de otimização fiscal
- ✅ Suporte prioritário
- ✅ Gestão de conta familiar

### Fluxos de Receita Adicionais
1. **Baseado em Comissão** (transparente para o usuário)
2. **Produtos de Dados** (anonimizados, com consentimento)
3. **Futuro: Produtos Próprios**

## 🛠️ Stack Tecnológico

- **Frontend:** Next.js 14, React, Tailwind CSS
- **Backend:** Express.js, Node.js
- **Banco de Dados:** PostgreSQL
- **Deploy:** Vercel (website), Railway (API)
- **APIs:** WhatsApp Business API, Meta Graph API

## 📊 Status Atual

### ✅ Concluído
- Landing page com CTAs do WhatsApp
- Integração webhook WhatsApp
- Configuração do banco de dados e persistência de mensagens
- Fluxo básico de conversação
- Deploy em produção

### 🚧 Em Progresso
- Assistente financeiro AI (Arnaldo)
- Fluxos avançados de conversação
- Funcionalidades de planejamento financeiro

## 📁 Estrutura do Projeto

```
zenmind-financial-assistant/
├── README.md                    # Este arquivo
├── PROJECT_README.md            # Documentação técnica adicional
├── GITHUB_SETUP.md             # Guia de configuração do GitHub
├── package.json                # Configuração do workspace raiz
├── package-lock.json           # Dependências travadas
├── zenmind-website/            # Site de marketing
│   ├── app/                    # Diretório app do Next.js
│   ├── public/                 # Assets estáticos
│   ├── package.json            # Dependências do website
│   └── README.md               # Documentação específica do website
├── whatsapp-integration/       # Serviço webhook WhatsApp
│   ├── src/                    # Código fonte
│   ├── database/               # Esquemas SQL
│   ├── scripts/                # Utilitários de configuração
│   ├── index.js                # Arquivo principal do servidor
│   ├── webhookHandler.js       # Lógica do webhook
│   ├── messageStore.js         # Armazenamento de mensagens
│   ├── package.json            # Dependências do serviço
│   └── README.md               # Documentação específica do serviço
└── docs/                       # Documentação adicional
    ├── customer-strategy.md    # Estratégia de aquisição de clientes
    ├── arnaldo-complete-vision.md # Visão completa do Arnaldo
    ├── arnaldo-financial-assistant-design.md
    ├── website-improvement-plan.md
    └── whatsapp-financial-assistant-mvp-plan.md
```

## 🧪 Testes

### Testes do Website
```bash
cd zenmind-website
npm run build  # Verificação de build
npm run lint   # Linting
```

### Testes da Integração WhatsApp
```bash
cd whatsapp-integration
npm run test-send  # Enviar mensagem de teste
npm run test-info  # Obter informações do telefone
```

### Teste da Integração
1. Envie uma mensagem WhatsApp para **+55 11 93904-1011**
2. Receba uma resposta automática do Arnaldo
3. Verifique o status de saúde em: https://whatsapp-integration-production-06bb.up.railway.app/health

## 🔐 Considerações de Segurança

- Todos os webhooks WhatsApp são verificados usando a verificação de assinatura da Meta
- Variáveis de ambiente são usadas para dados sensíveis
- HTTPS é obrigatório para deploys em produção
- Seguem as melhores práticas de segurança da API WhatsApp Business da Meta
- Todas as mensagens criptografadas em trânsito
- Banco de dados PostgreSQL com acesso seguro
- Nenhum dado financeiro armazenado sem consentimento
- Práticas compatíveis com LGPD

## 📈 Métricas de Sucesso

### Métricas do Usuário
- Usuários Ativos Diários (DAU)
- Retenção de 7 e 30 dias
- Mensagens por usuário por dia
- Taxa de conversão premium
- Taxa de indicação MGM

### Métricas de Impacto Financeiro
- Economia média por usuário
- Metas criadas vs alcançadas
- Melhorias no score de crédito
- Receita de comissão por usuário

## 🤝 Contribuindo

Este é um repositório privado. Membros da equipe devem:

1. Fazer fork do repositório
2. Criar uma branch de funcionalidade (`git checkout -b feature/funcionalidade-incrivel`)
3. Commit suas mudanças (`git commit -m 'Adicionar funcionalidade incrível'`)
4. Push para a branch (`git push origin feature/funcionalidade-incrivel`)
5. Abrir um Pull Request

## 🎯 Fluxo de Trabalho de Desenvolvimento

1. Criar branches de funcionalidade a partir da `main`
2. Fazer mudanças no diretório do componente apropriado
3. Testar localmente antes de fazer commit
4. Criar pull requests para revisão
5. Merge na `main` após aprovação

## 📞 Suporte

- **Questões técnicas:** Verificar logs do Railway/Vercel
- **Questões sobre o produto:** Entrar em contato com a equipe de produto
- **Suporte ao usuário:** Via WhatsApp

Para perguntas ou suporte, entre em contato com a equipe de desenvolvimento.

## 📄 Licença

Este projeto é proprietário e confidencial. Todos os direitos reservados.

## 🔗 Links Úteis

- [Website Oficial](https://www.zenmind.com.br)
- [Documentação da API WhatsApp Business](https://developers.facebook.com/docs/whatsapp/business-api)
- [Documentação do Next.js](https://nextjs.org/docs)

---

**Lembre-se da nossa missão:** Tornar o planejamento financeiro acessível a todos os brasileiros, uma mensagem WhatsApp por vez. 🇧🇷 💚

Construído com ❤️ pela equipe ZenMind