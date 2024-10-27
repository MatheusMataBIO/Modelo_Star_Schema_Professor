## Modelagem Dimensional Star Schema 🎯 

### Stacks Utilizadas 💻
<img src="https://upload.wikimedia.org/wikipedia/en/d/dd/MySQL_logo.svg" alt="MySQL Logo" width="100"/>

### Objetivo 🎯 

Esse projeto tem como objetivo praticar minhas habilidades de lógica e modelagem dimensional utlizando o Workbench do MySQL

### Descrição

Construí uma modelo dimensional do tipo Star Schema (modelo estrela) com o objetivo tendo como professor o objeto de análise.

Para detalhar cada relacionamento entre a tabela fato e as tabelas de dimensão no contexto de um modelo em estrela no MySQL Workbench, vamos considerar a tabela fato Fato_Professor e as tabelas de dimensão Dimensao_Professor, Dimensao_Curso, Dimensao_Departamento e Dimensao_Data. O objetivo é criar relações one-to-many (um-para-muitos) entre a tabela fato e cada tabela de dimensão, onde cada chave estrangeira na tabela fato se relaciona com uma chave primária nas tabelas de dimensão.

### Etapas

### 1. Criando o Projeto e Adicionando um Diagrama

Abra o MySQL Workbench e vá em File > New Model para iniciar um novo modelo.
No menu Model Overview, clique em Add Diagram para criar um diagrama EER (diagrama de relacionamento de entidade).
Um espaço em branco será aberto para o diagrama.


### 2. Tabela Fato: Fato_Professor

A tabela Fato_Professor centraliza as métricas e valores numéricos associados ao professor, incluindo os cursos ministrados, o departamento e outras métricas de interesse, como a carga horária.

Colunas da Tabela Fato:

ID_Professor (Chave estrangeira para Professor)
ID_Curso (Chave estrangeira para Curso)
ID_Departamento (Chave estrangeira para Departamento)
ID_Data (Chave estrangeira para Data)

### 3.  Tabelas Dimensão

**Professor** 

Detalha informações sobre os professores, como dados pessoais e profissionais.

Colunas:

ID_Professor (Chave primária)
Nome_Professor
Titulação (ex.: Doutorado, Mestrado)
Tempo_Carreira

**Curso** 

Contém informações sobre os cursos ministrados pelos professores.

Colunas:

ID_Curso (Chave primária)
Nome_Curso
Tipo_Curso (ex.: Graduação, Pós-Graduação)
Carga_Horaria

**Departamento** 

Descreve os departamentos aos quais os professores estão vinculados.

Colunas:

ID_Departamento (Chave primária)
Nome_Departamento
Faculdade (ex.: Faculdade de Ciências, Faculdade de Letras)

**Data** 

Inclui as datas de ofertas de cursos e disciplinas. 

ID_Data (Chave primária)
Período_Ofertas_Disciplinas 
Data_Ofertas_Cursos
Data_Término_Cursos


### 4. Descrição dos Relacionamentos
Professor -> Fato_Professor: A tabela Fato se conecta à dimensão Professor pelo ID do professor, permitindo analisar métricas específicas de cada professor.
Curso -> Fato_Professor: Cada linha em Fato_Professor pode ser relacionada a um curso específico pelo ID_Curso, ajudando a entender o impacto de cada curso 
Departamento -> Fato_Professor: A relação com Departamento permite avaliar a contribuição de cada departamento 
Data -> Fato_Professor: O relacionamento com Data permite a análise temporal da oferta de cursos 
