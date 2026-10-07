<div align="center">

# 🚗 OneCar — Aluguel de Carros 100% Digital

**Escolha o carro, defina o período, pague pelo app e retire no local combinado. Sem fila, sem atendente, sem burocracia.**

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![Versão](https://img.shields.io/badge/vers%C3%A3o-1.0.0-blue)
![Licença](https://img.shields.io/badge/licen%C3%A7a-MIT-green)
![Build](https://img.shields.io/badge/build-passing-brightgreen)
![Coverage](https://img.shields.io/badge/coverage-85%25-success)
![PRs](https://img.shields.io/badge/PRs-welcome-orange)

![C#](https://img.shields.io/badge/C%23-239120?logo=csharp&logoColor=white)
![.NET](https://img.shields.io/badge/.NET-512BD4?logo=dotnet&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?logo=react&logoColor=61DAFB)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?logo=microsoftsqlserver&logoColor=white)
![Figma](https://img.shields.io/badge/Figma-F24E1E?logo=figma&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)

[Sobre](#-sobre-o-projeto) •
[Funcionalidades](#-funcionalidades) •
[Telas](#-telas-do-sistema) •
[UML](#-diagramas-uml) •
[Stack](#-stack-de-tecnologia) •
[Instalação](#-como-executar) •
[API](#-documentação-da-api) •
[Contribuição](#-como-contribuir)

</div>

---

## 📑 Sumário

- [Sobre o projeto](#-sobre-o-projeto)
- [Problema e solução](#-problema-e-solução)
- [Funcionalidades](#-funcionalidades)
- [Telas do sistema](#-telas-do-sistema)
- [Diagramas UML](#-diagramas-uml)
- [Stack de tecnologia](#-stack-de-tecnologia)
- [Arquitetura](#-arquitetura)
- [Estrutura de pastas](#-estrutura-de-pastas)
- [Como executar](#-como-executar)
- [Configuração](#-configuração-appsettingsjson)
- [Documentação da API](#-documentação-da-api)
- [Testes](#-testes)
- [Roadmap](#-roadmap)
- [Como contribuir](#-como-contribuir)
- [Equipe](#-equipe)

---

## 📖 Sobre o projeto

O **OneCar** é uma plataforma de aluguel de veículos totalmente digital, inspirada nas grandes locadoras do mercado. Todo o processo acontece pelo aplicativo: o cliente escolhe o carro, define o período de locação, seleciona a forma de pagamento e retira o veículo em um ponto pré-definido (como aeroportos, rodoviárias e estações), **sem a necessidade de um atendente**.

O projeto foi desenvolvido com foco em **simplicidade, segurança e praticidade**, entregando a experiência essencial de qualquer locadora: reservar, pagar, retirar e devolver.

## 🎯 Problema e solução

| Problema | Solução |
|---|---|
| Filas e demora no balcão de atendimento | Reserva e contrato 100% pelo app |
| Custos altos com equipe de atendimento | Processo automatizado e autoatendimento |
| Falta de transparência no valor final | Cálculo de preço em tempo real, antes de confirmar |
| Horário de atendimento limitado | Disponibilidade 24h por dia, 7 dias por semana |
| Burocracia na retirada do carro | Retirada com QR Code e verificação de documentos digital |

---

## ✨ Funcionalidades

### 👤 Cliente
- Cadastro e login (e-mail, Google e Apple)
- Validação de CNH e documento com foto
- Busca de veículos por categoria, preço, câmbio e disponibilidade
- Filtro por local de retirada e devolução
- Simulação de preço por período
- Pagamento via **Pix, cartão de crédito, cartão de débito e boleto**
- Retirada do veículo por **QR Code / chave digital**
- Histórico de reservas e recibos
- Cancelamento e alteração de reserva
- Avaliação do veículo e do serviço
- Notificações push (confirmação, lembrete de retirada e devolução)

### 🛠️ Administrador
- Painel de gestão de frota
- Cadastro, edição e inativação de veículos
- Gestão de locais de retirada
- Controle de reservas e pagamentos
- Relatórios financeiros e de ocupação
- Gestão de usuários e documentos pendentes

### 🔒 Segurança
- Autenticação JWT com refresh token
- Criptografia de senhas com bcrypt
- Comunicação via HTTPS
- Conformidade com a **LGPD**

---

## 📱 Telas do sistema

> 🎨 **Protótipo no Figma:** [Acessar o projeto no Figma](https://www.figma.com/make/FnvCQsR5EpgN7rVIO6MUkh/Self-Service-Car-Rental-App?code-node-id=0-6&p=f&t=8gZEzMsdANiZ9oQ8-0&fullscreen=1)

> 🚧 O projeto está em fase inicial de desenvolvimento. As telas abaixo serão atualizadas conforme o sistema evoluir.

| Tela inicial | Escolha do veículo |
|:---:|:---:|
| <img width="463" height="736" alt="Image" src="https://github.com/user-attachments/assets/54f7d522-9f3a-47a9-ae3b-c74068e0b79f" /> | <img src="docs/screens/02-escolha-veiculo.png" width="280"/> |
| Busca de local, datas e acesso rápido às reservas | Lista de carros disponíveis com preço e categoria |

| Pagamento | Aluguel em andamento |
|:---:|:---:|
| <img src="docs/screens/03-pagamento.png" width="280"/> | <img src="docs/screens/04-aluguel-em-andamento.png" width="280"/> |
| Escolha da forma de pagamento (Pix, cartão ou ApplePay) | Detalhes da locação ativa, prazo e devolução |

---

## 📐 Diagramas UML

Os diagramas abaixo são escritos em **Mermaid** e renderizam automaticamente no GitHub.

### 1. Diagrama de Casos de Uso

```mermaid
flowchart LR
    Cliente([👤 Cliente])
    Admin([🛠️ Administrador])
    Pagto([💳 Gateway de Pagamento])

    subgraph Sistema["Sistema OneCar"]
        UC1(Cadastrar-se)
        UC2(Fazer login)
        UC3(Validar CNH)
        UC4(Buscar veículos)
        UC5(Simular preço)
        UC6(Realizar reserva)
        UC7(Efetuar pagamento)
        UC8(Retirar veículo via QR Code)
        UC9(Devolver veículo)
        UC10(Cancelar reserva)
        UC11(Avaliar serviço)
        UC12(Gerenciar frota)
        UC13(Gerenciar locais)
        UC14(Gerar relatórios)
        UC15(Aprovar documentos)
    end

    Cliente --> UC1
    Cliente --> UC2
    Cliente --> UC3
    Cliente --> UC4
    Cliente --> UC5
    Cliente --> UC6
    Cliente --> UC7
    Cliente --> UC8
    Cliente --> UC9
    Cliente --> UC10
    Cliente --> UC11

    Admin --> UC12
    Admin --> UC13
    Admin --> UC14
    Admin --> UC15

    UC7 --> Pagto
```

### 2. Diagrama de Classes

```mermaid
classDiagram
    class Usuario {
        +int id
        +String nome
        +String email
        +String cpf
        +String telefone
        +String senhaHash
        +Date dataCadastro
        +login()
        +atualizarPerfil()
    }

    class Cliente {
        +String cnh
        +Date validadeCnh
        +boolean documentoValidado
        +fazerReserva()
        +cancelarReserva()
    }

    class Administrador {
        +String cargo
        +gerenciarFrota()
        +gerarRelatorio()
    }

    class Veiculo {
        +int id
        +String placa
        +String marca
        +String modelo
        +int ano
        +String cor
        +String cambio
        +String combustivel
        +int lugares
        +StatusVeiculo status
        +verificarDisponibilidade()
    }

    class Categoria {
        +int id
        +String nome
        +double valorDiaria
    }

    class Local {
        +int id
        +String nome
        +String endereco
        +String cidade
        +double latitude
        +double longitude
    }

    class Reserva {
        +int id
        +Date dataRetirada
        +Date dataDevolucao
        +double valorTotal
        +StatusReserva status
        +calcularValor()
        +cancelar()
        +confirmar()
    }

    class Pagamento {
        +int id
        +double valor
        +FormaPagamento forma
        +StatusPagamento status
        +Date dataPagamento
        +processar()
        +estornar()
    }

    class Vistoria {
        +int id
        +TipoVistoria tipo
        +String observacoes
        +List~String~ fotos
        +Date data
    }

    class Avaliacao {
        +int id
        +int nota
        +String comentario
    }

    class Adicional {
        +int id
        +String descricao
        +double valorDiario
    }

    Usuario <|-- Cliente
    Usuario <|-- Administrador
    Cliente "1" --> "0..*" Reserva : realiza
    Reserva "1" --> "1" Veiculo : reserva
    Reserva "1" --> "1" Pagamento : possui
    Reserva "1" --> "2" Vistoria : retirada e devolução
    Reserva "1" --> "0..1" Avaliacao : gera
    Reserva "0..*" --> "0..*" Adicional : inclui
    Reserva "0..*" --> "1" Local : retirada
    Reserva "0..*" --> "1" Local : devolução
    Veiculo "0..*" --> "1" Categoria : pertence
    Veiculo "0..*" --> "1" Local : localizado em
    Administrador "1" --> "0..*" Veiculo : gerencia
```

### 3. Diagrama de Sequência — Reserva e Retirada

```mermaid
sequenceDiagram
    actor C as Cliente
    participant App as Front-end (React)
    participant API as API Backend
    participant DB as SQL Server
    participant PG as Gateway de Pagamento

    C->>App: Seleciona local, datas e carro
    App->>API: GET /veiculos/disponiveis
    API->>DB: Consulta disponibilidade
    DB-->>API: Lista de veículos
    API-->>App: Veículos e preços
    C->>App: Confirma reserva
    App->>API: POST /reservas
    API->>DB: Cria reserva (pendente)
    API->>PG: Solicita cobrança
    PG-->>API: Pagamento aprovado
    API->>DB: Atualiza reserva (confirmada)
    API-->>App: Reserva confirmada + QR Code
    App-->>C: Exibe comprovante

    Note over C,App: Dia da retirada
    C->>App: Apresenta QR Code no local
    App->>API: POST /retiradas/validar
    API->>DB: Valida reserva e documentos
    API-->>App: Veículo liberado
    App-->>C: Chave digital ativada
```

### 4. Diagrama de Atividades — Fluxo de Locação

```mermaid
flowchart TD
    A([Início]) --> B[Abrir aplicativo]
    B --> C{Possui conta?}
    C -- Não --> D[Realizar cadastro]
    D --> E[Enviar CNH e selfie]
    E --> F{Documentos aprovados?}
    F -- Não --> E
    F -- Sim --> G
    C -- Sim --> G[Escolher local e período]
    G --> H[Selecionar veículo]
    H --> I[Escolher adicionais]
    I --> J[Escolher forma de pagamento]
    J --> K{Pagamento aprovado?}
    K -- Não --> J
    K -- Sim --> L[Receber QR Code]
    L --> M[Ir ao local de retirada]
    M --> N[Realizar vistoria inicial]
    N --> O[Retirar veículo]
    O --> P[Utilizar veículo]
    P --> Q[Devolver no local combinado]
    Q --> R[Vistoria final]
    R --> S[Avaliar serviço]
    S --> T([Fim])
```

### 5. Diagrama de Estados — Reserva

```mermaid
stateDiagram-v2
    [*] --> Pendente
    Pendente --> Confirmada : Pagamento aprovado
    Pendente --> Cancelada : Pagamento recusado / expirou
    Confirmada --> EmAndamento : Retirada realizada
    Confirmada --> Cancelada : Cancelamento pelo cliente
    EmAndamento --> Finalizada : Veículo devolvido
    EmAndamento --> EmAndamento : Prorrogação
    Finalizada --> [*]
    Cancelada --> [*]
```

### 6. Diagrama Entidade-Relacionamento (DER)

```mermaid
erDiagram
    USUARIO ||--o{ RESERVA : realiza
    VEICULO ||--o{ RESERVA : "é reservado em"
    CATEGORIA ||--o{ VEICULO : classifica
    LOCAL ||--o{ VEICULO : abriga
    LOCAL ||--o{ RESERVA : "retirada/devolução"
    RESERVA ||--|| PAGAMENTO : possui
    RESERVA ||--o{ VISTORIA : tem
    RESERVA ||--o| AVALIACAO : recebe
    RESERVA }o--o{ ADICIONAL : inclui

    USUARIO {
        int id PK
        string nome
        string email
        string cpf
        string cnh
        date validade_cnh
    }
    VEICULO {
        int id PK
        string placa
        string marca
        string modelo
        int ano
        string status
    }
    CATEGORIA {
        int id PK
        string nome
        decimal valor_diaria
    }
    LOCAL {
        int id PK
        string nome
        string endereco
        string cidade
    }
    RESERVA {
        int id PK
        datetime data_retirada
        datetime data_devolucao
        decimal valor_total
        string status
    }
    PAGAMENTO {
        int id PK
        decimal valor
        string forma
        string status
    }
    VISTORIA {
        int id PK
        string tipo
        string observacoes
    }
    AVALIACAO {
        int id PK
        int nota
        string comentario
    }
    ADICIONAL {
        int id PK
        string descricao
        decimal valor_diario
    }
```

### 7. Diagrama de Componentes

```mermaid
flowchart TB
    subgraph Front["Camada de Apresentação"]
        WEB[🌐 Front-end<br/>HTML + React]
        ADM[💻 Painel Admin<br/>React]
    end

    subgraph Backend["Camada de Aplicação (C# / ASP.NET Core)"]
        CTRL[Controllers]
        AUTH[Autenticação JWT]
        RES[Serviço de Reservas]
        FROTA[Serviço de Frota]
        PAG[Serviço de Pagamentos]
        REPO[Repositories / EF Core]
    end

    subgraph Dados["Camada de Dados"]
        SQL[(SQL Server)]
    end

    subgraph Externos["Serviços Externos"]
        GATE[Gateway de Pagamento]
        MAPS[Google Maps API]
        MAIL[Serviço de E-mail]
    end

    WEB --> CTRL
    ADM --> CTRL
    CTRL --> AUTH
    CTRL --> RES
    CTRL --> FROTA
    CTRL --> PAG
    RES --> REPO
    FROTA --> REPO
    PAG --> REPO
    REPO --> SQL
    PAG --> GATE
    RES --> MAIL
    WEB --> MAPS
```

---

## 🛠️ Stack de tecnologia

### Front-end
| Tecnologia | Uso |
|---|---|
| **HTML5** | Estrutura das páginas |
| **CSS3** | Estilização e responsividade |
| **JavaScript** | Interações e regras de interface |
| **React** | Componentes e telas (código gerado a partir do Figma) |
| **Figma** | Protótipos, design system e geração das telas |
| **Axios / Fetch API** | Consumo da API |

### Back-end
| Tecnologia | Uso |
|---|---|
| **C#** | Linguagem principal do servidor |
| **.NET / ASP.NET Core Web API** | API REST |
| **Entity Framework Core** | ORM e acesso ao banco de dados |
| **JWT** | Autenticação e autorização |
| **BCrypt** | Criptografia de senhas |
| **Swagger (Swashbuckle)** | Documentação da API |
| **xUnit** + **Moq** | Testes automatizados |

### Banco de dados
| Tecnologia | Uso |
|---|---|
| **Microsoft SQL Server** | Banco de dados relacional |
| **SQL Server Management Studio (SSMS)** | Administração e consultas |
| **EF Core Migrations** | Versionamento do banco |

### Infraestrutura e ferramentas
| Tecnologia | Uso |
|---|---|
| **Docker** + **Docker Compose** | Containerização |
| **GitHub Actions** | CI/CD |
| **Git / GitHub** | Versionamento de código |
| **Visual Studio / VS Code** | Ambiente de desenvolvimento |

### Integrações
- 💳 **Gateway de pagamento** (Pix, cartão e boleto)
- 🗺️ **Google Maps API** — localização e rotas
- ✉️ **Serviço de e-mail (SMTP / SendGrid)** — e-mails transacionais

### Design e documentação
- 🎨 **Figma** — protótipos e design system
- 📐 **Mermaid** — diagramas UML

---

## 🏗️ Arquitetura

O sistema segue uma arquitetura em camadas (**Controller → Service → Repository**), com uma API REST em C# consumida pelo front-end web (HTML e React).

```
┌───────────────────────────┐
│  Front-end (HTML + React) │
└─────────────┬─────────────┘
              ▼
      ┌───────────────┐
      │  API REST C#  │
      │ (ASP.NET Core)│
      └───────┬───────┘
              ▼
      ┌───────────────┐
      │  SQL Server   │
      └───────────────┘
```

---

## 📂 Estrutura de pastas

```
onecar/
├── 📁 frontend/              # HTML + React (gerado do Figma)
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   └── styles/
│   └── package.json
├── 📁 backend/               # API em C# (.NET)
│   ├── OneCar.API/           # Controllers, Program.cs
│   ├── OneCar.Application/   # Services e regras de negócio
│   ├── OneCar.Domain/        # Entidades e interfaces
│   ├── OneCar.Infrastructure/# EF Core, repositórios, migrations
│   ├── OneCar.Tests/         # Testes com xUnit
│   └── OneCar.sln
├── 📁 database/              # Scripts SQL (criação e seed)
├── 📁 docs/
│   ├── screens/              # Prints das telas
│   └── uml/                  # Diagramas
├── 📄 docker-compose.yml
├── 📄 LICENSE
└── 📄 README.md
```

---

## 🚀 Como executar
ATENÇÃO AREA EM DESENVOLVIMENTO
### Pré-requisitos

- [.NET SDK](https://dotnet.microsoft.com/download) 8.0 ou superior
- [SQL Server](https://www.microsoft.com/sql-server) (local, Express ou via Docker)
- [Node.js](https://nodejs.org/) 18 ou superior (para o front-end React)
- [Git](https://git-scm.com/)
- Opcional: [Docker](https://www.docker.com/)

### Passo a passo

```bash
# 1. Clone o repositório
git clone https://github.com/seu-usuario/onecar.git
cd onecar

# 2. (Opcional) Suba o SQL Server com Docker
docker-compose up -d

# 3. Configure a string de conexão em backend/OneCar.API/appsettings.json

# 4. Rode o back-end
cd backend
dotnet restore
dotnet ef database update --project OneCar.Infrastructure --startup-project OneCar.API
dotnet run --project OneCar.API

# 5. Em outro terminal, rode o front-end
cd frontend
npm install
npm start
```

A API estará disponível em `https://localhost:5001` e a documentação Swagger em `https://localhost:5001/swagger`.

---

## 🔐 Configuração (appsettings.json)

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost,1433;Database=OneCar;User Id=sa;Password=SuaSenhaForte123;TrustServerCertificate=True"
  },
  "Jwt": {
    "Key": "sua_chave_secreta_com_32_caracteres_ou_mais",
    "Issuer": "OneCar",
    "Audience": "OneCarUsers",
    "ExpiresInMinutes": 60
  },
  "Payment": {
    "ApiKey": "sua_chave_do_gateway"
  },
  "GoogleMaps": {
    "ApiKey": "sua_chave_do_google"
  },
  "Email": {
    "Smtp": "smtp.exemplo.com",
    "User": "contato@onecar.com",
    "Password": "sua_senha"
  }
}
```

> ⚠️ Nunca suba chaves e senhas reais para o GitHub. Use *User Secrets* ou variáveis de ambiente.

---

## 📡 Documentação da API

### Principais endpoints

| Método | Rota | Descrição |
|:---:|---|---|
| `POST` | `/auth/register` | Cadastro de usuário |
| `POST` | `/auth/login` | Login e geração de token |
| `GET` | `/users/me` | Dados do usuário logado |
| `POST` | `/users/me/documents` | Envio de CNH e selfie |
| `GET` | `/locations` | Lista de locais de retirada |
| `GET` | `/vehicles` | Lista de veículos disponíveis |
| `GET` | `/vehicles/:id` | Detalhes do veículo |
| `POST` | `/reservations/quote` | Simulação de preço |
| `POST` | `/reservations` | Criar reserva |
| `GET` | `/reservations` | Histórico de reservas |
| `PATCH` | `/reservations/:id/cancel` | Cancelar reserva |
| `POST` | `/reservations/:id/pickup` | Validar retirada (QR Code) |
| `POST` | `/reservations/:id/return` | Registrar devolução |
| `POST` | `/payments` | Processar pagamento |
| `POST` | `/reviews` | Avaliar locação |

### Exemplo de requisição

```http
POST /reservations
Authorization: Bearer <token>
Content-Type: application/json

{
  "vehicleId": 12,
  "pickupLocationId": 1,
  "returnLocationId": 1,
  "pickupDate": "2026-11-10T10:00:00Z",
  "returnDate": "2026-11-15T10:00:00Z",
  "paymentMethod": "PIX"
}
```

```json
{
  "id": 481,
  "status": "PENDING",
  "totalAmount": 1250.00,
  "qrCode": "data:image/png;base64,..."
}
```

A documentação completa (Swagger) fica em `/swagger`.

---

## 🧪 Testes

```bash
# Executar todos os testes (xUnit)
dotnet test

# Com cobertura
dotnet test --collect:"XPlat Code Coverage"
```

---

## 🗺️ Roadmap

- [x] Cadastro e autenticação de usuários
- [x] Busca e filtro de veículos
- [x] Reserva e pagamento
- [x] Retirada por QR Code
- [x] Painel administrativo
- [ ] Chave digital via Bluetooth
- [ ] Programa de fidelidade e pontos
- [ ] Assinatura mensal de veículos
- [ ] Suporte a carros elétricos
- [ ] Chat de suporte dentro do app
- [ ] Aplicativo mobile nativo
- [ ] Versão em inglês e espanhol

---

## 🤝 Como contribuir

Contribuições são muito bem-vindas!

1. Faça um **fork** do projeto
2. Crie uma branch para a sua feature (`git checkout -b feature/minha-feature`)
3. Faça o commit das alterações (`git commit -m 'feat: adiciona minha feature'`)
4. Envie para a branch (`git push origin feature/minha-feature`)
5. Abra um **Pull Request**

Seguimos o padrão [Conventional Commits](https://www.conventionalcommits.org/pt-br/).

---

## 👥 Equipe

| Nome | Função | GitHub |
|---|---|---|
| Rafael | Desenvolvedor Full Stack | [@rafael](https://github.com/Rafael-santiago-silva) |
| Rafael | UI/UX Designer | [@rafael](https://github.com/Rafael-santiago-silva) |
| Rafael | Back-end | [@rafael](https://github.com/Rafael-santiago-silva) |

---

---

<div align="center">

Feito com 💙 por **Equipe OneCar**

⭐ Se este projeto te ajudou, deixe uma estrela!

</div>
