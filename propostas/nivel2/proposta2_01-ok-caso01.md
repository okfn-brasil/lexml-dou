
## Proposta02, exemplificando através do Caso01

Meta: **Level 2**. Ilustrado por [Caso01](../../casos/caso01.md).

**Resumo da porposta**: uso rigoroso das tags e marcações semânticas do [HTML5-onlyContent](https://github.com/okfn-brasil/HTML5-onlyContent/blob/master/spec.md), e adaptação do DOU de dezembro de 2017 para ilustrar a marcação adicional, com [RDF](https://en.wikipedia.org/wiki/Resource_Description_Framework) expresso em  [Microdata](https://en.wikipedia.org/wiki/Microdata_(HTML)), e metadados residuais via controle do atributo `class` (CSS) de maneira similar ao [Microformat](https://en.wikipedia.org/wiki/Microformat).

**Decisão pendente**: por ser uma portaria relativa a *ato executivo*, a rigor, não é compativel com a semântica de `Legislation`, mas comparativamente a outras opções do SchemaOrg, seria apenas uma flexibilização. A alternativa como CreativeWork ou [TextDigitalDocument](http://schema.org/TextDigitalDocument) também é viável, mas requer revisão de atributos típicos como `legislationPassedBy` (autoridade emitente), que flexibilizado como `GovernmentService`.

Decisão em uso:  enquanto não temos algo melhor, optando por deixar todas as matérias de "atos oficiais" como `Legislation`, flexibilizado para comportar demais poderes (não-legislativos).

**Código**:
```html
<article itemscope itemtype="http://schema.org/Legislation" lang="pt-br">

  <nav class="auditable-metadata"><!-- Metadados auditáveis-->
    <dl itemprop="isPartOf" itemscope itemtype="http://schema.org/PublicationIssue" class="sepByPipes">
      <dt>Publicado em</dt> <dd><time itemprop="dateCreated" datetime="2017-11-30">30/11/2017</time></dd>
      <dt>Edição</dt>       <dd itemprop="issueNumber">
          <span itemprop="identifier">229</span>, <label>Seção</label> <span>2</span>
      </dd>
      <dt>Página</dt>       <dd itemprop="pageStart">66</dd>
    </dl>
    <dl class="sepByPipes">
     <dt>Esfera/Organização</dt> <dd content="http://wikidata.org/entity/Q155">federal</dd>
       <!--  itemprop="legislationJurisdiction", semantica de prefixo LEX de legislationPassedBy -->
       <!-- wikidata-ID seria valor de http://pending.schema.org/CategoryCode -->
     <dt>Autoridade/Subseção</dt>
     <dd itemprop="legislationPassedBy">Ministério das Relações Exteriores / Gabinete do Ministro</dd>
    </dl>
  </nav>

  <header class="ParteInicial">

    <h2 class="Epigrafe" itemprop="name">
      <label itemprop="legislationType">PORTARIA</label> DE <time datetime="2017-11-29">29 DE NOVEMBRO DE 2017</time>
    </h2>

    <p>O MINISTRO DE ESTADO DAS RELAÇÕES EXTERIORES, de acordo com o disposto no art. 18, parágrafo 3o, do Decreto no 93.325, de 1o de outubro de 1986, e nos termos da Lei no 11.440, de 29 de dezembro de 2006, resolve:</p>
  </header>

  <p>Remover ex officio ANDRÉ ODENBREIT CARVALHO, Ministro de Segunda Classe da Carreira de Diplomata do Ministério das Relações Exteriores, da Missão do Brasil junto à União Europeia, em Bruxelas, para a Secretaria de Estado.

  <footer class="ParteFinal">
    <p class="assinatura-dou">ALOYSIO NUNES FERREIRA</p>
  </footer>

</article>
```
