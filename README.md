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

## Soluções já consolidadas
...

## Demais soluções, organizando

... Importante que os exemplos de referência (casos de uso) sejam listados e todas as propostas de solução façam uso dos mesmos para poderem ser comparadas, e para faciliar a sua análise...

* **Caso01**: um exemplo de portaria simples (poucos parágrafos e nenhuma estrutura).  <br/>Judisdição: federal; Autoridade: Ministério das Relações Exteriores / Gabinete do Ministro; TipoDocumento: portaria.  Documento: [PORTARIA DE 29 DE NOVEMBRO DE 2017](http://portal.imprensanacional.gov.br/todas?p_p_id=101&p_p_lifecycle=0&p_p_state=maximized&p_p_mode=view&_101_struts_action=%2Fasset_publisher%2Fview_content&_101_type=content&_101_viewMode=view&_101_groupId=68942&_101_urlTitle=portaria-de-29-de-novembro-de-2017).

* **Caso02**: ...

## Propostas de solução, em discussão neste git
...

**Level 0**: basta estar em HTML minimamente estruturado, uma matéria por página-web. Ver HTML em uso no DOU em 2017-12-07.

* ...

**Level 1**: requer estruturação controlada, uso rigoroso das marcações semânticas do [HTML5](https://github.com/okfn-brasil/HTML5-onlyContent) e adaptação do atributo *class* (CSS) do DOU de dezembro de 2017 para fins de controle semântico adicional, no mesmo espirito que [Microformat](https://en.wikipedia.org/wiki/Microformat).

* [**proposta01-caso01**](propostas/level1/proposta01-caso01.md)
* ...

**Level 2**: uso rigoroso das marcações semânticas do [HTML5-onlyContent](https://github.com/okfn-brasil/HTML5-onlyContent), e adaptação do DOU de dezembro de 2017 para ilustrar a marcação adicional, com RDF expresso em  [Microdata](https://en.wikipedia.org/wiki/Microdata_(HTML)), e metadados residuais class-microformat.

* [**proposta02-caso01**](propostas/level2/proposta02-caso01.md)
* ...
