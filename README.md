# Equipes_72 — Composição das equipes eMulti (Rede Municipal do Rio de Janeiro)

Painel e dados sobre a composição profissional das equipes Multiprofissionais (eMulti, tipo de equipe 72) da rede municipal do estado do Rio de Janeiro, a partir da Base de Dados do CNES, competência 05/2026.

## Painel online

Após ativar o GitHub Pages, o painel fica disponível em:

```
https://anamazza.github.io/Equipes_72/
```

O painel é um arquivo HTML único, com os dados embutidos. Ele traz indicadores gerais, filtros por município, categoria profissional e unidade, e seis gráficos com rótulos fixos: profissionais por categoria, equipes que contam com cada categoria, principais municípios, principais ocupações (CBO), distribuição do número de profissionais por equipe e carga horária por categoria. Também permite baixar os dados em Excel, o relatório em PDF e cada gráfico em PNG com o título embutido.

## Conteúdo do repositório

- `index.html` — painel interativo (abre direto no navegador).
- `base_detalhada_sem_cns.csv` — base detalhada, uma linha por profissional em cada equipe, sem o CNS.
- `composicao_emulti_CNES_base.ipynb` — notebook que reconstrói a composição a partir da Base de Dados do CNES.

## Como os dados foram gerados

A composição por equipe não está nos microdados do FTP do DATASUS, porque ali o arquivo de profissional não traz o identificador da equipe. Ela é reconstruída a partir da Base de Dados completa do CNES, em que a equipe é identificada pela chave composta `CO_MUNICIPIO + CO_AREA + SEQ_EQUIPE` (o INE fica na coluna `CO_EQUIPE` da tabela de equipes).

O notebook faz, em resumo:

1. Baixa a Base de Dados do CNES da competência.
2. Filtra as equipes tipo 72 na `tbEquipe` e monta a chave composta.
3. Junta os profissionais pela mesma chave na `rlEstabEquipeProf`, considerando apenas vínculos ativos.
4. Enriquece com descrição oficial do CBO, carga horária, nome da unidade e município.
5. Exporta a base detalhada e as tabelas de composição.

## Privacidade

Os arquivos publicados aqui não contêm o CNS dos profissionais. A base original usada na geração inclui esse identificador e não deve ser publicada em repositório público.

## Fonte

Ministério da Saúde, Cadastro Nacional de Estabelecimentos de Saúde (CNES), Base de Dados, competência 05/2026.
