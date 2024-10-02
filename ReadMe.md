Projeto de Modelagem Dimensional: Professores

Objetivo do Projeto

O objetivo deste projeto é criar um diagrama dimensional (star schema) com foco na análise de dados dos professores. O diagrama relacional disponibilizado foi utilizado como base para a criação do esquema em estrela, com tabelas fato e dimensões estruturadas para otimizar consultas e análises.

Objeto de Análise

O foco principal da análise são os professores. A tabela fato foi construída para refletir os dados dos professores, como cursos ministrados e departamento ao qual pertencem. O projeto não contempla informações sobre alunos, concentrando-se apenas nas atividades e dados relacionados aos docentes.

Estrutura do Projeto

1. Tabela Fato: fato_professores
A tabela fato centraliza as métricas e eventos relacionados aos professores, sendo composta por chaves estrangeiras que referenciam as tabelas de dimensão.

Colunas principais:

id_professor: Identificador do professor
id_curso: Identificador do curso ministrado
id_departamento: Identificador do departamento
id_data: Identificador da data associada ao evento (oferta de curso, etc.)
carga_horaria_total: Total de carga horária ministrada pelo professor
num_cursos_ministrados: Número de cursos ministrados
salario: Salário do professor
avaliacao_desempenho: Avaliação de desempenho atribuída ao professor

2. Tabelas Dimensão
As tabelas dimensão fornecem detalhes adicionais relacionados ao professor, cursos, departamentos e datas.

Dimensão Professores (dimensao_professores): Contém informações detalhadas sobre cada professor, como nome, especialização, titulação e anos de experiência.

Dimensão Cursos (dimensao_cursos): Contém dados sobre os cursos ministrados, incluindo o nome do curso, tipo (graduação, pós-graduação) e carga horária.

Dimensão Departamentos (dimensao_departamentos): Contém informações sobre os departamentos e áreas de conhecimento a que os professores pertencem.

Dimensão Datas (dimensao_datas): Permite análises temporais, com informações como data completa, ano, mês, trimestre e dia da semana.

3. Dimensão de Datas
Uma tabela especial de datas foi criada para compensar a falta de dados de datas no diagrama relacional original. Essa dimensão permite análises detalhadas ao longo do tempo, como a data de oferta dos cursos ou disciplinas.

Campos principais:

id_data: Identificador único da data (YYYYMMDD)
data_completa: Data completa
ano: Ano do evento
mes: Mês do evento
trimestre: Trimestre do ano
dia_da_semana: Dia da semana correspondente
4. Relacionamento entre as Tabelas
O esquema em estrela foi desenhado de modo que a tabela fato se relacione diretamente com cada uma das dimensões através de chaves estrangeiras. Isso permite uma análise eficiente e rápida, focada no desempenho dos professores e suas atividades.

5. Granularidade
A granularidade das informações pode variar de acordo com a necessidade de análise. Por exemplo, para a dimensão de datas, a granularidade pode ser diária, semanal ou mensal, conforme o nível de detalhe requerido nas consultas.

O que foi feito
Criação da tabela fato: A tabela fato foi projetada para conter os principais dados de interesse para análise do desempenho dos professores.
Criação das tabelas de dimensão: Dimensões para professor, curso, departamento e datas foram criadas para detalhar os atributos necessários para a análise.
Inclusão da tabela de datas: Mesmo que os dados de datas não estivessem inicialmente presentes no diagrama relacional, uma tabela de datas foi criada com base em suposições.
Próximos Passos
Carregar Dados: Dados reais ou simulados devem ser carregados nas tabelas.
Consultas e Relatórios: A partir do modelo dimensional criado, poderão ser geradas consultas para extrair insights sobre os professores, tais como:
Carga horária total por departamento
Avaliação média de desempenho por curso
Análise temporal de cursos ministrados
Conclusão
Este projeto de modelagem dimensional permite uma análise robusta dos dados dos professores, fornecendo uma estrutura eficiente para a geração de relatórios e insights. Com o diagrama em estrela, o desempenho de consultas complexas sobre grandes volumes de dados será otimizado, facilitando a tomada de decisão.