## Proposta01, exemplificando através do Caso01

Meta: **Nível 2**.   Ilustrado por [Caso01](../../casos/caso01.md).

**Resumo da porposta**: uso rigoroso das tags e marcações semânticas do [HTML5-onlyContent](https://github.com/okfn-brasil/HTML5-onlyContent), e controle do atributo `class` (CSS), do DOU de dezembro de 2017, para ilustrar a marcação adicional, no mesmo espirito que [Microformat](https://en.wikipedia.org/wiki/Microformat).

**Código**:
```html
<article class="portaria-dou">

<nav class="detalhes-dou">
  <p class="linha-pipes">
    Publicado em: <span class="publicado-dou-data">30/11/2017</span>
    | Edição: <span class="edicao-dou-data">229</span>
    | Seção:  <span class="secao-dou">Seção: 2</span>
    | Página: <span class="pagina-dou">66</span>
  </p>
  <p class="linha-pipes">
   <span class="jurisdicao-dou">Esfera federal</span>
   | <span class="autoridade-dou">Ministério das Relações Exteriores / Gabinete do Ministro</span>
  </p>
</nav>

<header class="ParteInicial">
	<h3 class="titulo-dou">PORTARIA DE 29 DE NOVEMBRO DE 2017</h3>

         <p>O MINISTRO DE ESTADO DAS RELAÇÕES EXTERIORES, de acordo com o disposto no art. 18, parágrafo 3o, do Decreto no 93.325, de 1o de outubro de 1986, e nos termos da Lei no 11.440, de 29 de dezembro de 2006, resolve:</p>
</header>

<p>Remover ex officio ANDRÉ ODENBREIT CARVALHO, Ministro de Segunda Classe da Carreira de Diplomata do Ministério das Relações Exteriores, da Missão do Brasil junto à União Europeia, em Bruxelas, para a Secretaria de Estado.

<footer class="ParteFinal">
  <p class="assinatura-dou">ALOYSIO NUNES FERREIRA</p>
</footer>

</article>
```
