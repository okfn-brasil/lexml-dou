# lexml-dou
Sobsídios para a **Imprensa Nacional** (responsável pelo Diário Oficial da União - DOU) e o **LexML** (padrões ePING LexML) estabelecerem consensos, norteados pelas diretivas e demandas fixadas na iniciativa "Atos.Gov" da **Casa Civil**.

Repositório aberto para **consulta pública**, mediada pela Open Knowledge Brasil.

## Apresentação dos problemas

> **As pessoas não conseguem encontrar normas do Governo federal na internet**. A
frase anterior, por mais impactante que possa ser, expressa uma realidade atual (...) encontrar atos administrativos na internet, situação absurda e inaceitável.  (...) em torno de 400 normas por ano, ao passo que são produzidas aproximadamente 1.500 normas de hierarquia inferior por dia, tais como portarias, instruções normativas e resoluções, assinadas por diversas autoridades nos 27 ministérios e em suas 159 autarquias e fundações. A disponibilização dessas milhares de normas diárias na internet é gerenciada por cada órgão ou entidade, individualmente, sem padronização nem tampouco garantia de conteúdos ou atualização de vigência. Há, porém, um órgão federal que desde 1808 garante, por meio da publicidade oficial gerada pelo Diário Oficial da União, que as normas produzam seus efeitos jurídicos, sendo o guardião de todo o acervo normativo federal: a Imprensa Nacional.<br/>[Casa Civil, iniciativa Atos.gov](subsidios/PaperAtosGov.pdf)

Além deste problema principal, diversos problemas secundários e subproblemas do principal podem ser enumerados:

1. Documentos individualizados: problema solucionado no HTML, mas ainda não no PDF (ou EPUB).

2. Documentos identificados de forma única e transparente: as normas LexML requerem uso da [URN LEX](https://pt.wikipedia.org/wiki/Lex_(URN)), por hora tem-se apenas o ID da matéria, que também deve ser mantido.

3. Documentos em HTML5 estruturado, tendo seus  *elementos essenciais* devidamente destacados: existem interseções entre as considerações do DOU relativas a "elementos essenciais" e as considerações do LexML para a formação da URN LEX a partir de metadados explícitos do conteúdo &mdash; presentes no conteúdo auditado pelo público.

4. ...

## Princípios e propostas principais

Não existe uma solução simples e direta, a implantação precisa ser gradual, e o custo ou mesmo viabilidade de implantação da solução envolve um contexto amplo que será aqui apelidado de "informátização do setor".  Quanto maior o [nível  de maturidade](https://en.wikipedia.org/wiki/Capability_Maturity_Model) na informaização, maiores as chances de sucesso na implantação, e maior a viabilidade de uma solução complexa. Elegemos então 4 níveis de maturidade:

* **Nível zero**: quando o contexto não está muito preparado mais existe boa vontade para começar, e as adaptações básicas são realizadas... Um grande salto como começar a produzir o HTML além do PDF. A DTD resultante é apelidada de `HTML-free`.

* **Nível 1**: o template dos documentos HTML pode ser controlado, de modo que tags HTML5 e atributos `class`  controlados podem ser empregados de maneira mais padronizada.  A DTD resultante é apelidada de `HTML5-lex1`.

* **Nível 2**: além do template controlado, a comunidade estabelece consensos, e adopta taambém marcação semântica nos metadados.  A DTD resultante é apelidada de `HTML5-lex2`.

* **Nível 3**: o HTML inteiro é padronizado, com tags semanticas e marcações adicionais de grão-fino (ex. destaque labels, identificação das partes, etc.).  A DTD resultante é apelidada de `HTML5-lex3`.

Acima do nível 3 temos a opção do XML, caso a DTD `HTML5-lex3` não possa ser mapeada (XSLT) para o [XML-LexML](http://projeto.lexml.gov.br/documentacao/Parte-3-XML-Schema.pdf). É previsto, de qualquer modo, que além do nível haja o versionamento, prevendo correções e aperfeiçoamentos futuros (ex. `HTML5-lex2v2.1` poderia ser um rótulo de DTD).

## Soluções já consolidadas
...

## Organizando soluções através de exemplos

... Importante que os exemplos de referência (casos de uso) sejam listados e todas as propostas de solução façam uso dos mesmos para poderem ser comparadas, e para faciliar a sua análise...

* [**Caso01**](casos/caso01.md): um exemplo de portaria simples (poucos parágrafos e nenhuma estrutura).  <br/>Judisdição: federal; Autoridade: Ministério das Relações Exteriores / Gabinete do Ministro; TipoDocumento: portaria.  

* [**Caso02**](casos/caso02.md): um exemplo de lei simples (poucos parágrafos e só articulação)<br/> Judisdição: federal; Autoridade: Atos do Congresso Nacional; TipoDocumento: Decreto Legislativo.

## Propostas de solução, em discussão neste git
...

**Nível 0**: basta estar em HTML minimamente estruturado, uma matéria por página-web.

* [**proposta0_01-dou-caso01.md**](propostas/nivel0/proposta0_01-dou-caso01.md). Ver HTML em uso no DOU em 2017-12-07.
* [**proposta0_02-dou-caso02.md**](propostas/nivel0/proposta0_02-dou-caso02.md). Idem.
* [**proposta0_03-dou-caso03.md**](propostas/nivel0/proposta0_03-dou-caso03.md). Idem.
* [**proposta0_04-ccv-caso03.md**](propostas/nivel0/proposta0_04-ccv-caso03.md). Ver HTML da Casa Civil.


**Nível 1**: requer estruturação controlada, uso rigoroso das marcações semânticas do [HTML5](https://github.com/okfn-brasil/HTML5-onlyContent) e adaptação do atributo *class* (CSS) do DOU de dezembro de 2017 para fins de controle semântico adicional, no mesmo espirito que [Microformat](https://en.wikipedia.org/wiki/Microformat).

* [**proposta01-caso01**](propostas/nivel1/proposta1_01-caso01.md)

* ...

**Nível 2**: uso rigoroso das marcações semânticas do [HTML5-onlyContent](https://github.com/okfn-brasil/HTML5-onlyContent), e adaptação do DOU de dezembro de 2017 para ilustrar a marcação adicional, com RDF expresso em  [Microdata](https://en.wikipedia.org/wiki/Microdata_(HTML)), e metadados residuais class-microformat.

* [**proposta2_01-ok-caso01**](propostas/nivel2/proposta2_01-ok-caso01.md)
* ...
