# Perícia CRM - Sistema Completo de Gestão

## Visão Geral

O **Perícia CRM** é um sistema completo de gerenciamento de relacionamento com clientes (CRM) desenvolvido especificamente para profissionais que atuam com perícias judiciais e assistências técnicas. O sistema oferece uma plataforma integrada para gerenciar todos os aspectos do trabalho pericial, desde o cadastro de clientes até o controle financeiro e calendário de prazos.

## Tecnologias Utilizadas

### Backend
- **Node.js** com **Express** - Servidor web
- **tRPC** - Framework de API type-safe
- **Drizzle ORM** - ORM para MySQL
- **MySQL** - Banco de dados relacional
- **Zod** - Validação de schemas
- **Jose** - Autenticação JWT

### Frontend
- **React 19** - Biblioteca UI
- **Vite** - Build tool e dev server
- **TypeScript** - Tipagem estática
- **Tailwind CSS** - Framework CSS
- **Radix UI** - Componentes acessíveis
- **Wouter** - Roteamento leve
- **TanStack Query** - Gerenciamento de estado servidor
- **React Hook Form** - Gerenciamento de formulários
- **Recharts** - Biblioteca de gráficos
- **Sonner** - Sistema de notificações toast

## Estrutura do Banco de Dados

O sistema utiliza 7 tabelas principais:

### 1. **users** - Usuários do Sistema
- `id` - ID único do usuário
- `openId` - Identificador OAuth
- `name` - Nome do usuário
- `email` - Email do usuário
- `loginMethod` - Método de login
- `role` - Papel (user/admin)
- `createdAt` - Data de criação
- `updatedAt` - Data de atualização
- `lastSignedIn` - Último login

### 2. **pericias** - Perícias Judiciais
- `id` - ID único da perícia
- `userId` - ID do usuário responsável
- `titulo` - Título da perícia
- `processo` - Número do processo (único)
- `status` - Status (em_andamento/concluida/pendente)
- `tipo` - Tipo de perícia
- `valor` - Valor dos honorários (em centavos)
- `autora` - Nome da parte autora
- `re` - Nome da parte ré
- `descricao` - Descrição detalhada
- `prazo` - Data limite
- `createdAt` - Data de criação
- `updatedAt` - Data de atualização

### 3. **assistencias** - Assistências Técnicas
- `id` - ID único da assistência
- `userId` - ID do usuário responsável
- `titulo` - Título da assistência
- `processo` - Número do processo
- `status` - Status (em_andamento/concluida/pendente)
- `valor` - Valor dos honorários (em centavos)
- `descricao` - Descrição detalhada
- `prazo` - Data limite
- `createdAt` - Data de criação
- `updatedAt` - Data de atualização

### 4. **clientes** - Clientes
- `id` - ID único do cliente
- `userId` - ID do usuário responsável
- `nome` - Nome do cliente
- `email` - Email do cliente
- `telefone` - Telefone do cliente
- `endereco` - Endereço completo
- `descricao` - Informações adicionais
- `createdAt` - Data de criação
- `updatedAt` - Data de atualização

### 5. **especialistas** - Especialistas e Peritos
- `id` - ID único do especialista
- `userId` - ID do usuário responsável
- `nome` - Nome do especialista
- `email` - Email do especialista
- `telefone` - Telefone do especialista
- `especialidade` - Área de especialização
- `registroProfissional` - Registro profissional (CREA, CRC, etc.)
- `endereco` - Endereço completo
- `descricao` - Informações adicionais
- `createdAt` - Data de criação
- `updatedAt` - Data de atualização

### 6. **tarefas** - Tarefas e Atividades
- `id` - ID único da tarefa
- `userId` - ID do usuário responsável
- `titulo` - Título da tarefa
- `descricao` - Descrição detalhada
- `status` - Status (pendente/em_progresso/concluida)
- `prioridade` - Prioridade (baixa/media/alta)
- `pericias_id` - ID da perícia vinculada (opcional)
- `prazo` - Data limite
- `createdAt` - Data de criação
- `updatedAt` - Data de atualização

