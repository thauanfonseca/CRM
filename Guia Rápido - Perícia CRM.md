# Guia Rápido - Perícia CRM

## 🚀 Início Rápido

### 1. Instalação
```bash
cd /home/ubuntu
pnpm install
```

### 2. Configuração do Banco de Dados
Edite o arquivo `.env` e adicione sua string de conexão MySQL:
```env
DATABASE_URL=mysql://usuario:senha@localhost:3306/pericia_crm
```

### 3. Executar Migrações
```bash
pnpm db:push
```

### 4. Iniciar o Servidor de Desenvolvimento
```bash
pnpm dev
```

O sistema estará disponível em: `http://localhost:5000`

## 📱 Páginas Disponíveis

### 1. Dashboard (/)
- Visão geral de perícias e assistências
- Métricas em tempo real
- Indicadores de progresso

### 2. Perícias (/pericias)
- Listar todas as perícias
- Criar, editar e excluir perícias
- Buscar por título ou processo
- Visualizar estatísticas

### 3. Assistências (/assistencias)
- Listar todas as assistências técnicas
- Criar, editar e excluir assistências
- Buscar e filtrar
- Visualizar estatísticas

### 4. Clientes (/clientes)
- Listar todos os clientes
- Criar, editar e excluir clientes
- Buscar por nome ou email
- Visualizar contatos

### 5. Especialistas (/especialistas)
- Listar todos os especialistas
- Criar, editar e excluir especialistas
- Buscar por nome ou especialidade
- Visualizar registros profissionais

### 6. Tarefas (/tarefas)
- Listar todas as tarefas
- Criar, editar e excluir tarefas
- Filtrar por status e prioridade
- Vincular a perícias

### 7. Relatórios (/relatorios)
- Listar todos os relatórios
- Criar, editar e excluir relatórios
- Editor de conteúdo
- Vincular a perícias

### 8. Financeiro (/financeiro)
- Dashboard financeiro completo
- Valores totais, recebidos e pendentes
- Divisão por tipo de serviço
- Histórico mensal

### 9. Calendário (/calendario)
- Visualização mensal de prazos
- Navegação entre meses
- Próximos prazos destacados
- Eventos por tipo

## 🎨 Cores do Sistema

- **Primary (Cyan)**: #00D9FF - Perícias e elementos principais
- **Secondary (Coral)**: #FF6B6B - Assistências e elementos secundários
- **Accent (Cyan)**: #00D9FF - Estados "em andamento"
- **Success (Verde)**: #00D084 - Estados "concluído"
- **Warning (Laranja)**: Estados "pendente"

## 📊 Status dos Serviços

### Perícias e Assistências
- **Em Andamento**: Serviço em execução
- **Concluída**: Serviço finalizado
- **Pendente**: Aguardando início

### Tarefas
- **Pendente**: Tarefa não iniciada
- **Em Progresso**: Tarefa em execução
- **Concluída**: Tarefa finalizada

### Prioridades
- **Baixa**: Pode esperar
- **Média**: Prioridade normal
- **Alta**: Urgente

## 💡 Dicas de Uso

### Criando uma Perícia
1. Acesse "Perícias" no menu
2. Clique em "Nova Perícia"
3. Preencha os campos obrigatórios (Título e Processo)
4. Adicione informações opcionais (Tipo, Valor, Partes, Descrição)
5. Clique em "Criar Perícia"

### Editando Registros
1. Localize o registro na lista
2. Clique no ícone de lápis (Editar)
3. Modifique os campos desejados
4. Clique em "Atualizar"

### Excluindo Registros
1. Localize o registro na lista
2. Clique no ícone de lixeira (Excluir)
3. Confirme a exclusão

### Buscando Registros
- Use a barra de busca no topo de cada página
- A busca funciona em tempo real
- Busca por título, nome, processo, etc.

### Visualizando Estatísticas
- Cards de estatísticas aparecem no topo de cada página
- Dashboard mostra métricas gerais
- Financeiro mostra valores detalhados

## 🔧 Comandos Úteis

### Desenvolvimento
```bash
pnpm dev          # Iniciar servidor de desenvolvimento
pnpm check        # Verificar erros de TypeScript
pnpm format       # Formatar código com Prettier
```

### Banco de Dados
```bash
pnpm db:push      # Executar migrações
```

### Produção
```bash
pnpm build        # Build para produção
pnpm start        # Iniciar servidor de produção
```

### Testes
```bash
pnpm test         # Executar testes
```

## 🐛 Solução de Problemas

### Erro de Conexão com Banco de Dados
1. Verifique se o MySQL está rodando
2. Confirme as credenciais no arquivo `.env`
3. Teste a conexão manualmente

### Erro ao Instalar Dependências
1. Limpe o cache: `pnpm store prune`
2. Delete `node_modules` e `pnpm-lock.yaml`
3. Execute `pnpm install` novamente

### Página em Branco
1. Verifique o console do navegador (F12)
2. Confirme se o servidor está rodando
3. Limpe o cache do navegador

### Erro de Autenticação
1. Faça logout e login novamente
2. Limpe os cookies do navegador
3. Verifique as configurações OAuth

## 📚 Recursos Adicionais

### Documentação Completa
Consulte `README_CRM.md` para documentação detalhada.

### Status do Projeto
Consulte `TODO_ATUALIZADO.md` para ver o que está implementado e o que está pendente.

### Estrutura de Arquivos
```
/home/ubuntu/
├── client/src/          # Frontend React
│   ├── pages/          # Páginas da aplicação
│   ├── components/     # Componentes reutilizáveis
│   └── App.tsx         # Configuração de rotas
├── server/             # Backend tRPC
│   ├── routers.ts      # Rotas da API
│   └── db.ts           # Funções de banco
├── drizzle/            # Schema do banco
└── shared/             # Código compartilhado
```

## 🎯 Próximos Passos

1. **Explore o Dashboard**: Veja as métricas gerais
2. **Cadastre Clientes**: Adicione seus clientes
3. **Cadastre Especialistas**: Adicione peritos e especialistas
4. **Crie Perícias**: Comece a gerenciar suas perícias
5. **Adicione Tarefas**: Organize seu trabalho
6. **Acompanhe Financeiro**: Monitore seus honorários
7. **Use o Calendário**: Gerencie seus prazos

## 💬 Suporte

Para dúvidas ou problemas:
1. Consulte a documentação completa
2. Verifique os logs do servidor
3. Revise o console do navegador

---

**Boa sorte com seu CRM! 🚀**
