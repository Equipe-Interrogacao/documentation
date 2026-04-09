<p align="center">
      <img src="./img/logo.png" alt="logo" width="150">
<hr>

<span id="topo">
<p align="center">
    <a href="#sobre">Sobre</a>  |
    <a href="#backlogs">Backlogs, Épicos & User Stories</a>  |
    <a href="#tecnologias">Tecnologias</a>  |
    <a href="#equipe">Equipe</a> |
    <a href="#links">Links úteis</a>
</p>

<span id="sobre">

## :bookmark_tabs: Sobre o projeto

Sistema ASG (Ambiental, Social e Governança) para análise de propriedades rurais no estado de São Paulo, utilizando dados públicos geoespaciais e permitindo consultas inteligentes via mapa e linguagem natural.

O objetivo principal é apoiar governo e usuários na tomada de decisão, fiscalização e análise de risco ambiental, com respostas rápidas, visuais e rastreáveis.

### :warning: Problema

> _Dificuldade de fiscalização e análise de risco ambiental em propriedades rurais, com dados dispersos em múltiplas fontes públicas, ausência de cruzamento automatizado de informações geoespaciais e falta de uma interface unificada para consultas e tomada de decisão._

### :white_check_mark: Proposta de Solução

> _Uma plataforma inteligente de análise territorial que integra dados geoespaciais públicos (SICAR, INPE, ICMBio, FUNAI, INCRA, FCP), aplica cruzamentos ASG e permite exploração visual via mapa interativo combinada com consultas em linguagem natural. O sistema entrega insights claros, rápidos e auditáveis para análise ambiental e regulatória de propriedades rurais._

:pushpin: Status do Projeto: **🚧 Em andamento**

### 🏁 Entregas de Sprints

Cada entrega será realizada a partir da criação de uma **tag** em cada repositório (Front, Back), além da criação de uma branch no repositório da documentação com um relatório completo de tudo o que foi desenvolvido naquela sprint.

| Sprint | Período | Meta | Status |
|:--:|:----------:|:-----------------------------------|:-----------:|
| 01 | 16/03 a 05/04 | Fundação, dados SICAR e mapa — Buscar propriedade CAR e ver polígono no mapa | Concluído |
| 02 | 13/04 a 03/05 | Cruzamento de dados, análise ASG e PLN básico — Indicadores ASG com fontes rastreáveis, relatório básico e chatbot com linguagem natural simples | 🚧 Em andamento |
| 03 | 11/05 a 31/05 | Busca semântica avançada e polimento — Consultas complexas em linguagem natural, imagens de satélite e refinamento geral | 🕐 Aguardando |

