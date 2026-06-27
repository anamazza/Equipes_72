Equipes_72 — Composição das equipes eMulti (CNES)
Painel sobre a composição profissional das equipes Multiprofissionais (eMulti, tipo de equipe 72) no Brasil, a partir da Base de Dados do CNES, competência 05/2026.
Painel online
`https://anamazza.github.io/Equipes_72/`
Arquivo HTML único, com os dados embutidos. Traz indicadores gerais, filtros encadeados de região, UF e município, um mapa de calor por UF (clicar num estado filtra o painel), gráficos com rótulos fixos e botões para baixar os dados em Excel, o relatório em PDF e cada gráfico em PNG.
Conteúdo do repositório
`index.html` — painel nacional (região, UF, município e mapa de calor).
`composicao_emulti_CNES_base.ipynb` — notebook que reconstrói a composição a partir da Base de Dados do CNES.
Como os dados foram gerados
A composição por equipe não está nos microdados do FTP do DATASUS, porque ali o arquivo de profissional não traz o identificador da equipe. Ela é reconstruída a partir da Base de Dados completa do CNES, em que a equipe é identificada pela chave composta CO_MUNICIPIO + CO_AREA + SEQ_EQUIPE (o INE fica na coluna CO_EQUIPE da tabela de equipes). O notebook filtra as equipes tipo 72, junta os profissionais pela mesma chave considerando apenas vínculos ativos, e enriquece com descrição oficial do CBO, carga horária, nome da unidade, município, UF e região.
Privacidade
Os arquivos publicados aqui não contêm o CNS dos profissionais.
Fonte
Ministério da Saúde, Cadastro Nacional de Estabelecimentos de Saúde (CNES), Base de Dados, competência 05/2026.
