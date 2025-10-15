# 🏅 Sistema de Gestão das Olimpíadas (SGO)

> Projeto desenvolvido como parte da disciplina **Projeto de Software** (4º período de Engenharia de Software) – Professor João Paulo Carneiro Aramuni.

O **Sistema de Gestão das Olimpíadas (SGO)** tem como objetivo centralizar e gerenciar as principais atividades das Olimpíadas, como o **cadastro de competições**, **inscrição de atletas**, **alocação de locais**, **registro de resultados** e **geração de relatórios de medalhas**.

---

## 🎯 Objetivos do Sistema

- Permitir o **gerenciamento completo das competições olímpicas**;
- Controlar **inscrições de atletas** e vinculação aos respectivos países;
- Garantir a **disponibilidade e alocação de locais** sem conflitos de horários;
- Registrar **resultados e classificações automáticas**;
- Gerar **relatórios analíticos de desempenho** e **ranking de medalhas** por país.

---

## 📋 Funcionalidades Principais

- **Cadastro de Competições** - Gerenciamento completo de modalidades, datas, horários e locais
- **Inscrição de Atletas** - Sistema de inscrição para atletas de diferentes países
- **Alocação de Locais** - Alocação inteligente evitando conflitos de horário
- **Controle de Resultados** - Registro de vencedores e classificados
- **Relatórios de Medalhas** - Geração de relatórios de desempenho por país

---

## 👥 Atores do Sistema

```mermaid
flowchart TD
    A[Administrador] --> G[Sistema SGO]
    C[Coordenador] --> G
    J[Juiz/Árbitro] --> G
    At[Atleta] --> G
    
    G --> CM[Cadastro Competições]
    G --> IA[Inscrição Atletas]
    G --> AL[Alocação Locais]
    G --> RC[Registro Resultados]
    G --> RM[Relatórios Medalhas]
```

---

## 🧩 Estrutura do Repositório

```
📁 Sistema-Gestao-Olimpiadas/
┣ 📁 imagens/
┃ ┣ diagrama_de_caso_de_uso.jpg
┃ ┣ diagrama_de_classes.jpg
┃ ┣ diagrama_de_pacotes.jpg
┃ ┣ diagrama_de_pacote_simplificado.jpg
┃ ┣ diagrama_de_componentes.jpg
┃ ┗ diagrama_de_implantacao.jpg
┣ 📁 modelagens/
┃ ┣ diagrama_de_caso_de_uso.drawio
┃ ┣ diagrama_de_classes.drawio
┃ ┣ diagrama_de_pacotes.drawio
┃ ┣ diagrama_de_componentes.drawio
┃ ┗ diagrama_de_implantacao.drawio
┗ 📄 README.md
```

---

## 👤 Histórias de Usuário

| ID | História de Usuário | Prioridade |
|----|----------------------|-------------|
| **US01** | Como **administrador**, desejo cadastrar novas competições informando modalidade, data, horário e local, para organizar o cronograma de eventos. | Alta |
| **US02** | Como **atleta**, quero me inscrever em competições específicas, representando meu país, para participar das Olimpíadas. | Alta |
| **US03** | Como **administrador**, desejo alocar locais para competições de modo que não ocorram conflitos de horário. | Alta |
| **US04** | Como **juiz**, quero registrar resultados e classificações, para atualizar o quadro de medalhas automaticamente. | Alta |
| **US05** | Como **coordenador**, quero gerar relatórios de medalhas por país, para analisar o desempenho geral nas Olimpíadas. | Média |

---

## 🧠 Regras de Negócio

1. **Cadastro de Competições:** Cada competição deve conter modalidade, data, local e lista de atletas.  
2. **Inscrição de Atletas:** Um atleta pode participar de várias competições, mas representa **apenas um país** em cada modalidade.  
3. **Alocação de Locais:** Um local só pode sediar **uma competição por vez**.  
4. **Registro de Resultados:** Após a competição, são atribuídas medalhas de **ouro**, **prata** e **bronze**.  
5. **Relatórios de Medalhas:** O sistema gera automaticamente o **ranking por país**.

---

## 🏗️ Diagramas do Sistema

### 1. Diagrama de Caso de Uso

```mermaid
graph TD
  A[Administrador] --> B(Cadastrar Competição)
  A --> C(Alocar Local)
  A --> D(Gerenciar Atletas)
  E[Atleta] --> F(Inscrever-se em Competição)
  G[Juiz] --> H(Registrar Resultados)
  I[Coordenador] --> J(Gerar Relatório de Medalhas)
```

### 2. Diagrama de Classes

```mermaid
classDiagram
    class Competicao {
        +String nomeModalidade
        +Date data
        +Time horario
        +Local local
        +adicionarAtleta()
        +registrarResultado()
    }
    
    class Atleta {
        +String nome
        +String pais
        +List~Competicao~ competicoes
        +inscreverCompeticao()
    }
    
    class Local {
        +String nome
        +String endereco
        +Integer capacidade
        +verificarDisponibilidade()
    }
    
    class Resultado {
        +Atleta primeiroLugar
        +Atleta segundoLugar  
        +Atleta terceiroLugar
        +registrarVencedores()
    }
    
    class Pais {
        +String nome
        +Integer medalhasOuro
        +Integer medalhasPrata
        +Integer medalhasBronze
        +calcularTotalMedalhas()
    }
    
    Competicao "1" -- "*" Atleta
    Competicao "1" -- "1" Local
    Competicao "1" -- "1" Resultado
    Atleta "1" -- "1" Pais
```

