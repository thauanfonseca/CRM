# Plano de Desenvolvimento - Perícia CRM Completo

## Visão Geral
Completar o desenvolvimento do CRM para gestão de perícias judiciais e assistências técnicas, adicionando todas as funcionalidades faltantes identificadas no arquivo TODO.

## Arquitetura Atual
- **Backend**: Node.js + Express + tRPC + Drizzle ORM + MySQL
- **Frontend**: React 19 + Vite + Tailwind CSS + Wouter (routing)
- **Componentes UI**: Radix UI + shadcn/ui
- **Autenticação**: OAuth com Manus (já implementada)

## Funcionalidades a Implementar

### 1. Backend - Completar CRUD Operations
- [x] Perícias: list, create, getById, update, delete
- [ ] Assistências: adicionar update, delete, getById
- [ ] Clientes: adicionar update, delete, getById
- [ ] Especialistas: adicionar update, delete, getById
- [ ] Tarefas: adicionar update, delete, getById
- [ ] Relatórios: adicionar update, delete, getById
- [ ] Adicionar procedures para métricas financeiras
- [ ] Adicionar procedures para estatísticas do dashboard

### 2. Frontend - Páginas Completas

#### Dashboard (Home)
- [x] Cards de métricas básicas
- [ ] Gráficos de status (pizza/barras)
- [ ] Últimas perícias adicionadas
- [ ] Últimas assistências técnicas
- [ ] Tarefas pendentes próximas do prazo
- [ ] Alertas de prazos vencendo

#### Perícias
- [x] Listagem com busca e filtros
- [x] Criar nova perícia
- [ ] Editar perícia (modal)
- [x] Excluir perícia
- [ ] Página de detalhes da perícia
- [ ] Anexar documentos
- [ ] Histórico de alterações

#### Assistências Técnicas (NOVA)
- [ ] Listagem com busca e filtros
- [ ] Criar nova assistência
- [ ] Editar assistência
- [ ] Excluir assistência
- [ ] Página de detalhes

#### Clientes
- [x] Listagem com busca
- [x] Criar novo cliente
- [ ] Editar cliente
- [ ] Excluir cliente
- [ ] Página de detalhes do cliente
- [ ] Histórico de perícias/assistências

#### Especialistas
- [x] Listagem com busca
- [x] Criar novo especialista
- [ ] Editar especialista
- [ ] Excluir especialista
- [ ] Página de detalhes
- [ ] Histórico de trabalhos

#### Tarefas
- [x] Listagem com filtros
- [x] Criar nova tarefa
- [ ] Editar tarefa
- [ ] Marcar como concluída
- [ ] Excluir tarefa
- [ ] Vincular a perícias/assistências

#### Financeiro (NOVA)
- [ ] Dashboard financeiro
- [ ] Controle de honorários
- [ ] Receitas por período
- [ ] Gráficos de faturamento
- [ ] Exportar relatórios financeiros

#### Relatórios (NOVA)
- [ ] Listagem de relatórios
- [ ] Criar novo relatório
- [ ] Editar relatório
- [ ] Visualizar relatório
- [ ] Exportar em PDF
- [ ] Relatórios por período

#### Calendário (NOVA)
- [ ] Visualização mensal
- [ ] Prazos de perícias
- [ ] Prazos de assistências
- [ ] Tarefas agendadas
- [ ] Alertas de vencimento

#### Perfil do Usuário (NOVA)
- [ ] Visualizar dados do perfil
- [ ] Editar informações
- [ ] Configurações do sistema
- [ ] Preferências de notificação

### 3. Componentes Reutilizáveis
- [ ] DataTable genérica com paginação
- [ ] Filtros avançados
- [ ] Modal de confirmação
- [ ] Upload de arquivos
- [ ] Visualizador de documentos
- [ ] Gráficos (usando Recharts)
- [ ] Calendário (usando react-day-picker)

### 4. Funcionalidades Avançadas
- [ ] Sistema de notificações
- [ ] Alertas de prazos
- [ ] Busca global
- [ ] Exportação de dados (Excel/PDF)
- [ ] Backup de dados
- [ ] Logs de auditoria

## Priorização de Implementação

### Fase 1: Backend Completo
1. Completar CRUD de todas as entidades
2. Adicionar procedures de métricas
3. Implementar filtros avançados

### Fase 2: Páginas Principais
1. Assistências Técnicas (completa)
2. Edição de Perícias, Clientes, Especialistas
3. Detalhes de cada entidade

### Fase 3: Páginas Secundárias
1. Financeiro
2. Relatórios
3. Calendário
4. Perfil do Usuário

### Fase 4: Melhorias e Polimento
1. Gráficos no dashboard
2. Sistema de notificações
3. Exportação de dados
4. Testes completos

## Estrutura de Arquivos

```
/home/ubuntu/
├── client/src/
│   ├── pages/
│   │   ├── Home.tsx (✓ melhorar)
│   │   ├── Pericias.tsx (✓ melhorar)
│   │   ├── Assistencias.tsx (criar)
│   │   ├── Clientes.tsx (✓ melhorar)
│   │   ├── Especialistas.tsx (✓ melhorar)
│   │   ├── Tarefas.tsx (✓ melhorar)
│   │   ├── Financeiro.tsx (criar)
│   │   ├── Relatorios.tsx (criar)
│   │   ├── Calendario.tsx (criar)
│   │   └── Perfil.tsx (criar)
│   └── components/
│       ├── DataTable.tsx (criar)
│       ├── Charts/ (criar)
│       └── Modals/ (criar)
├── server/
│   ├── routers.ts (✓ expandir)
│   └── db.ts (✓ expandir)
└── drizzle/
    └── schema.ts (✓ já completo)
```

## Tecnologias Adicionais Necessárias
- Recharts (já instalado) - para gráficos
- react-day-picker (já instalado) - para calendário
- jsPDF ou similar - para exportação PDF
- xlsx - para exportação Excel

## Métricas de Sucesso
- [ ] Todas as operações CRUD funcionando
- [ ] Todas as páginas navegáveis
- [ ] Dashboard com métricas em tempo real
- [ ] Sistema responsivo
- [ ] Testes passando
- [ ] Performance adequada
