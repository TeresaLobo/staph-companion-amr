# Staphylococcaceae: animais de companhia e resistência antimicrobiana

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23239447.svg)](https://doi.org/10.5281/zenodo.23239447)

**Depósito publicado:** [Zenodo, versão 0.1.0](https://doi.org/10.5281/zenodo.23239447). Este DOI identifica os dados derivados e o código desta versão; o pacote completo de sequências e o manuscrito não integram o registro.

Autora do estudo: **Teresa de Lisieux Guedes Ferreira Lôbo**.

Versão **0.1.0**, dados e código de pesquisa em revisão. Este repositório contém dados derivados, tabelas, figuras e scripts; não certifica a conclusão do manuscrito nem uma publicação em periódico.

O arquivo **analises_staph_v0.1.0.zip** contém as pastas descritas abaixo, com dados, código, figuras e manifesto SHA-256. Extraia-o antes de executar os scripts.

## Conteúdo e estado da validação

- `dados/`, `tabelas/` e `figuras/`: resultados arquivados validados, com **414 buscas proteicas**, AMRFinderPlus 4.2.7 e base **2026-03-24.1** (1842 hits AMR e 75 STRESS).
- `validacao/`: verificações das análises arquivadas. O relatório de correções inclui estados históricos; consultar este README para o estado desta release.
- `reanotacao_sem_wsl/relatorios_tratados/`: **415 relatórios novos**, busca combinada DNA/proteínas no Galaxy, base **2026-05-15.1** (1884 hits AMR e 78 STRESS). CRC, identificadores, cabeçalhos e versões conferidos. A validação integral das novas anotações e a integração ao manuscrito continuam pendentes.
- `reprodutibilidade/`: scripts de auditoria, reconstrução, sensibilidade e tratamento. Alguns exigem o projeto original ou arquivos de sequência/anotação externos; conferir argumentos e caminhos antes de executar. Não há uma execução integral autossuficiente nesta release.

Não misturar os denominadores 414 e 415. `mecA1` é contabilizado separadamente de `mecA`. Não há dados experimentais de suscetibilidade, demonstração de transmissão ou atribuição confirmada de elementos a plasmídeos. As buscas concluídas não demonstram, sozinhas, reservatório epidemiológico ou resistência fenotípica.

Os 415 genomas são públicos, obtidos do NCBI; a lista de acessos, BioSamples, BioProjects e URLs de origem encontra-se em `dados/genomas_metadados_resultados.csv`. A autora realizou o estudo secundário; não reivindica geração das sequências originais. Seleção por espécie e ordem de acesso; amostra não aleatória e com confundimento por espécie/hospedeiro.

## Reproduzir

Python 3, pandas, numpy e reportlab são usados pelos scripts disponíveis. Prokka e AMRFinderPlus foram executados em ambientes registrados na documentação. A reconstrução das análises arquivadas exige a pasta original como primeiro argumento de `validate_rebuild.py`; o segundo argumento define a saída. Faça uma cópia de trabalho antes de reexecutar scripts que escrevem resultados.

Para reprocessar os relatórios novos, colocar `amrfinder_415_Galaxy.zip` em `reanotacao_sem_wsl/` e executar `python reprodutibilidade/treat_galaxy_reports.py` numa cópia de trabalho. O ZIP bruto não integra o histórico Git. Os arquivos volumosos e o manuscrito de revisão estão no pacote local `pack_artigo_completo_para_revisao.zip`, que será depositado separadamente no Zenodo; o identificador do pacote completo será adicionado após seu depósito separado. Ainda não existe link público desse pacote nesta versão.

## Citação, licença e pendências

Metadados em `.zenodo.json`; citação em `CITATION.cff`. DOI da versão 0.1.0: https://doi.org/10.5281/zenodo.23239447 . Dados derivados e documentação próprios: CC BY 4.0. Código próprio: MIT, conforme `LICENSE_CODE`. Arquivos de terceiros mantêm suas condições originais; a licença deste repositório não concede novos direitos sobre sequências NCBI nem software externo.

Ainda faltam a validação completa das anotações novas, conferência dos genes do controle positivo, integração final ao manuscrito e confirmação das declarações institucionais pela autora. A submissão ao periódico não foi realizada.
