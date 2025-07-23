# 🧘 ZenMind - Assistente Financeiro

> **Democratizando o planejamento financeiro através do WhatsApp**

Um assistente financeiro inteligente baseado em IA, acessível via WhatsApp, projetado para ajudar brasileiros a gerenciar suas finanças e construir melhores hábitos financeiros.

[![Status](https://img.shields.io/badge/Status-Em%20Desenvolvimento-yellow.svg)](https://github.com/joselpq/zenmind-financial-assistant)
[![WhatsApp](https://img.shields.io/badge/WhatsApp-+55%2011%2093904--1011-25D366?logo=whatsapp)](https://wa.me/5511939041011)
[![Site](https://img.shields.io/badge/Site-zenmind.com.br-blue)](https://zenmind.com.br)

## 🎯 Missão

Democratizar a educação e planejamento financeiro para brasileiros de baixa renda, fornecendo conselhos financeiros personalizados através do WhatsApp - a plataforma que eles já usam diariamente.

## ✨ Características Principais

### 🤖 **Arnaldo - Seu Consultor Financeiro IA**
- Assistente financeiro inteligente via WhatsApp
- Análise personalizada da situação financeira
- Conselhos adaptados à realidade brasileira
- Disponível 24/7 para suas dúvidas

### 💰 **Gestão Financeira Completa**
- **Controle de Orçamento**: Acompanhamento de receitas e despesas
- **Metas Financeiras**: Planejamento de sonhos e objetivos
- **Análise de Investimentos**: Recomendações personalizadas
- **Educação Financeira**: Conteúdo educativo contextualizado

### 🔒 **Segurança e Privacidade**
- Criptografia de ponta a ponta
- Conformidade com LGPD
- Dados armazenados com segurança
- Transparência total sobre uso de dados

## 🏗️ Arquitetura da Plataforma

```
┌─────────────────┐         ┌──────────────────┐         ┌─────────────────┐
│                 │         │                  │         │                 │
│  Site Landing   │────────▶│  Integração      │────────▶│   PostgreSQL    │
│   (Next.js)     │         │   WhatsApp       │         │    Database     │
│                 │         │  (Express.js)    │         │                 │
└─────────────────┘         └──────────────────┘         └─────────────────┘
     Vercel                      Railway                      Railway
       │                           │
       │                           │
       ▼                           ▼
┌─────────────────┐         ┌──────────────────┐
│                 │         │                  │
│    Usuários     │         │  Usuários        │
│   (Website)     │         │  WhatsApp        │
│                 │         │  (+55 11...)     │
└─────────────────┘         └──────────────────┘
```

## 🚀 Início Rápido

### Pré-requisitos

- Node.js 18+ e npm
- Conta WhatsApp Business
- Conta Meta Developer
- Conta Vercel (para deploy do site)
- Conta Railway (para deploy do serviço webhook)

### 📱 **Teste Agora Mesmo!**

**Mande uma mensagem para:** [+55 11 93904-1011](https://wa.me/5511939041011)

Experimente enviar:
- "Olá" - Para começar a conversar com o Arnaldo
- "Ajuda" - Para ver comandos disponíveis
- "Orçamento" - Para começar seu planejamento financeiro

### 💻 Desenvolvimento Local

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/joselpq/zenmind-financial-assistant.git
   cd zenmind-financial-assistant
   ```

2. **Configure o site:**
   ```bash
   cd zenmind-website
   npm install
   npm run dev
   # Acesse http://localhost:3000
   ```

3. **Configure o serviço WhatsApp:**
   ```bash
   cd ../whatsapp-integration
   npm install
   cp .env.example .env  # Configure suas credenciais
   npm run dev
   # Executa em http://localhost:3000
   ```

### ⚙️ Variáveis de Ambiente

Para `whatsapp-integration/`, crie um arquivo `.env` com:

```env
WHATSAPP_BUSINESS_ACCOUNT_ID=seu_business_account_id
META_APP_SECRET=seu_app_secret
TEST_PHONE_NUMBER_ID=seu_phone_number_id
TEST_ACCESS_TOKEN=seu_access_token
WEBHOOK_VERIFY_TOKEN=seu_verify_token
PORT=3000
```

## 📁 Estrutura do Projeto

```
zenmind-financial-assistant/
├── README.md                    # Documentação principal (inglês)
├── README.pt.md                 # Documentação em português
├── PROJECT_README.md            # Visão técnica do projeto
├── package.json                 # Configuração monorepo
│
├── zenmind-website/             # Site de marketing (Next.js)
│   ├── app/                     # App router do Next.js
│   ├── public/                  # Assets estáticos
│   └── package.json             # Dependências do site
│
├── whatsapp-integration/        # Serviço webhook WhatsApp
│   ├── src/                     # Código fonte
│   ├── database/                # Schemas SQL
│   ├── scripts/                 # Utilitários de setup
│   └── server.js                # Servidor principal
│
└── docs/                        # Documentação adicional
    ├── arnaldo-complete-vision.md
    ├── customer-strategy.md
    └── whatsapp-financial-assistant-mvp-plan.md
```

## 🛠️ Stack Tecnológico

- **Frontend:** Next.js 14, React, Tailwind CSS
- **Backend:** Express.js, Node.js
- **Database:** PostgreSQL
- **Deploy:** Vercel (site), Railway (API)
- **APIs:** WhatsApp Business API, Meta Graph API
- **IA:** OpenAI GPT-4, modelos customizados

## 📊 Status Atual do Projeto

### ✅ **Concluído**
- [x] Site landing page com CTAs para WhatsApp
- [x] Integração webhook WhatsApp funcional
- [x] Setup do banco de dados e persistência de mensagens
- [x] Fluxo básico de conversação
- [x] Deploy em produção
- [x] Resposta automática do Arnaldo

### 🚧 **Em Desenvolvimento**
- [ ] Assistente financeiro IA (Arnaldo)
- [ ] Fluxos avançados de conversação
- [ ] Funcionalidades de planejamento financeiro
- [ ] Análise de fotos de extratos bancários

### 📋 **Planejado**
- [ ] Rastreamento de gastos via WhatsApp
- [ ] Metas de economia e lembretes
- [ ] Conteúdo de educação financeira
- [ ] Integração com sistemas de pagamento brasileiros
- [ ] Open Finance/PIX integration
- [ ] Análise de crédito e score

## 💡 Funcionalidades Principais

### 🆓 **Plano Gratuito**
- ✅ Orçamento básico e controle de gastos
- ✅ Educação financeira geral
- ✅ Dicas simples de economia
- ✅ Definição básica de metas
- ✅ Comparação com pares (anônima)

### 💎 **Plano Premium (R$ 9,90/mês)**
- ✅ Conselhos personalizados de investimento
- ✅ Planejamento avançado de metas com projeções
- ✅ Dicas de otimização fiscal
- ✅ Suporte prioritário
- ✅ Gestão de conta familiar

## 🧪 Como Testar

### Site
```bash
cd zenmind-website
npm run build  # Verificar build
npm run lint   # Verificar linting
```

### Integração WhatsApp
```bash
cd whatsapp-integration
npm run test-send  # Enviar mensagem de teste
npm run test-info  # Obter info do telefone
```

### Endpoints de Saúde
- **Site:** [https://zenmind.com.br](https://zenmind.com.br)
- **API:** [https://whatsapp-integration-production-06bb.up.railway.app/health](https://whatsapp-integration-production-06bb.up.railway.app/health)

## 📋 Roadmap de Desenvolvimento

### **Fase 1: Construtor de Confiança** (Meses 1-2)
**Objetivo:** Resolver dor imediata, construir confiança, coletar dados

**Funcionalidades MVP:**
- Calculadora de orçamento emergencial
- Rastreamento simples de gastos via WhatsApp
- Alertas de gastos diários
- Desafios básicos de economia

### **Fase 2: Saúde Financeira** (Meses 3-4)
**Objetivo:** Entender quadro financeiro completo

**Funcionalidades:**
- Rastreamento e categorização de renda
- Lembretes e gestão de contas
- Insights e tendências de gastos
- Comparação com pares (anonimizada)

### **Fase 3: Conquista de Objetivos** (Meses 5-6)
**Objetivo:** Ajudar usuários a sonhar e planejar

**Funcionalidades:**
- Assistente de definição de metas
- Calculadora de planos de economia
- Acompanhamento de progresso
- Sistema de motivação

## 🔐 Segurança e Privacidade

- Todas as mensagens criptografadas em trânsito
- Banco PostgreSQL com acesso seguro
- Nenhum dado financeiro armazenado sem consentimento
- Práticas compatíveis com LGPD
- Verificação de assinatura de todos os webhooks WhatsApp
- Variáveis de ambiente para dados sensíveis
- HTTPS obrigatório para deployments de produção

## 🤝 Como Contribuir

1. Faça um fork do repositório
2. Crie uma branch para sua feature (`git checkout -b feature/funcionalidade-incrivel`)
3. Commit suas mudanças (`git commit -m 'Adiciona funcionalidade incrível'`)
4. Push para a branch (`git push origin feature/funcionalidade-incrivel`)
5. Abra um Pull Request

### Fluxo de Trabalho

1. Crie branches de feature a partir da `main`
2. Faça alterações no diretório do componente apropriado
3. Teste localmente antes de fazer commit
4. Crie pull requests para revisão
5. Merge para `main` após aprovação

## 📈 Métricas de Sucesso

### Métricas de Usuário
- Usuários Ativos Diários (DAU)
- Retenção 7 e 30 dias
- Mensagens por usuário por dia
- Taxa de conversão premium
- Taxa de indicação MGM

### Métricas de Impacto Financeiro
- Economia média por usuário
- Metas criadas vs. alcançadas
- Melhorias no score de crédito
- Receita de comissão por usuário

## 👥 Equipe

- **Produto:** Define requisitos e experiência do usuário
- **Engenharia:** Constrói e mantém a plataforma
- **Arnaldo:** Seu assistente financeiro IA 🤖

## 📞 Suporte

- **Problemas técnicos:** Verifique logs Railway/Vercel
- **Questões de produto:** Entre em contato com a equipe de produto
- **Suporte ao usuário:** Via WhatsApp

## 📚 Recursos e Links

- **Site Oficial:** [https://zenmind.com.br](https://zenmind.com.br)
- **WhatsApp:** [+55 11 93904-1011](https://wa.me/5511939041011)
- **Documentação WhatsApp Business API:** [Meta Developers](https://developers.facebook.com/docs/whatsapp/business-api)
- **Documentação Next.js:** [nextjs.org/docs](https://nextjs.org/docs)

## 📄 Licença

Este projeto é proprietário e confidencial. Todos os direitos reservados.

---

**Lembre-se da nossa missão:** Tornar o planejamento financeiro acessível a todos os brasileiros, uma mensagem de WhatsApp por vez. 🇧🇷 💚

**Construído com ❤️ pela equipe ZenMind**

---

## 🌟 Começar Agora

**Pronto para transformar sua vida financeira?**

1. 📱 Abra o WhatsApp
2. 💬 Mande uma mensagem para [+55 11 93904-1011](https://wa.me/5511939041011)
3. 🤖 Converse com o Arnaldo
4. 📈 Comece a construir seu futuro financeiro!

*"O melhor momento para começar foi há 10 anos. O segundo melhor momento é agora."*