→ [Voltar ao topo](#topo)

<span id="backlogs">

## :dart: Backlogs, Épicos & User Stories

### Product Backlog (MVP — 3 sprints)

| Rank | Prioridade | User Story | Estimativa | Sprint |
|------|------------|------------|------------|--------|
| 1 | Alta | Como operador, quero uma arquitetura base em microsserviços (Python, Docker Compose, variáveis de ambiente) configurável sem alterar código. | 8 | 1 |
| 2 | Alta | Como analista, quero que os dados do SICAR-SP (shapefiles, geometrias e atributos) sejam ingeridos e processados para basear análises ASG. | 8 | 1 |
| 3 | Alta | Como analista, quero uma API de busca por código CAR que retorne dados básicos e GeoJSON do polígono, com fonte rastreável (SICAR). | 5 | 1 |
| 4 | Alta | Como analista, quero uma tela de busca por código CAR onde vejo os dados básicos e o polígono renderizado no mapa. | 8 | 1 |
| 5 | Média | Como desenvolvedor, quero pipeline de CI/CD, testes e documentação inicial para garantir qualidade e deploy. | 5 | 1 |
| 6 | Alta | Como analista, quero dados de desmatamento e queimadas do INPE (PRODES, DETER, Queimadas) filtrados para SP para análises ambientais. | 8 | 2 |
| 7 | Alta | Como analista, quero cruzar o polígono do CAR com alertas do INPE para identificar passivos ambientais, com fonte e data do dado. | 8 | 2 |
| 8 | Alta | Como analista, quero dados de UCs, Terras Indígenas, Assentamentos e Quilombolas para verificar sobreposição com áreas protegidas. | 8 | 2 |
| 9 | Alta | Como gestor, quero um relatório ASG consolidado com indicadores e fontes de cada dado, compatível com OGC/QGIS. | 8 | 2 |
| 10 | Alta | Como analista, quero visualizar camadas no mapa e um painel lateral com resumo dos indicadores ASG. | 7 | 2 |
| 11 | Alta | Como administrador, quero um botão protegido por login e senha que abra um modal de atualização dos bancos de dados, onde o sistema verifica via endpoint se há dados novos nas APIs públicas (comparando contagem de registros ou versão) antes de disparar as APIs de ingestão, evitando reprocessamento desnecessário. | 8 | 2 |
| 12 | Alta | Como analista, quero digitar perguntas simples em linguagem natural (ex.: "tem desmatamento nessa área?") e receber uma resposta clara com os dados relevantes — o sistema deve identificar palavras-chave (PLN simples) para direcionar a consulta ao microsserviço correto. | 8 | 2 |
| 13 | Alta | Como analista, quero uma interface onde digito perguntas em texto livre e recebo respostas com dados relevantes e fontes citadas. | 8 | 3 |
| 14 | Alta | Como analista, quero que o sistema interprete a intenção da pergunta e chame o microsserviço adequado, retornando resposta consolidada. | 8 | 3 |
| 15 | Média | Como analista, quero que a resposta ou relatório inclua visualização da área de interesse com imagens de satélite. | 5 | 3 |
| 16 | Média | Como usuário, quero respostas entre 1 e 10 segundos, testes de integração, ajustes de UX e documentação da API. | 8 | 3 |

---

### 🗂️ Sprint 1 — Fundação, dados SICAR e mapa
**Período:** 16/03 a 05/04
**Meta:** Buscar propriedade CAR e ver polígono no mapa

#### Tópicos

**1. Infraestrutura & Arquitetura Base**
- Configuração do ambiente com Docker Compose e microsserviços Python
- Variáveis de ambiente centralizadas — sistema configurável sem alterar código
- Pipeline de CI/CD, testes automatizados e documentação inicial

**2. Ingestão de Dados SICAR-SP**
- Download e processamento dos shapefiles do SICAR para São Paulo
- Armazenamento de geometrias e atributos no banco PostGIS
- Fonte de dados rastreável vinculada a cada registro

**3. API de Busca por CAR**
- Endpoint de busca por código CAR retornando dados básicos e GeoJSON do polígono
- Fonte SICAR identificada e retornada junto com a resposta

**4. Interface — Tela de Busca e Mapa**
- Tela de busca por código CAR
- Renderização do polígono da propriedade no mapa interativo
- Exibição dos dados básicos ao lado do mapa

---

### 🗂️ Sprint 2 — Cruzamento de dados, análise ASG e PLN básico
**Período:** 13/04 a 03/05
**Meta:** Indicadores ASG com fontes rastreáveis, relatório básico e chatbot com linguagem natural simples

#### Tópicos

**1. Ingestão de Dados Ambientais (INPE)**
- Ingestão de dados de desmatamento (PRODES) e alertas (DETER) filtrados para SP
- Ingestão de dados de queimadas do INPE para SP
- Data e fonte de cada dado preservados para rastreabilidade

**2. Ingestão de Dados Socioambientais (ICMBio / FUNAI / INCRA / FCP)**
- Unidades de Conservação (UCs) do ICMBio
- Terras Indígenas (FUNAI) e Assentamentos (INCRA)
- Territórios Quilombolas (FCP)

**3. Cruzamento ASG e Análise**
- Cruzamento do polígono CAR com alertas INPE para identificar passivos ambientais
- Verificação de sobreposição com áreas protegidas (UCs, TIs, assentamentos, quilombolas)
- Indicadores ASG calculados com data e fonte de cada dado

**4. Relatório ASG e Visualização no Mapa**
- Relatório consolidado com indicadores e fontes, compatível com OGC/QGIS
- Camadas temáticas sobrepostas no mapa interativo
- Painel lateral com resumo dos indicadores ASG

**5. Painel de Atualização de Dados (Admin)**
- Botão protegido por login e senha na interface administrativa
- Modal de atualização: lista todos os bancos de dados disponíveis
- Verificação prévia via endpoint: compara contagem de registros ou versão/hash da API pública antes de acionar a ingestão
- Disparo seletivo das APIs de ingestão apenas onde há dados novos ou divergência detectada
- Log de resultado por fonte (atualizado / sem alteração / erro)

**6. Chatbot PLN Simples**
- Campo de texto livre para o usuário digitar perguntas simples (ex.: "tem desmatamento nessa área?", "essa propriedade tem sobreposição com terra indígena?")
- Processamento por PLN simples: extração de palavras-chave para identificar a propriedade consultada e o tipo de análise solicitada
- Roteamento da pergunta ao microsserviço adequado com retorno de resposta clara e com fonte citada

---

### 🗂️ Sprint 3 — Busca semântica avançada e polimento
**Período:** 11/05 a 31/05
**Meta:** Consultas complexas em linguagem natural, imagens de satélite e refinamento geral

#### Tópicos

**1. PLN Avançado e Busca Semântica**
- Interpretação de intenção em perguntas complexas e ambíguas
- Roteamento dinâmico para o microsserviço correto com base na semântica da pergunta
- Resposta consolidada com dados e fontes citadas

**2. Interface de Chat Avançada**
- Interface dedicada para perguntas em texto livre
- Respostas estruturadas com dados relevantes, fontes e links para as camadas no mapa
- Histórico de consultas na sessão

**3. Visualização com Imagens de Satélite**
- Exibição de imagens de satélite da área de interesse na resposta ou relatório
- Integração com a camada de mapa correspondente

**4. Polimento, Performance e Qualidade**
- Meta de resposta entre 1 e 10 segundos para consultas comuns
- Testes de integração end-to-end
- Ajustes de UX e acessibilidade
- Documentação completa da API (OpenAPI/Swagger)

---

→ [Voltar ao topo](#topo)

<span id="tecnologias">

## 🛠️ Tecnologias

Linguagens, bibliotecas e tecnologias usadas na construção do projeto:

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
<img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
<img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React" />
<img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite" />
<img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL" />
<img src="https://img.shields.io/badge/PostGIS-008BB9?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostGIS" />
<img src="https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white" alt="Nginx" />
<img src="https://img.shields.io/badge/Google%20Maps-4285F4?style=for-the-badge&logo=google-maps&logoColor=white" alt="Google Maps" />
<img src="https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white" alt="VSCode" />
<img src="https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
<img src="https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white" alt="Postman" />
<img src="https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white" alt="Figma" />

→ [Voltar ao topo](#topo)

<span id="equipe">

## :busts_in_silhouette: Equipe

|    Função     | Nome                           |                                                                                                                                                      LinkedIn & GitHub                                                                                                                                                      |
| :-----------: | :----------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Product Owner | Jonas Ribeiro  | [![Linkedin Badge](https://img.shields.io/badge/Linkedin-blue?style=flat-square&logo=Linkedin&logoColor=white)](https://www.linkedin.com/in/jonasrsribeiro/) [![GitHub Badge](https://img.shields.io/badge/GitHub-111217?style=flat-square&logo=github&logoColor=white)](https://github.com/jonasrsribeiro) |
| Scrum Master  | Bruno Fernando                | [![Linkedin Badge](https://img.shields.io/badge/Linkedin-blue?style=flat-square&logo=Linkedin&logoColor=white)](https://www.linkedin.com/in/bruno-campos-97560b231?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app) [![GitHub Badge](https://img.shields.io/badge/GitHub-111217?style=flat-square&logo=github&logoColor=white)](https://github.com/BrunoFerCam) |
| Dev Team      | Erika Dias Ribeiro             | [![Linkedin Badge](https://img.shields.io/badge/Linkedin-blue?style=flat-square&logo=Linkedin&logoColor=white)](https://www.linkedin.com/in/erika-dias-608359266/) [![GitHub Badge](https://img.shields.io/badge/GitHub-111217?style=flat-square&logo=github&logoColor=white)](https://github.com/ErikaDias2) |
| Dev Team      | Diogo Palharini                | [![GitHub Badge](https://img.shields.io/badge/GitHub-111217?style=flat-square&logo=github&logoColor=white)](https://github.com/DiogoPalharini) |

→ [Voltar ao topo](#topo)

<span id="links">

## :link: Links úteis

- Repositório Frontend: https://github.com/Equipe-Interrogacao/frontend
- Repositório Backend: https://github.com/Equipe-Interrogacao/backend

   <br>

  → [Voltar ao topo](#topo)
