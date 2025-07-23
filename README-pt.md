# ZenMind Assistente Financeiro

Uma plataforma abrangente de assistente financeiro baseada no WhatsApp que ajuda os usuários a gerenciar suas finanças através de IA conversacional.

## Visão Geral do Projeto

O ZenMind Assistente Financeiro é um monorepo contendo múltiplos componentes integrados que trabalham juntos para fornecer uma experiência perfeita de gestão financeira via WhatsApp.

### Componentes

- **`zenmind-website/`** - Site de marketing e página inicial em Next.js
- **`whatsapp-integration/`** - Serviço de webhook da API Business do WhatsApp para tratamento de mensagens

## Arquitetura

```
┌─────────────────┐     ┌─────────────────┐
│                 │     │                 │
│  Site ZenMind   │     │ Usuários        │
│   (Next.js)     │     │ WhatsApp        │
│                 │     │                 │
└────────┬────────┘     └────────┬────────┘
         │                       │
         │                       │ Mensagens
         │                       │
         │              ┌────────▼────────┐
         │              │                 │
         └──────────────┤ Serviço de      │
                        │ Integração      │
                        │ WhatsApp        │
                        │                 │
                        └─────────────────┘
```

## Início Rápido

### Pré-requisitos

- Node.js 18+ e npm
- Conta WhatsApp Business
- Conta Meta Developer
- Conta Vercel (para deploy do site)
- Conta Railway (para deploy do serviço webhook)

### Desenvolvimento Local

1. Clone o repositório:
```bash
git clone https://github.com/yourusername/zenmind-financial-assistant.git
cd zenmind-financial-assistant
```

2. Instale as dependências para todos os componentes:
```bash
# Instalar dependências do site
cd zenmind-website
npm install

# Instalar dependências da integração WhatsApp
cd ../whatsapp-integration
npm install
```

3. Configure as variáveis de ambiente:

Para `zenmind-website/`:
- Nenhuma variável de ambiente necessária para configuração básica

Para `whatsapp-integration/`:
Crie um arquivo `.env` com:
```env
WHATSAPP_BUSINESS_ACCOUNT_ID=seu_id_conta_business
META_APP_SECRET=seu_app_secret
TEST_PHONE_NUMBER_ID=seu_id_numero_telefone
TEST_ACCESS_TOKEN=seu_token_acesso
WEBHOOK_VERIFY_TOKEN=seu_token_verificacao
PORT=3000
```

4. Execute os serviços:

```bash
# Terminal 1 - Site
cd zenmind-website
npm run dev

# Terminal 2 - Integração WhatsApp
cd whatsapp-integration
npm start
```

## Deploy

### Deploy do Site (Vercel)

1. Instale a CLI do Vercel: `npm i -g vercel`
2. Do diretório `zenmind-website/`: `vercel`
3. Siga as instruções para fazer o deploy
4. Configure domínio personalizado no painel do Vercel

### Deploy da Integração WhatsApp (Railway)

1. Conecte seu repositório GitHub ao Railway
2. Configure variáveis de ambiente no painel do Railway
3. Faça o deploy a partir da branch main

## Funcionalidades

### Funcionalidades Atuais
- Página inicial profissional com informações do serviço
- Integração webhook do WhatsApp
- Recebimento e armazenamento de mensagens
- Rastreamento de janela de conversa (regra de 24 horas)
- Verificação de assinatura do webhook

### Funcionalidades Planejadas
- Conselhos financeiros com IA
- Rastreamento e categorização de despesas
- Gerenciamento de orçamento
- Definição de metas financeiras
- Recomendações de investimento
- Lembretes de contas
- Relatórios e insights financeiros

## Fluxo de Desenvolvimento

1. Crie branches de funcionalidade a partir da `main`
2. Faça alterações no diretório do componente apropriado
3. Teste localmente antes de fazer commit
4. Crie pull requests para revisão
5. Faça merge na `main` após aprovação

## Estrutura do Projeto

```
zenmind-financial-assistant/
├── README.md                    # Este arquivo
├── .gitignore                   # Gitignore raiz
├── zenmind-website/             # Site de marketing
│   ├── app/                     # Diretório app do Next.js
│   ├── public/                  # Assets estáticos
│   ├── package.json             # Dependências do site
│   └── README.md                # Docs específicos do site
├── whatsapp-integration/        # Serviço webhook WhatsApp
│   ├── index.js                 # Arquivo principal do servidor
│   ├── webhookHandler.js        # Lógica do webhook
│   ├── messageStore.js          # Armazenamento de mensagens
│   ├── package.json             # Dependências do serviço
│   └── README.md                # Docs específicos do serviço
└── docs/                        # Documentação adicional
    ├── customer-strategy.md     # Estratégia de aquisição de clientes
    └── whatsapp-financial-assistant-mvp-plan.md
```

## Testes

### Testes do Site
```bash
cd zenmind-website
npm run build  # Verificação de build
npm run lint   # Linting
```

### Testes da Integração WhatsApp
```bash
cd whatsapp-integration
npm run test-send  # Enviar mensagem de teste
npm run test-info  # Obter info do telefone
```

## Considerações de Segurança

- Todos os webhooks do WhatsApp são verificados usando a verificação de assinatura da Meta
- Variáveis de ambiente são usadas para dados sensíveis
- HTTPS é obrigatório para deploys em produção
- Siga as melhores práticas de segurança da API Business do WhatsApp da Meta

## Contribuindo

1. Faça fork do repositório
2. Crie uma branch de funcionalidade (`git checkout -b feature/funcionalidade-incrivel`)
3. Faça commit das suas alterações (`git commit -m 'Adicionar funcionalidade incrível'`)
4. Faça push para a branch (`git push origin feature/funcionalidade-incrivel`)
5. Abra um Pull Request

## Licença

Este projeto é proprietário e confidencial. Todos os direitos reservados.

## Suporte

Para perguntas ou suporte, entre em contato com a equipe de desenvolvimento.

## Links

- [Site](https://www.zenmind.com.br)
- [Documentação da API Business do WhatsApp](https://developers.facebook.com/docs/whatsapp/business-api)
- [Documentação do Next.js](https://nextjs.org/docs)

---

Construído com ❤️ pela equipe ZenMind