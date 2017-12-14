
## Proposta 2.02, exemplificando através do Caso02

Meta: **Nível 2**. Ilustrado por [Caso02](../../casos/caso02.md) e  [demo](https://okfn-brasil.github.io/lexml-dou/demo/prop2_02.html).

**Resumo da porposta**: uso rigoroso das tags e marcações semânticas do [HTML5-onlyContent](https://github.com/okfn-brasil/HTML5-onlyContent/blob/master/spec.md), com [RDF](https://en.wikipedia.org/wiki/Resource_Description_Framework) expresso em  [Microdata](https://en.wikipedia.org/wiki/Microdata_(HTML)), e  semântica estrutural resisual com atributo `class` (CSS) de maneira similar ao [Microformat](https://en.wikipedia.org/wiki/Microformat).

**Código**:
```html
<article id="oficial" itemscope itemprop="Legislation" itemtype="http://schema.org/Legislation" xml:lang="pt-br">

  <nav class="content-metadata"><!-- Metadados -->
    <p itemprop="isPartOf" itemscope itemtype="http://schema.org/PublicationIssue">
      <label>Publicado em</label>: <time itemprop="dateCreated" datetime="2017-12-05">05/12/2017</time>
      | <span itemprop="issueNumber">
        <label>Edição</label>: <span itemprop="identifier">229</span>
      | <label>Seção</label>:  <span>1</span>
      </span>
      | <a href="http://pesquisa.in.gov.br/imprensa/jsp/visualiza/index.jsp?data=05/12/2017&amp;jornal=515&amp;pagina=2"><label>Página</label>:
          <span itemprop="pageStart">2</span></a>
    </p>
    <p class="linha-pipes">
     <span value="br"><label>Esfera</label> federal</span><!--  itemprop="legislationJurisdiction" -->
     | <label>Autoridade/Subseção:</label> <span itemprop="legislationPassedBy">Atos do Congresso Nacional</span>
    </p>
  </nav>


  <header class="ParteInicial" id="inicio">
    <p class="par Preambulo"> Faço saber que o Congresso Nacional aprovou, e eu, Eunício Oliveira,
        Presidente do Senado Federal, nos termos do parágrafo único do art. 52 do Regimento Comum e
        do inciso XXVIII do art. 48 do Regimento Interno do Senado Federal, promulgo o seguinte</p>

    <h2 class="Epigrafe" itemprop="http://schema.org/name">
      <label itemprop="legislationType">DECRETO LEGISLATIVO</label>
      <span>Nº 173</span>, DE <time>2017</time><sup><a href="#foot1">(*)</a></sup>
    </h2>

    <p class="Ementa" itemprop="description">Aprova o texto do Acordo Complementar de Revisão do Convênio de Seguridade
     Social firmado entre a República Federativa do Brasil e o Reino da Espanha, assinado em Madri,
     em 24 de julho de 2012.</p>

    <p class="par Preambulo">O Congresso Nacional decreta:</p>
  </header>

  <div id="art1" class="art">
    <p class="art caput"><label>Art. 1º</label> – Fica aprovado o texto do Acordo Complementar de Revisão do
     Convênio de Seguridade Social firmado entre a República Federativa do Brasil e o Reino da
      Espanha, assinado em Madri, em 24 de julho de 2012. </p>

    <p class="par"><label>Parágrafo único</label>. Nos termos do inciso I do art. 49 da Constituição
     Federal, ficam sujeitos à aprovação do Congresso Nacional quaisquer atos que possam resultar
     em revisão do referido Acordo, bem como quaisquer ajustes complementares que acarretem
     encargos ou compromissos gravosos ao patrimônio nacional. </p>
  </div>

  <p id="art2" class="art"><label>Art. 2º</label> – Este Decreto Legislativo entra em vigor na data de sua
     publicação.</p>

  <footer id="fecho" class="ParteFinal">
    <div class="Assinatura" itemprop="legislationResponsible" itemscope itemtype="http://schema.org/Person">
      <p itemprop="name" class="assina-dou">Senador EUNÍCIO OLIVEIRA</p>
      <p itemprop="memberOf" class="cargo-dou">Presidente do Senado Federal</p>
    </div>
    <div class="rodape" itemscope itemtype="http://schema.org/WPFooter">
      <hr/>
      <p id="foot1" itemprop="about"><label>(*)</label> O texto do Protocolo acima citado está publicado no <a href="http://legis.senado.leg.br/diarios/BuscaDiario?tipDiario=1&datDiario=17/10/2017&paginaDireta=38">Diário do Senado Federal de 17/10/2017</a>.</p>
    </div>
  </footer>
</article>
```
