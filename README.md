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

Cada entrega será realizada a partir da criação de uma **tag** em cada repositório (Front, Back), além da criação de uma branch no repositório da documentação com um relatório completo de tudo o que foi desenvolvido naquela sprint. Observe a relação a seguir:
| Sprint | Período | Meta | Status |
|:--:|:----------:|:-----------------------------------|:-----------:|
| 01 | 16/03 a 05/04 | Fundação, dados SICAR e mapa — Buscar propriedade CAR e ver polígono no mapa | 🚧 Em andamento |
| 02 | 13/04 a 03/05 | Cruzamento de dados e análise ASG — Indicadores ASG com fontes rastreáveis e relatório básico | 🕐 Aguardando |
| 03 | 11/05 a 31/05 | PLN, busca semântica e polimento — Usuário faz perguntas em linguagem natural e recebe respostas com fontes | 🕐 Aguardando |

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
| 11 | Alta | Como analista, quero que o sistema processe perguntas em linguagem natural e identifique a propriedade consultada e o tipo de análise. | 8 | 3 |
| 12 | Alta | Como analista, quero uma interface onde digito perguntas em texto livre e recebo respostas com dados relevantes e fontes citadas. | 8 | 3 |
| 13 | Alta | Como analista, quero que o sistema interprete a intenção da pergunta e chame o microsserviço adequado, retornando resposta consolidada. | 8 | 3 |
| 14 | Média | Como analista, quero que a resposta ou relatório inclua visualização da área de interesse com imagens de satélite. | 5 | 3 |
| 15 | Média | Como usuário, quero respostas entre 1 e 10 segundos, testes de integração, ajustes de UX e documentação da API. | 8 | 3 |

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