### 7. **relatorios** - Relatórios
- `id` - ID único do relatório
- `userId` - ID do usuário responsável
- `titulo` - Título do relatório
- `tipo` - Tipo do relatório
- `conteudo` - Conteúdo do relatório
- `pericias_id` - ID da perícia vinculada (opcional)
- `createdAt` - Data de criação
- `updatedAt` - Data de atualização

## Funcionalidades Implementadas

### 1. Dashboard (Home)
- **Métricas em tempo real** de perícias e assistências
- **Cards informativos** com totais, em andamento, concluídas e valores
- **Indicadores visuais** de progresso
- **Cálculos automáticos** de honorários e taxas de conclusão
- **Separação clara** entre perícias judiciais e assistências técnicas

### 2. Gestão de Perícias
- **Listagem completa** com busca e filtros
- **Criação de novas perícias** com formulário completo
- **Edição de perícias existentes**
- **Exclusão com confirmação**
- **Visualização de status** com badges coloridas
- **Estatísticas rápidas** (total, em andamento, concluídas, valor total)
- **Campos específicos**: processo, tipo, autora, ré, valor, prazo

### 3. Gestão de Assistências Técnicas
- **Listagem completa** com busca
- **Criação e edição** de assistências
- **Exclusão com confirmação**
- **Visualização de status** e prazos
- **Estatísticas rápidas** por status
- **Controle de valores** e honorários

### 4. Gestão de Clientes
- **Listagem em cards** com informações visuais
- **Busca por nome ou email**
- **Criação e edição** com formulário completo
- **Exclusão com confirmação**
- **Campos**: nome, email, telefone, endereço, descrição
- **Estatísticas**: total, com email, com telefone
- **Ícones visuais** para contatos

### 5. Gestão de Especialistas
- **Listagem em cards** organizada
- **Busca por nome ou especialidade**
- **Criação e edição** de especialistas
- **Exclusão com confirmação**
- **Campos específicos**: especialidade, registro profissional
- **Estatísticas**: total, com registro, com especialidade
- **Visualização destacada** da especialidade

### 6. Gestão de Tarefas
- **Listagem de tarefas** pessoais
- **Criação e edição** de tarefas
- **Filtros por status** (pendente, em progresso, concluída)
- **Prioridades** (baixa, média, alta)
- **Vinculação com perícias**
- **Controle de prazos**

### 7. Relatórios
- **Criação de relatórios** personalizados
- **Editor de conteúdo** com textarea
- **Tipos de relatórios** configuráveis
- **Vinculação com perícias**
- **Histórico completo** de relatórios
- **Estatísticas**: total, do mês, vinculados

### 8. Controle Financeiro
- **Dashboard financeiro** completo
- **Valor total** de todos os serviços
- **Valor recebido** (serviços concluídos)
- **Valor pendente** (em andamento)
- **Taxa de conclusão** percentual
- **Divisão por tipo**: perícias vs assistências
- **Histórico mensal** dos últimos 6 meses
- **Gráficos de barras** para visualização temporal

### 9. Calendário de Prazos
- **Visualização mensal** interativa
- **Navegação entre meses** (anterior/próximo/hoje)
- **Eventos coloridos** por tipo (perícias, assistências, tarefas)
- **Indicador visual** do dia atual
- **Lista de próximos prazos** (5 mais próximos)
- **Legenda** com ícones por tipo
- **Destaque de dias** com múltiplos eventos

### 10. Autenticação e Segurança
- **OAuth com Manus** implementado
- **Sessões persistentes** com cookies
- **Proteção de rotas** (protectedProcedure)
- **Isolamento de dados** por usuário
- **Logout seguro** com limpeza de sessão

## API Backend (tRPC)

Todas as operações CRUD estão implementadas para cada entidade:

### Perícias
- `pericias.list` - Listar todas as perícias do usuário
- `pericias.getById` - Obter perícia por ID
- `pericias.create` - Criar nova perícia
- `pericias.update` - Atualizar perícia existente
- `pericias.delete` - Deletar perícia

