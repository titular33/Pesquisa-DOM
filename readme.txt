O que é o DOM ? 
 O Document Object Model (DOM) é uma interface de programação para os documentos HTML e XML. Representa a página de forma que os programas possam alterar a estrutura do documento, alterar o estilo e conteúdo. 
 O DOM representa o documento com nós e objetos, dessa forma, as linguagens de programação podem se conectar à página.
 Uma página da Web é um documento. Este documento pode ser exibido na janela do navegador ou como a fonte HTML. Mas é o mesmo documento nos dois casos. 
  O DOM é uma representação orientada a objetos da página da web, que pode ser modificada com uma linguagem de script como JavaScript.
O DOM nos proporciona várias API’s importantes para a criação de aplicações fantásticas e cada vez mais inovadoras, entendendo o básico dele você já consegue fazer projetos incríveis.

1.  O que são os objetos window e document?
Para a melhor comprensão de DOM, é utilizada o conceito de Arvore DOM, onde imaginamos uma árvore genealógica com a seguinte regra, quem está acima é pai de quem está embaixo! 
Como vimos na Imagem 1, Window é tudo que está na “janela” , seria o pai de todos. E Document é um dos seus filhos referenciando o codigo implementado.

2 - Diferença de `getElementById`, `getElementsByClassName`, `querySelector`, `querySelectorAll`
Métodos
O DOM possui muitos métodos, são eles que fazem a ligação entre os nodes (elementos) e os eventos, algo que vou falar mais abaixo. Vou mostrar os métodos mais usados e pra quê eles servem também.
 Lembrando que existem vários, para todos os tipos e você pode ver todos aqui.

getElementById()
Esse método retorna o elemento que estiver contendo o nome do ID passado. Como os IDs devem ser únicos, é um método muito útil para pegar apenas o elemento desejado.
  var myStart = document.getElementsById('start');
myStart: elemento específico que se equipara com o seletor passado.
start: seletor passado, caso não houvesse nenhum ele retornaria null.

getElementsByClassName()
Esse método retorna um HTMLCollection de todos elementos que estiverem contendo o nome da classe passada.
  var myContainer = document.getElementsByClassName('container');
myContainer: elemento específico que se equipara com o seletor passado.
.container: seletor passado, caso não houvesse nenhum ele retornaria null.

getElementsByTagName()
Na mesma maneira do método acima, ele também retorna uma HTMLCollection mas com uma diferença: esse método retorna todos elementos contendo a tag name passada.
  var buttons = document.getElementsByTagName('button');
buttons: elemento específico que se equipara com o seletor passado.
button: tag name passada.

querySelector()
Retorna o primeiro elemento que se equipara ao seletor CSS passado. Lembrando que o seletor deve seguir a sintaxe CSS. Caso não tenha nenhum seletor, ele retornará _null. _
  var resetButton = document.querySelector('#reset');
resetButton: primeiro elemento que se equipara com o seletor passado. 
#reset: seletor passado, caso não houvesse nenhum ele retornaria null.

querySelectorAll()
Muito igual ao querySelector(), mas ele tem apenas uma diferença: retorna todos elementos que se equiparam ao seletor CSS passado.
 O seletor também deve seguir a sintaxe CSS, caso não haja nenhum ele retornará null.
  var myButtons = document.querySelectorAll('#buttons');
myButtons: elementos que se equiparam com o seletor passado.
#buttons: seletor passado, como nesse caso não há nenhum seletor com esse nome, ele retorna null.
Esses são apenas 3 métodos do DOM, existem vários e alguns são bastante usados, por exemplo o createElement() que cria um novo elemento HTML usando o nome da da tag a ser criada,
 o setAttribute() que você pode setar novos atributos para elementos HTML e muitos outros.

•	O que é um Element no JavaScript?
A interface Element é a classe base mais geral da qual todos os objetos em um Document herda. 
Ela somente tem métodos e propriedades comuns para todos os tipos de elementos. 
Mais classes específicas herdam de Element. 
Por exemplo, a interface HTMLElement é a interface base para elementos HTML, enquanto a interface SVGElement (en-US) é a base para todos os elementos SVG. 
A maioria das funcionalidades é especificada mais abaixo da hierarquia de classes. 
Exemplos : 
https://developer.mozilla.org/en-US/docs/Web/API/Element

.  Diferença de innerHTML, innerText e textContent
A diferença está no retorno deles.

innerText -> Retorna somente o texto, sem formatações ou elementos html.

innerHtml -> Retorna o texto, COM formatações e COM elementos html.

textContent -> Retorna o text COM formatações, mas sem os elementos html.

Qual a diferença entre uma NodeList e uma array comum? Como transformar a NodeList em uma array?

NodeList não é um array, se comporta de maneira similar ao array. NodeList faz parte do DOM , e tem o typeof similar de um object!
NodeList é o Nó que possui varios elements.

Podemos usar um for para ler isso
const paragrafos = document.querySelector('.paragrafos');
const ps = paragrafos.querySelectorAll('p);
console.log(ps )// NodeList
for(let p of ps){
    console.log(p); //Cada um
}
 Prova que não é Array
const paragrafos = document.querySelectorAll('.paragrafos');
Array.isArray(paragrafos) // false

Conversão rapida
Array.from(paragrafos).map(i => console.log(i));

https://emanoellopes.me/como-converter-nodelists-em-arrays/#:~:text=Basta%20usar%20o%20Array.,from(anchors).

Document.createElement()
 
Em um documento HTML, o método Document.createElement() cria o elemento HTML especificado ou um HTMLUnknownElement (en-US) se o nome do elemento dado não
 for conhecido.
 ...
   let newElement = document.createElement('input');

        document.body.appendChild(newElement);
     ...