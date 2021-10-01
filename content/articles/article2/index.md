---
title: Starting Learn React
tags: react, js, full-stack
excerpt: Iniziamo il viaggio alla scoperta di React in diverse lezioni
createdAt: 2021-07-13 15:53:34
---

## NPX

Prima di passare ad usare react a pieno e quindi installare il bundler o la cli proviamo a capire come funziona l'injection caricando le sole liberie tramite [unpkg](https://unpkg.com/).

````html
<body>
  <div id="root"></div>
  <script src="https://unpkg.com/react@17.0.2/umd/react.development.js"></script>
  <script src="https://unpkg.com/react-dom@17.0.2/umd/react-dom.development.js"></script>
  <script type="text/javascript">
    const rootElement = document.getElementById('root')
    const element = React.createElement('div', {
      className: 'container',
      children: 'Stringa fatta con React!',
    })
    ReactDOM.render(element, rootElement)
  </script>
</body>
````

In pratica andiamo a caricare le librerie di React come prima cosa:

````html
<script src="https://unpkg.com/react@17.0.2/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@17.0.2/umd/react-dom.development.js"></script>
````

Poi andiamo a scrivere il nostro primo codice **React** andando a selezionare come prima cosa l'elemento su cui fare l'injection

````js
const rootElement = document.getElementById('root')
````

E poi andando a usare la funzionalita' di **createElement** per creare un nuovo div e metterci dentro il testo.
La funzione in oggetto, come riportato dalla [documentazione ufficiale](https://it.reactjs.org/docs/react-api.html#createelement) non fa altro che prendere
 come argomenti il Tipo, nel nostro caso un div, le props che nel nostro caso sono un oggetto composto da classe e contenuto

````js
React.createElement(
  type,
  [props],
  [...children]
)
````
quindi diventera' per noi:

````js
const element = React.createElement('div', {
      className: 'container',
      children: 'Stringa fatta con React!',
    })
````
Come ultima cosa andiamo a fare il **render** del nostro elemento passando l'elemeneto come primo argomento e il container che lo deve ospitare

````js
ReactDOM.render(element, rootElement)
````


Il risultato è il seguente:

![fastify_code](/6DCFFC08-646D-4D81-B4C5-A3382C6186CE.jpg)

Questo era solo un esercizio di stile poichè andrò ad usare sempre JSX che si occuperà lui di fare il createElement sotto il cofano.

La prossima volta andremo a fare la stessa cosa utilizzando però **JSX**


*Stay Tuned*
Alex