### Assistências
- `assistencias.list` - Listar todas as assistências
- `assistencias.getById` - Obter assistência por ID
- `assistencias.create` - Criar nova assistência
- `assistencias.update` - Atualizar assistência
- `assistencias.delete` - Deletar assistência

### Clientes
- `clientes.list` - Listar todos os clientes
- `clientes.getById` - Obter cliente por ID
- `clientes.create` - Criar novo cliente
- `clientes.update` - Atualizar cliente
- `clientes.delete` - Deletar cliente

### Especialistas
- `especialistas.list` - Listar todos os especialistas
- `especialistas.getById` - Obter especialista por ID
- `especialistas.create` - Criar novo especialista
- `especialistas.update` - Atualizar especialista
- `especialistas.delete` - Deletar especialista

### Tarefas
- `tarefas.list` - Listar todas as tarefas
- `tarefas.getById` - Obter tarefa por ID
- `tarefas.create` - Criar nova tarefa
- `tarefas.update` - Atualizar tarefa
- `tarefas.delete` - Deletar tarefa

### Relatórios
- `relatorios.list` - Listar todos os relatórios
- `relatorios.getById` - Obter relatório por ID
- `relatorios.create` - Criar novo relatório
- `relatorios.update` - Atualizar relatório
- `relatorios.delete` - Deletar relatório

### Autenticação
- `auth.me` - Obter dados do usuário atual
- `auth.logout` - Fazer logout

## Estrutura de Arquivos

```
/home/ubuntu/
├── client/src/
│   ├── pages/
│   │   ├── Home.tsx                 # Dashboard principal
│   │   ├── Pericias.tsx             # Gestão de perícias
│   │   ├── Assistencias.tsx         # Gestão de assistências (NOVO)
│   │   ├── Clientes.tsx             # Gestão de clientes (MELHORADO)
│   │   ├── Especialistas.tsx        # Gestão de especialistas (MELHORADO)
│   │   ├── Tarefas.tsx              # Gestão de tarefas
│   │   ├── Relatorios.tsx           # Gestão de relatórios (NOVO)
│   │   ├── Financeiro.tsx           # Controle financeiro (NOVO)
│   │   ├── Calendario.tsx           # Calendário de prazos (NOVO)
│   │   └── NotFound.tsx             # Página 404
│   ├── components/
│   │   ├── DashboardLayout.tsx      # Layout principal (ATUALIZADO)
│   │   ├── ErrorBoundary.tsx        # Tratamento de erros
│   │   └── ui/                      # Componentes UI (Radix + shadcn)
│   ├── App.tsx                      # Configuração de rotas (ATUALIZADO)
│   └── main.tsx                     # Ponto de entrada
├── server/
│   ├── routers.ts                   # Rotas tRPC (COMPLETO)
│   ├── db.ts                        # Funções de banco (COMPLETO)
│   └── _core/                       # Configurações do servidor
├── drizzle/
│   ├── schema.ts                    # Schema do banco de dados
│   └── relations.ts                 # Relações entre tabelas
├── shared/
│   ├── types.ts                     # Tipos compartilhados
│   └── const.ts                     # Constantes
├── package.json                     # Dependências
├── drizzle.config.ts                # Configuração do Drizzle
├── vite.config.ts                   # Configuração do Vite
└── tsconfig.json                    # Configuração do TypeScript
```

## Como Executar

### 1. Instalar Dependências
```bash
cd /home/ubuntu
pnpm install
```

### 2. Configurar Banco de Dados
Certifique-se de que a variável `DATABASE_URL` está configurada no arquivo `.env`:
```
DATABASE_URL=mysql://user:password@host:port/database
```

### 3. Executar Migrações
```bash
pnpm db:push
```

### 4. Iniciar em Desenvolvimento
```bash
pnpm dev
```

O servidor estará disponível em `http://localhost:5000` (ou porta configurada).

### 5. Build para Produção
```bash
pnpm build
pnpm start
```

## Design e Tema

O sistema utiliza um **tema dark** moderno com as seguintes cores principais:

