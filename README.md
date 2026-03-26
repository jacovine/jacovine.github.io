# inep-educacao-pipeline

<!-- badges: start -->
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
<!-- badges: end -->

Repositório integrado para download, processamento, padronização, integração e geocodificação de dados do INEP para exibição de indicadores educacionais na plataforma GeoReDUS.

Site do projeto:  
https://georedus.github.io/educacao-inep/

Este projeto integra o desenvolvimento da plataforma **GeoReDUS**  
https://www.redus.org.br/georedus

---

## Visão Geral

O repositório organiza e integra bases públicas do Instituto Nacional de Estudos e Pesquisas Educacionais Anísio Teixeira (INEP), com foco em:

1. Indicadores educacionais oficiais
2. Microdados do Censo Escolar
3. Integração e geocodificação das escolas

Os valores são os divulgados oficialmente pelo INEP; os pipelines realizam a seleção, padronização, compatibilização e organização das variáveis de interesse.

---

## Bases Utilizadas

### Indicadores educacionais

- Ideb: Índice de Desenvolvimento da Educação Básica
- Inse: Indicador de Nível Socioeconômico
- TDI: Taxa de Distorção Idade-Série
- Taxas de Rendimento Escolar: Reprovação (TR) e Abandono (TA)

### Microdados
- Censo Escolar da Educação Básica
Os dados brutos são públicos e disponibilizados pelo INEP.

---

## Estrutura dos Arquivos em R (formato .qmd)

- `index.qmd` – documentação e visão geral
- `1_ideb.qmd`
- `2_inse.qmd`
- `3_tdi.qmd`
- `4_trta.qmd`
- `5_microdados.qmd`
- `6_geocode.qmd`

---

## Geocodificação

A integração espacial utiliza:

- Catálogo de Escolas (INEP)
- Pacote `geobr` (IPEA)
- Pacote `geocodebr` (IPEA)

A geocodificação é realizada em etapas sucessivas para maximizar cobertura e consistência espacial.

---

## Produtos Gerados

O pipeline exporta:

- Arquivos `.csv`
- Arquivos `.rds`
- Arquivos espaciais `.gpkg`

Estrutura de diretórios:

dados/
└── {ano}/
├── 01_brutos/
├── 02_tratados/
└── 03_geocode/

---

## Uso

Desenvolvido em R com publicação via Quarto.

Recomenda-se o uso de `renv` para reprodutibilidade.

### Reprodução

1. Clonar o repositório.
2. Abrir o projeto em RStudio ou Positron.
3. Restaurar dependências:

```r
renv::restore()
```

4. Definir o ano desejado (ano <- XXXX).
5. Executar o .qmd correspondente ou renderizar o site completo.

O pipeline realiza download automático das bases, padronização, integração e exportação.

### Compatibilidade

Estruturado para os anos de 2021 e 2023, considerando a periodicidade bienal de INSE e IDEB.

### Citação

Ao utilizar o código:

Cshunderlick, T. (2026). Pipeline para organização e geocodificação de dados educacionais do INEP [Software]. GeoReDUS.

Ao utilizar os dados, citar também as fontes originais do INEP.

### Licença

O código está licenciado sob a GNU General Public License v3.0.
As bases de dados originais seguem os termos definidos pelo INEP.

### Agradecimentos

Este trabalho integra a plataforma GeoReDUS.

Apoio institucional:
Centro de Estudos da Metrópole (CEM), FFLCH-USP e CEBRAP.

Financiamento: 
FAPESP – Processo nº 2013/07616-7.