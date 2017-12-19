# lexml-dou
Sobsídios para a **Imprensa Nacional** (responsável pelo Diário Oficial da União - DOU) e o **LexML** (padrões ePING LexML) estabelecerem consensos, norteados pelas diretivas e demandas fixadas na iniciativa "Atos.Gov" da **Casa Civil**.

Repositório aberto para **consulta pública**, mediada pela Open Knowledge Brasil.

## Apresentação dos problemas

> **As pessoas não conseguem encontrar normas do Governo federal na internet**. A
frase anterior, por mais impactante que possa ser, expressa uma realidade atual (...) encontrar atos administrativos na internet, situação absurda e inaceitável.  (...) em torno de 400 normas por ano, ao passo que são produzidas aproximadamente 1.500 normas de hierarquia inferior por dia, tais como portarias, instruções normativas e resoluções, assinadas por diversas autoridades nos 27 ministérios e em suas 159 autarquias e fundações. A disponibilização dessas milhares de normas diárias na internet é gerenciada por cada órgão ou entidade, individualmente, sem padronização nem tampouco garantia de conteúdos ou atualização de vigência. Há, porém, um órgão federal que desde 1808 garante, por meio da publicidade oficial gerada pelo Diário Oficial da União, que as normas produzam seus efeitos jurídicos, sendo o guardião de todo o acervo normativo federal: a Imprensa Nacional.<br/>[Casa Civil, iniciativa Atos.gov](subsidios/PaperAtosGov.pdf)

Além deste problema principal, diversos problemas secundários podem ser enumerados:

