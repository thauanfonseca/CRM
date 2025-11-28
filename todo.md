# Perícia CRM - TODO

## Design & Estilo
- [x] Configurar tema dark com cores: Cyan (#00D9FF), Coral (#FF6B6B), Verde (#00D084)
- [x] Implementar CSS global com tokens de design
- [x] Criar componentes de cards com ícones e métricas
- [x] Implementar sidebar de navegação colapsível
- [x] Criar badges de status coloridas

## Banco de Dados
- [x] Criar schema para Perícias (título, processo, status, tipo, valor, partes)
- [x] Criar schema para Assistências Técnicas
- [x] Criar schema para Clientes
- [x] Criar schema para Especialistas
- [x] Criar schema para Tarefas
- [x] Criar schema para Relatórios
- [x] Executar migrações com `pnpm db:push`

## Backend (tRPC)
- [x] Criar procedures para CRUD de Perícias
- [x] Criar procedures para CRUD de Assistências
- [x] Criar procedures para CRUD de Clientes
- [x] Criar procedures para CRUD de Especialistas
- [x] Criar procedures para Tarefas
- [x] Criar procedures para Relatórios
- [x] Implementar cálculos de métricas (total, em andamento, concluídas)
- [x] Implementar filtros e buscas

## Frontend - Layout Base
- [x] Implementar DashboardLayout com sidebar
- [x] Criar navegação principal
- [x] Implementar autenticação e logout
- [ ] Criar página de perfil do usuário

## Frontend - Dashboard
- [x] Criar cards de métricas (Total, Em Andamento, Concluídas, Valor Total)
- [ ] Implementar gráficos de status
- [ ] Criar seção de últimas perícias adicionadas
- [ ] Criar seção de últimas assistências técnicas
- [x] Implementar progresso geral

## Frontend - Gestão de Perícias
- [x] Criar página de listagem de perícias
- [x] Implementar busca e filtros
- [x] Criar modal/formulário de nova perícia
- [ ] Implementar edição de perícia
- [x] Implementar exclusão de perícia
- [ ] Criar página de detalhes de perícia

## Frontend - Gestão de Assistências
- [ ] Criar página de listagem de assistências
- [ ] Implementar busca e filtros
- [ ] Criar modal/formulário de nova assistência
- [ ] Implementar edição de assistência
- [ ] Implementar exclusão de assistência

## Frontend - Gestão de Clientes
- [x] Criar página de listagem de clientes
- [x] Implementar busca
- [x] Criar modal/formulário de novo cliente
- [ ] Implementar edição de cliente
- [ ] Implementar exclusão de cliente

## Frontend - Gestão de Especialistas
- [x] Criar página de listagem de especialistas
- [x] Implementar busca
- [x] Criar modal/formulário de novo especialista
- [ ] Implementar edição de especialista
- [ ] Implementar exclusão de especialista

## Frontend - Financeiro
- [ ] Criar página de controle financeiro
- [ ] Implementar visualização de honorários
- [ ] Criar relatórios de receita

## Frontend - Tarefas
- [x] Criar página de minhas tarefas
- [x] Implementar criação de tarefas
- [ ] Implementar marcação de conclusão
- [x] Implementar filtros de status

## Frontend - Relatórios
- [ ] Criar página de relatórios
- [ ] Implementar geração de relatórios por período
- [ ] Implementar exportação de relatórios

## Frontend - Calendário
- [ ] Integrar calendário para prazos
- [ ] Implementar visualização de prazos

## Testes
- [x] Escrever testes vitest para procedures de perícias
- [x] Escrever testes vitest para procedures de clientes
- [x] Escrever testes vitest para procedures de especialistas
- [x] Testar fluxos de autenticação

## Deployment
- [ ] Criar checkpoint inicial
- [ ] Testar em produção
- [ ] Configurar domínio personalizado
