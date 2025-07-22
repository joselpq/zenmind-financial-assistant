# Arnaldo - AI Financial Assistant Design

## 🎯 Core Problems to Solve (Start Narrow)

### Phase 1: Emergency Financial Guidance (MVP)
**Problem:** "I ran out of money before the end of the month"
- **Solution:** Immediate expense analysis and survival budget
- **Features:**
  - Quick expense categorization via WhatsApp
  - Daily spending limit calculator
  - Essential vs non-essential expense identification
  - Next 7-day survival plan

### Phase 2: Basic Financial Literacy
**Problem:** "I don't understand where my money goes"
- **Solution:** Simple expense tracking and insights
- **Features:**
  - Voice message expense logging
  - Weekly spending summaries
  - Category-based insights (food, transport, bills)
  - Simple saving tips based on spending patterns

### Phase 3: Goal-Based Savings
**Problem:** "I can never save money"
- **Solution:** Micro-savings with achievable goals
- **Features:**
  - Small, achievable savings goals (R$50-200)
  - Daily/weekly saving reminders
  - Progress celebrations
  - Emergency fund building

## 🏗️ Technical Architecture

### 1. Conversation State Management
```
User Message → Context Builder → AI Decision → Response
     ↓              ↓                ↓           ↓
  Database     User Profile    Action Type   WhatsApp
```

### 2. Core Components

#### A. Context Builder
- Retrieves last 10 messages from conversation
- Loads user profile (income level, goals, current situation)
- Identifies conversation intent

#### B. AI Decision Engine
- **LLM Integration** (OpenAI/Anthropic)
- **Prompt Templates** for consistent personality
- **Action Classification:**
  - Information request
  - Expense logging
  - Financial advice
  - Goal setting
  - Emergency help

#### C. Response Generator
- Formats AI response for WhatsApp
- Adds interactive buttons/quick replies
- Includes progress indicators
- Maintains Arnaldo's friendly tone

### 3. Data Model Extensions

```sql
-- User financial profile
CREATE TABLE user_profiles (
  user_id UUID REFERENCES users(id),
  monthly_income DECIMAL(10,2),
  income_type VARCHAR(50), -- formal, informal, variable
  family_size INTEGER,
  financial_goals JSONB,
  created_at TIMESTAMP DEFAULT NOW()
);

-- Expense tracking
CREATE TABLE expenses (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users(id),
  category VARCHAR(50),
  amount DECIMAL(10,2),
  description TEXT,
  logged_via VARCHAR(20), -- text, voice, image
  created_at TIMESTAMP DEFAULT NOW()
);

-- Financial insights
CREATE TABLE insights (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users(id),
  type VARCHAR(50), -- weekly_summary, saving_tip, warning
  content TEXT,
  delivered_at TIMESTAMP
);
```

## 🚀 Implementation Plan

### Week 1: Basic Context & LLM Integration
1. Set up OpenAI/Anthropic API integration
2. Create context builder to retrieve conversation history
3. Design Arnaldo's base prompt and personality
4. Implement basic Q&A flow

### Week 2: Expense Tracking MVP
1. Add expense logging via text messages
2. Create expense categorization logic
3. Build daily spending summary
4. Test with real users

### Week 3: Financial Insights
1. Implement weekly spending analysis
2. Add personalized saving tips
3. Create emergency budget calculator
4. Deploy and monitor

## 💬 Example Conversations

### Scenario 1: Emergency Help
```
User: "Arnaldo, acabou meu dinheiro e ainda faltam 5 dias pro pagamento"

Arnaldo: "Calma, vou te ajudar! 💪 Primeiro, vamos ver quanto você tem:
1. Tem algum dinheiro guardado? (mesmo moedas)
2. Já pagou as contas essenciais?
3. Quanto precisa por dia até o pagamento?

Responde uma por vez que eu monto um plano de emergência pra você"
```

### Scenario 2: Expense Tracking
```
User: "Gastei 45 reais no mercado"

Arnaldo: "Anotado! 🛒 R$45 no mercado. 

Seus gastos hoje: R$67
Limite diário sugerido: R$50

Dica: Você passou R$17 do limite. Tenta compensar amanhã gastando só R$33. Vou te lembrar! 😊"
```

### Scenario 3: Savings Goal
```
User: "Quero guardar dinheiro mas nunca consigo"

Arnaldo: "Vamos começar pequeno! Que tal R$1 por dia? 🐷

Em 30 dias = R$30
Em 6 meses = R$180

Parece pouco? Com R$180 você:
- Compra gás por 2 meses
- Paga uma conta de luz
- Tem emergência coberta

Bora começar? Eu te lembro todo dia!"
```

## 🎨 Arnaldo's Personality

- **Friendly & Supportive:** Never judges, always encourages
- **Practical:** Focuses on actionable advice
- **Brazilian:** Uses local expressions, understands context
- **Patient:** Repeats information when needed
- **Celebratory:** Celebrates small wins

## 📊 Success Metrics

1. **Engagement:** Daily active users
2. **Retention:** Users active after 7, 30 days
3. **Behavior Change:** % of users tracking expenses
4. **Savings:** Average amount saved per user
5. **NPS:** User satisfaction scores

## 🔄 Feedback Loop

1. Weekly user interviews via WhatsApp
2. Analyze conversation patterns
3. Identify confusion points
4. Iterate on Arnaldo's responses
5. A/B test different approaches