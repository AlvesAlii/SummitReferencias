<div align="center">

# SummitReferencias

**Análise Forense e Correção Preditiva do Erro Estatístico da Eleição Norte-Americana de 1936**

4º UMC Summit · Pesquisa, Inovação e Extensão · Universidade de Mogi das Cruzes

[![Site](https://img.shields.io/badge/site-alvesalii.github.io%2FSummitReferencias-3e2865?style=for-the-badge)](https://alvesalii.github.io/SummitReferencias/)
[![Notebook](https://img.shields.io/badge/notebook-Google%20Colab-963eaf?style=for-the-badge&logo=googlecolab&logoColor=white)](https://colab.research.google.com/drive/11jlHW2HZg95QQr3NLWuY5VtJ-yvYTK2Y?usp=sharing)

<a href="https://alvesalii.github.io/SummitReferencias/"><img src="https://api.qrserver.com/v1/create-qr-code/?size=440x440&margin=12&color=3e2865&bgcolor=ffffff&data=https%3A%2F%2Falvesalii.github.io%2FSummitReferencias%2F" alt="QR code para a página de links do projeto" width="220"></a>

Escaneie o QR code ou acesse **[alvesalii.github.io/SummitReferencias](https://alvesalii.github.io/SummitReferencias/)**
para abrir o notebook e as referências do estudo.

</div>

---

## Sobre o projeto

Em 1936, a revista *The Literary Digest* recebeu **2,37 milhões** de respostas à sua enquete eleitoral e previu a vitória de Alf Landon com 57% dos votos. Franklin D. Roosevelt venceu com **62%**. O erro mostrou que uma amostra muito grande não compensa uma amostra enviesada: a revista ouviu sobretudo assinantes, donos de telefone e de automóvel, um público mais republicano do que o eleitorado da época.

Neste trabalho, investigamos esse erro como cientistas de dados forenses: limpamos os dados históricos, medimos o viés de seleção e de não resposta e testamos se um modelo simples, ancorado no resultado real de 1932, consegue corrigir a previsão de 1936.

## Metodologia

| Etapa | O que foi feito | Ferramentas |
|---|---|---|
| 1. Coleta | Abas de 1932 e 1936 do `LitDigestFull.xlsx` | Excel |
| 2. Limpeza | Padronização de colunas e estados; junção sem perdas (48 estados) | Pandas · NumPy |
| 3. Diagnóstico | Comparação do viés declarado em 1932 com o erro da enquete em 1936 | Matplotlib |
| 4. Modelo | Regressão Linear com a enquete de 1936 e o resultado real de 1932 | Scikit-Learn |
| 5. Validação | Leave-One-Out; erro médio absoluto (MAE) e acerto do vencedor | Scikit-Learn |

## Principais resultados

| Métrica | Enquete original | Modelo corrigido |
|---|:---:|:---:|
| Erro médio por estado (MAE) | 18,7 p.p. | **3,4 p.p.** |
| Estados com o vencedor correto | 18 de 48 | **47 de 48** |
| Votos eleitorais atribuídos ao vencedor correto | 170 | **526** |

- A correlação entre o viés da amostra em 1932 e o erro da enquete em 1936 foi de **r = −0,90**: o erro era sistemático e, por isso, corrigível.
- *p.p.* = pontos percentuais, a diferença entre o percentual previsto e o real.

## Conclusões

- **Volume não é representatividade:** milhões de respostas não evitaram o erro, porque a amostra era enviesada.
- **Uma âncora confiável corrige o viés:** o resultado real de 1932 reduziu o erro médio de 18,7 para 3,4 p.p.
- **IA responsável começa pelos dados:** dados enviesados geram modelos enviesados; auditar quem está na amostra é o primeiro passo.

## Autores

| | |
|---|---|
| **Autores** | Alexandre Araújo, Alison Alves, Antonio Saurin e Isabelli Reno |
| **Orientador** | Prof. Fabiano Bezerra Menegidio |
| **Local** | Universidade de Mogi das Cruzes (UMC), Mogi das Cruzes, SP |

## Referências

- Resultados oficiais: [eleição de 1936](https://en.wikipedia.org/wiki/1936_United_States_presidential_election) e [eleição de 1932](https://en.wikipedia.org/wiki/1932_United_States_presidential_election) (Wikipedia).

## Arquivos deste repositório

| Arquivo | Conteúdo |
|---|---|
| `index.html` | Página de links publicada no GitHub Pages |
