🏥 Sistema de Agendamento - Clínica Médica
Sistema completo de agendamento de consultas médicas desenvolvido com Vue.js (frontend) e Node.js (backend), incluindo autenticação JWT, integração com APIs externas e painel administrativo.

📋 Funcionalidades:
    
    🔐 Autenticação e Segurança:

        Login e cadastro seguro com JWT
        Middleware de proteção de rotas
        Diferentes níveis de acesso (paciente/secretário)
        Senhas criptografadas com bcryptjs
    
    📅 Agendamentos:

        Agendamento de consultas com verificação de disponibilidade
        Visualização de horários livres em tempo real
        Status de agendamentos (agendado, confirmado, cancelado)
        Observações e detalhes da consulta
    
    🌍 Integrações com APIs Externas:

        ViaCEP: Preenchimento automático de endereço
        OpenWeatherMap: Previsão do tempo para o dia da consulta
        Alertas de chuva para os pacientes
    
    👨‍💼 Painel Administrativo:

        Gerenciamento de todos os agendamentos
        Estatísticas em tempo real
        Alteração de status dos agendamentos
        Exportação de dados em CSV

🛠 Tecnologias Utilizadas:

    Backend:

        Node.js - Runtime JavaScript
        Express.js - Framework web
        PostgreSQL - Banco de dados
        JWT - Autenticação
        Bcrypt - Criptografia de senhas
        Axios - Requisições HTTP

    Frontend:

        Vue.js 3 - Framework JavaScript reativo
        Axios - Cliente HTTP
        CSS3 - Estilização responsiva
        Font Awesome - Ícones

🚀 Instalação e Configuração

    Pré-requisitos:

        Node.js 16+ instalado
        PostgreSQL instalado e rodando
        Conta na OpenWeatherMap (API gratuita)

# 1. Configuração do Banco de Dados

    bash

    # Conectar ao PostgreSQL

    psql -U postgres

    # Criar banco de dados

    CREATE DATABASE clinica_db;

    # Executar script de inicialização

    \i init.sql

# 2. Configuração do Backend

    bash

    # Navegar para o diretório backend

    cd backend

    # Instalar dependências
    npm install

    # Copiar arquivo de ambiente
    cp .env.example .env

    # Editar .env com suas configurações
    DATABASE_URL=postgresql://username:password@localhost:5432/clinica_db
    JWT_SECRET=sua_chave_secreta_jwt_muito_segura_aqui
    OPENWEATHER_API_KEY=sua_api_key_openweather_aqui
    PORT=3000
    NODE_ENV=development
# 3. Obter API Key do OpenWeatherMap
    Acesse OpenWeatherMap
    Crie uma conta gratuita
    Gere sua API key
    Adicione no arquivo .env
# 4. Iniciar o Backend
    bash
    # Ambiente de desenvolvimento
    npm run dev

    # Ambiente de produção
    npm start
    O servidor estará rodando em http://localhost:3000

# 5. Configuração do Frontend
    bash
    # Navegar para o diretório frontend
    cd frontend

    # Instalar dependências (opcional - para live-server)
    npm install

    # Ou simplesmente abrir o index.html no navegador
Para desenvolvimento com live-server:

bash
npm run dev
O frontend estará disponível em http://localhost:8080

👤 Usuários de Teste
Secretário (Admin)
Email: admin@clinica.com
Senha: admin123
Paciente
Email: joao@email.com
Senha: teste123
📱 Como Usar
Para Pacientes:
Cadastro/Login: Crie sua conta ou faça login
Novo Agendamento:
Selecione data e horário disponível
Escolha especialidade e médico
Adicione observações se necessário
Visualizar Agendamentos: Veja suas consultas e previsão do tempo
Acompanhar Status: Receba atualizações do status da consulta
Para Secretários:
Login: Use as credenciais de secretário
Painel Admin: Acesse estatísticas e controles
Gerenciar Agendamentos:
Visualize todos os agendamentos
Altere status das consultas
Exporte dados para análise
Criar Agendamentos: Agende consultas para pacientes
🔧 Estrutura do Projeto
clinica-system/
├── backend/
│   ├── server.js          # Servidor principal
│   ├── package.json       # Dependências backend
│   └── .env.example      # Configurações de ambiente
├── frontend/
│   ├── index.html        # Aplicação Vue.js
│   └── package.json      # Dependências frontend
├── database/
│   └── init.sql          # Script de inicialização
└── README.md             # Esta documentação
🌐 Deploy
Deploy do Backend (Heroku)
bash
# Instalar Heroku CLI
# Criar app no Heroku
heroku create clinica-backend

# Configurar variáveis de ambiente
heroku config:set DATABASE_URL=postgresql://...
heroku config:set JWT_SECRET=...
heroku config:set OPENWEATHER_API_KEY=...