### 3. Diagrama de Pacotes

```mermaid
graph LR
  dominio[Pacote Domínio] --> servicos[Pacote Serviços]
  servicos --> relatorios[Pacote Relatórios]
  dominio --> enums[Pacote Enums]
  enums --> servicos
  relatorios --> servicos
```

**Legenda do Diagrama de Pacotes:**
- **domínio**: Entidades do sistema (Competição, Atleta, Local, etc.)
- **serviços**: Regras de negócio
- **relatórios**: Geração de relatórios
- **enums**: Enumerações do sistema

### 4. Diagrama de Componentes

```mermaid
graph TB
    subgraph "Camada de Apresentação"
        UI[Interface Web]
        MI[Interface Mobile]
        DA[Dashboard Admin]
    end
    
    subgraph "Camada de Aplicação"
        MC[Módulo Competições]
        MI2[Módulo Inscrições]
        MA[Módulo Alocação]
        MR[Módulo Resultados]
        MREL[Módulo Relatórios]
    end
    
    subgraph "Camada de Domínio"
        A[Atleta]
        C[Competição]
        L[Local]
        R[Resultado]
        P[País]
    end
    
    subgraph "Infraestrutura"
        DB[(Banco de Dados)]
        API[API Gateway]
        AUTH[Autenticação]
    end
    
    UI --> MC
    UI --> MI2
    UI --> MA
    UI --> MR
    UI --> MREL
    
    MC --> C
    MI2 --> A
    MA --> L
    MR --> R
    MREL --> P
    
    C --> DB
    A --> DB
    L --> DB
    R --> DB
    P --> DB
```

### 5. Diagrama de Implantação

```mermaid
flowchart TB
    subgraph USUARIOS [Dispositivos dos Usuários]
        LA[Laptop Admin]
        TJ[Tablet Juiz]
        MA[Mobile Atleta]
        PC[PC COI]
    end
    
    subgraph DMZ [Zona Desmilitarizada]
        FW1[Firewall 1]
        LB[Load Balancer]
        WS1[Web Server 1]
        WS2[Web Server 2]
    end
    
    subgraph APP [Camada de Aplicação]
        FW2[Firewall 2]
        AS1[App Server 1]
        AS2[App Server 2]
        AS3[App Server 3]
    end
    
    subgraph DATA [Camada de Dados]
        FW3[Firewall 3]
        DB1[(DB Principal)]
        DB2[(DB Logs)]
        DB3[(DB Réplica)]
        BS[Backup Storage]
    end
    
    subgraph EXT [Sistemas Externos]
        CS[Cloud Services]
        ST[Sistema Timing]
        SCOI[Sistema COI]
    end
    
    USUARIOS --> DMZ
    DMZ --> APP
    APP --> DATA
    APP --> EXT
```

---

## 🛠️ Tecnologias Recomendadas

- **Backend:** Java Spring Boot ou Node.js
- **Frontend:** React ou Angular
- **Banco de Dados:** PostgreSQL ou MySQL
- **Infraestrutura:** Docker, AWS/Azure
- **Documentação:** Swagger para APIs

---

## 📝 Regras de Negócio Implementadas

✅ **Cadastro de Competições** - O sistema permite cadastro completo com nome da modalidade, data, horário, local e lista de atletas inscritos  
✅ **Inscrição de Atletas** - Atletas podem se inscrever em várias competições, mas só representam um país por modalidade  
✅ **Alocação de Locais** - Locais são alocados evitando conflitos de horário (um local por competição por vez)  
✅ **Controle de Resultados** - Registro completo de vencedores (1º, 2º e 3º lugares)  
✅ **Relatórios de Medalhas** - Geração automática de relatórios de desempenho por país  

---

## 💡 Diferenciais do Projeto

✅ **Completude UML:** Contém **todos os 5 diagramas obrigatórios** (caso de uso, classes, pacotes, componentes e implantação)  
✅ **Organização Modular:** Uso de pacotes bem definidos (`domínio`, `serviços`, `relatórios`, `enums`)  
✅ **Diagrama de Pacotes Simplificado** adicional para melhor legibilidade  
✅ **Consistência entre camadas** (interface, serviços, domínio e persistência)  
✅ **Diagrama de Implantação** realista, com redundância de servidores, cache e backup  
✅ **README documentado e visual**, com **mini diagramas Mermaid** integrados  
✅ **Arquitetura em 3 camadas** bem definida (Apresentação, Aplicação, Dados)  
✅ **Integração com sistemas externos** (Sistema Timing, Sistema COI)  

---

## 🧾 Autores

**👨‍💻 Paulo Henrique Fonseca de Assis**  
**👨‍💻 Áulus Arcanjo Alves Batista**  
Estudantes de Engenharia de Software – 4º Período  
📍 Desenvolvido para a disciplina de **Projeto de Software** - PUC Minas

---
