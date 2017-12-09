
## Proposta02, exemplificando através do Caso01

Meta: **Level 3**.

**Resumo da porposta**: uso rigoroso das marcações semânticas do [HTML5-onlyContent](https://github.com/okfn-brasil/HTML5-onlyContent), e adaptação do DOU de dezembro de 2017 para ilustrar a marcação adicional, com RDF expresso em  [Microdata](https://en.wikipedia.org/wiki/Microdata_(HTML)), e metadados residuais class-microformat.

**Código**:
```html
<article itemscope itemprop="Legislation" itemtype="http://pending.schema.org/Legislation">
  <nav class="detalhes-dou">
    <p itemscope itemtype="http://schema.org/PublicationIssue">
      Publicado em: <span itemprop="dateCreated">30/11/2017</span>
      | Edição e seção: <span itemprop="issueNumber">229, sec. 2</span>
      | Página: <span itemprop="pageStart">66</span>
    </p>
    <p class="linha-pipes">
     <span itemprop="legislationJurisdiction">Esfera federal</span>
     | <span itemprop="legislationPassedBy">Ministério das Relações Exteriores / Gabinete do Ministro</span>
     | <span itemprop="legislationType">Portaria</span>
    </p>
  </nav>

  <header class="ParteInicial">
    <h3 itemprop="http://schema.org/name">PORTARIA DE 29 DE NOVEMBRO DE 2017</h3>

    <p>O MINISTRO DE ESTADO DAS RELAÇÕES EXTERIORES, de acordo com o disposto no art. 18, parágrafo 3o, do Decreto no 93.325, de 1o de outubro de 1986, e nos termos da Lei no 11.440, de 29 de dezembro de 2006, resolve:</p>
  </header>

  <p>Remover ex officio ANDRÉ ODENBREIT CARVALHO, Ministro de Segunda Classe da Carreira de Diplomata do Ministério das Relações Exteriores, da Missão do Brasil junto à União Europeia, em Bruxelas, para a Secretaria de Estado.

  <footer class="ParteFinal">
    <p class="assinatura-dou">ALOYSIO NUNES FERREIRA</p>
  </footer>

</article>
```