1. *Documentos individualizados*: problema solucionado parcialmente no HTML. <br/>A individualização permite que o HTML receba um selo de autenticação digital auditável  ([checksum](https://en.wikipedia.org/wiki/Checksum)), mas em caso de documento com imagens ou anexos, requer um só [documento EPUB](https://en.wikipedia.org/wiki/EPUB) encapsulando todos os arquivos.

2. *Documentos identificados de forma única*: identificadores de edição e de matéria, com respectivos códigos presentes na página de apresentação da matéria.

3. *Endereço principal do documento oficial*: a "URL canônica", com base no domínio principal (`IN.gov.br`) precisa ser expresso de forma "o mais simples possível" (endereço curto em conformidade com recomendação das [cool URIs](https://www.w3.org/TR/cooluris/)), enfatizando apenas o identificador de matéria e o identificador de edição. <br/>Além disso a URL precisa ser *persistente*, ou seja, uma [PURL](https://en.wikipedia.org/wiki/Persistent_uniform_resource_locator) com durabilidade de anos ou décadas, garantida por lei ou por contrato de fornecidamento.

4. *Conteúdo dos documentos em [HTML5](https://www.w3.org/TR/html5/) estruturado com  **elementos essenciais** devidamente destacados*: existem interseções entre as considerações do DOU relativas a "elementos essenciais" (ver [portaria 268](http://lexml.gov.br/urn/urn:lex:br:imprensa.nacional:portaria:2009-10-05;268) da IN) e as considerações do LexML para a formação da URN LEX a partir de metadados explícitos do conteúdo &mdash; presentes no conteúdo auditado pelo público.

5. *Marcação dos elementos da URN LEX*: o portal LexML hoje já se encarrega da catalogação e da *resolução da [URN LEX](https://pt.wikipedia.org/wiki/Lex_(URN))* (quem acessa a URN pelo portal obtém automaticamente a URL da Imprensa Nacional), todavia, para que seja possível e o processo totalmente automatizado, os *elementos essenciais* (bastando aqueles que suprem a URN LEX) do conteúdo HTML precisam ser devidamente marcados.

6. ...

## Princípios e propostas principais

Não existe uma solução simples e direta, a implantação precisa ser gradual, e o custo ou mesmo viabilidade de implantação da solução envolve um contexto amplo que será aqui denominado de "informatização do setor".  Quanto maior o *[nível  de maturidade](https://en.wikipedia.org/wiki/Capability_Maturity_Model) na informatização*, maiores as chances de sucesso na implantação, e maior a viabilidade de uma solução mais ampla e complexa. Foram eleitos **5 níveis de maturidade**, e a cada nível uma DTD ([*Document Type Definition*](https://en.wikipedia.org/wiki/Document_type_definition)) mais exigente que a DTD do nível anterior:

* **Nível zero**: no início, a produção [HTML](https://pt.wikipedia.org/wiki/HTML) em si já é um grande salto para todo o setor, assim como para o público. Não há necessidade de se cumprir padrões adicionais, o formato HTML em "estilo livre" é suficiente. A DTD resultante é apelidada de `HTML-free`.

* **Nível 1**: o setor cria condições de gerar  documentos HTML de forma mais  controlada, de modo que tags [HTML5](https://www.w3.org/TR/html5/) (HTML versão 5.2) e atributos `class` podem ser empregados de maneira mais padronizada. Os conteúdos marcados são sequências, sem uma hierarquia explícita. A DTD resultante é apelidada de `HTML5-lex1`.

* **Nível 2**: mesmo que o *Nível 2*, porém adotando hierarquização (ex. tag `section`) e itemização (ex. listas `ol`) mais rigorosas. Os conteúdos marcados podem apresentar uma hierarquia explícita. A DTD resultante é apelidada de `HTML5-lex2`.

* **Nível 3**: incorpora padronização de controle semântico nos metadados auditáveis, principalmente aqueles necessários para a garantia de interoperabilidade LexML (componentes da [URN LEX](https://pt.wikipedia.org/wiki/Lex_(URN)#Identificadores_transparentes)), e rotulação de fragmentos (ex. rótulos  "capítulo", "artigo", etc. ao longo do texto). As opções [RDFa](https://www.w3.org/TR/rdfa-core/) e [Microdata](https://en.wikipedia.org/wiki/Microdata_(HTML)) são válidas, sendo preferível (*default*) a marcação Microdata. A DTD resultante é apelidada de `HTML5-lex3` (opcional  `HTML5-lex3rdfa`).<br/>Notas: ficariam também estabelecidas neste nível as diretivas de encapsulamento [EPUB](https://en.wikipedia.org/wiki/EPUB) (ou similar) para  conteúdos multimidia (ex. matérias com figuras ou mapas); e as diretivas para certificação digital pública ([*checksum*](https://en.wikipedia.org/wiki/Checksum)) da matéria.

* **Nível 4**: avança na marcação semântica de grão-fino (por ex. o nome "Senador João Silva" é subdividido nas partes "João Silva" e  titulo honorífico "Senador"), e estabelece controle sobre marcações semânticas adicionais (ex. nomes de lugares, datas, códigos de processos, etc.) e *hyperlinks* (ligações intradocumento e com outros documentos nas citações formais).  A DTD resultante é apelidada de `HTML5-lex4` (opcional  `HTML5-lex4rdfa`).

Acima do *nível 4* temos a opção do [XML LexML](http://projeto.lexml.gov.br/documentacao/Parte-3-XML-Schema.pdf) substituindo o HTML, caso a DTD `HTML5-lex4` não possa ser mapeada (via [XSLT](https://en.wikipedia.org/wiki/XSLT)) integralmente. As DTDs XML-LexML seriam apelidadas de `XML-lexml-vN` com versionamento `vN` em conformidade com as normas LexML vigentes.  <br/>Nota: como as normas técnicas vinculadas às DTDs estão também em constante processo de evolução, é previsto, adicionalmente, para fins de preservação digital, que além do código de *nível* (lex1, lex2, etc.) haja o versionamento  na rotulação das DTDs. Por exemplo a DTD "HTML5 nível 3 versão 2.1" seria designada `HTML5-lex3v2.1`.

## Soluções já consolidadas
... em construção ...

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

**Nível 2** e **Nível 3**: uso rigoroso das marcações semânticas do [HTML5-onlyContent](https://github.com/okfn-brasil/HTML5-onlyContent), e adaptação do DOU de dezembro de 2017 para ilustrar a marcação adicional, com [RDF](https://en.wikipedia.org/wiki/Resource_Description_Framework) expresso em  **[Microdata](https://en.wikipedia.org/wiki/Microdata_(HTML))**, e metadados residuais class-microformat.

* [**proposta2_01-ok-caso01**](propostas/nivel2/proposta2_01-ok-caso01.md)
* [**proposta2_02-ok-caso02**](propostas/nivel2/proposta2_02-ok-caso02.md)
* ...