- **Primary (Cyan)**: `#00D9FF` - Usado para perícias e elementos principais
- **Secondary (Coral)**: `#FF6B6B` - Usado para assistências e elementos secundários
- **Accent (Cyan)**: `#00D9FF` - Usado para estados "em andamento"
- **Success (Verde)**: `#00D084` - Usado para estados "concluído"
- **Warning (Laranja)**: Usado para estados "pendente"

### Componentes UI
Todos os componentes seguem o padrão **shadcn/ui** com **Radix UI**, garantindo:
- Acessibilidade (ARIA)
- Responsividade
- Animações suaves
- Consistência visual

## Melhorias Implementadas

### Backend
✅ CRUD completo para todas as entidades  
✅ Validação de dados com Zod  
✅ Isolamento de dados por usuário  
✅ Tratamento de erros consistente  
✅ Type-safety com tRPC  

### Frontend
✅ 9 páginas funcionais completas  
✅ Edição inline para todas as entidades  
✅ Exclusão com confirmação  
✅ Busca e filtros em todas as listagens  
✅ Estatísticas em tempo real  
✅ Notificações toast (sucesso/erro)  
✅ Loading states em todas as operações  
✅ Formulários validados  
✅ Design responsivo  
✅ Navegação intuitiva  

### Novas Funcionalidades
✅ Página de Assistências Técnicas completa  
✅ Página de Relatórios  
✅ Página de Controle Financeiro  
✅ Página de Calendário de Prazos  
✅ Edição de Clientes e Especialistas  
✅ Estatísticas financeiras avançadas  
✅ Histórico mensal de receitas  
✅ Visualização de próximos prazos  

## Próximas Melhorias Sugeridas

### Funcionalidades Avançadas
- [ ] Gráficos interativos no dashboard (pizza, linhas)
- [ ] Exportação de dados (Excel, PDF)
- [ ] Sistema de notificações push
- [ ] Alertas automáticos de prazos vencendo
- [ ] Upload de documentos anexos
- [ ] Histórico de alterações (audit log)
- [ ] Busca global avançada
- [ ] Filtros salvos/favoritos
- [ ] Dashboard customizável

### Integrações
- [ ] Integração com Google Calendar
- [ ] Envio de emails automáticos
- [ ] WhatsApp Business API
- [ ] Backup automático
- [ ] Sincronização em nuvem

### Performance
- [ ] Paginação de listas grandes
- [ ] Cache de queries
- [ ] Lazy loading de componentes
- [ ] Service Worker para offline

### UX/UI
- [ ] Modo claro/escuro toggle
- [ ] Temas personalizáveis
- [ ] Atalhos de teclado
- [ ] Tour guiado para novos usuários
- [ ] Ajuda contextual

## Testes

O projeto está configurado com **Vitest** para testes. Existem alguns testes básicos implementados:

```bash
# Executar testes
pnpm test

# Executar testes em modo watch
pnpm test --watch
```

Testes existentes:
- `server/auth.logout.test.ts` - Testes de autenticação
- `server/pericias.test.ts` - Testes de perícias

## Segurança

### Medidas Implementadas
- ✅ Autenticação OAuth obrigatória
- ✅ Sessões com cookies httpOnly
- ✅ Isolamento de dados por usuário
- ✅ Validação de entrada com Zod
- ✅ Proteção contra SQL injection (Drizzle ORM)
- ✅ CORS configurado
- ✅ Rate limiting (pode ser adicionado)

### Recomendações
- Sempre use HTTPS em produção
- Configure variáveis de ambiente seguras
- Implemente rate limiting
- Adicione logs de auditoria
- Configure backups automáticos

## Suporte e Documentação

Para mais informações sobre as tecnologias utilizadas:

- [React](https://react.dev/)
- [tRPC](https://trpc.io/)
- [Drizzle ORM](https://orm.drizzle.team/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Radix UI](https://www.radix-ui.com/)
- [Vite](https://vitejs.dev/)

## Licença

MIT

---

**Desenvolvido com ❤️ para profissionais de perícia judicial**