# Deploy
git push heroku main
Deploy do Frontend (Netlify/Vercel)
Faça upload dos arquivos frontend
Configure a URL da API no código
Deploy automático
🔒 Segurança
Senhas criptografadas com bcrypt
Autenticação JWT com expiração
Validação de dados no backend
Proteção contra SQL injection
CORS configurado adequadamente
📊 APIs Utilizadas
Endpoints Principais
POST   /api/register          # Cadastro de usuários
POST   /api/login             # Autenticação
GET    /api/agendamentos      # Listar agendamentos
POST   /api/agendamentos      # Criar agendamento
PUT    /api/agendamentos/:id/status  # Atualizar status
GET    /api/horarios-disponiveis    # Horários disponíveis
GET    /api/cep/:cep               # Buscar endereço por CEP
APIs Externas
ViaCEP: https://viacep.com.br/ws/{cep}/json/
OpenWeatherMap: https://api.openweathermap.org/data/2.5/forecast
🐛 Solução de Problemas
Backend não conecta ao banco
bash
# Verificar se PostgreSQL está rodando
sudo service postgresql start

# Testar conexão
psql -U postgres -d clinica_db
Erro de CORS
Verifique se o backend está rodando na porta correta
Confirme a URL da API no frontend
API do clima não funciona
Verifique se a API key está correta no .env
Teste a API key no navegador: https://api.openweathermap.org/data/2.5/weather?q=Salvador&appid=SUA_API_KEY
Horários não carregam
Verifique se a data selecionada não é no passado
Confirme se o token JWT está válido
📈 Próximas Funcionalidades
 Notificações por email
 Sistema de lembretes SMS
 Integração com Google Calendar
 Relatórios avançados
 Chat em tempo real
 Sistema de avaliações
 Prontuário eletrônico básico
🤝 Contribuição
Fork o projeto
Crie uma branch para sua feature (git checkout -b feature/AmazingFeature)
Commit suas mudanças (git commit -m 'Add some AmazingFeature')
Push para a branch (git push origin feature/AmazingFeature)
Abra um Pull Request
📝 Licença
Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

👨‍💻 Desenvolvimento
Scripts Disponíveis
Backend:

bash
npm start        # Produção
npm run dev      # Desenvolvimento com nodemon
Frontend:

bash
    npm run dev      # Servidor de desenvolvimento
    npm run build    # Build para produção
    npm start        # Servidor de produção

Estrutura de Dados
Usuário:

javascript
{
  id: number,
  nome: string,
  email: string,
  tipo: 'paciente' | 'secretario',
  telefone: string,
  cep: string,
  endereco: string
}
Agendamento:

javascript
{
  id: number,
  paciente_id: number,
  data_consulta: date,
  hora_consulta: time,
  especialidade: string,
  medico: string,
  observacoes: string,
  status: 'agendado' | 'confirmado' | 'cancelado',
  previsao_clima: string
}

🔍 Testes

Testar Backend
    bash
    # Testar endpoints com curl
    curl -X POST http://localhost:3000/api/login \
      -H "Content-Type: application/json" \
      -d '{"email":"admin@clinica.com","senha":"admin123"}'

Testar Frontend
    Abra o navegador em http://localhost:8080

📞 Suporte
Para suporte e dúvidas: Instagram: @ocaique.adm / Gmail: morekaik27@gmail.com

📧 Email: suporte@clinica.com
💬 Issues no GitHub
📚 Documentação: [Wiki do Projeto]
🏆 Créditos
Desenvolvido como projeto acadêmico seguindo as melhores práticas de desenvolvimento web moderno.

Referências Bibliográficas:

ALVES, W. P. Projetos de sistemas web: conceitos, estruturas, criação de banco de dados e ferramentas de desenvolvimento. São Paulo: Saraiva, 2015.
FREITAS, P. H. C.; BIRNFELD, K.; SARAIVA, M. O. Programação back end III. Porto Alegre: Grupo A, 2021.
OLIVEIRA, C. L. V.; ZANETTI, H. A. P. Javascript descomplicado: programação para web, iot e dispositivos móveis. São Paulo: Saraiva, 2020.

🚀 Deploy Rápido
# Opção 1: Local
    bash
    
# Backend
cd backend && npm install && npm run dev

# Frontend (nova aba)
cd frontend && open index.html

# Opção 2: Docker (Opcional)
dockerfile
Dockerfile backend
FROM node:16
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]

# Opção 3: Heroku + Netlify
Backend: Deploy no Heroku com PostgreSQL addon
Frontend: Deploy no Netlify com build automático
Banco: Usar Heroku Postgres (gratuito até 10k rows)
⚡ Sistema pronto para produção com todas as funcionalidades implementadas!

Checklist de Entrega ✅
 Backend Node.js + Express completo
 Frontend Vue.js responsivo
 Autenticação JWT segura
 Integração ViaCEP para endereços
 Integração OpenWeatherMap para clima
 Painel administrativo funcional
 Banco PostgreSQL estruturado
 Documentação completa
 Usuários de teste configurados
 Scripts de deploy prontos
 Tratamento de erros implementado
 Interface responsiva e moderna
 Validações de segurança aplicadas

