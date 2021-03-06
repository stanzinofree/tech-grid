---
title: Il nostro primo Custom Component
tags: react, js, full-stack, jsx, babel
excerpt: Andiamo a scrivere il nostro primo Component
createdAt: 2021-07-14 10:35:00
---

## Custom Component

Fino ad ora abbiamo giocato con l'Injection di codice Html, ma facciamo un passo avanti verso al potenza di React, creiamo un componente che possiamo utilizzare quante volte vogliamo che ci semplifichi la vita non dovendo riscrivere sempre le stesse cose
Il codice finale sarà:

````html
<body>
  <div id="root"></div>
  <script src="https://unpkg.com/react@16.12.0/umd/react.development.js"></script>
  <script src="https://unpkg.com/react-dom@16.12.0/umd/react-dom.development.js"></script>
  <script src="https://unpkg.com/@babel/standalone@7.8.3/babel.js"></script>
  <script type="text/babel">
    const Banner = (props) => <div className="banner">{props.children}</div>
    const element = (
      <div className="container">
        <Message>Hello World</Message>
        <Message>Goodbye World
          <span>TEXT</span></Message>
      </div>
    )

    ReactDOM.render(element, document.getElementById('root'))
  </script>
</body>

````

Rispetto a prima andiamo ad aggiungere la nostra libreria di Transpiling, quando andremo ad usare l'installazione vera il tutto sarà più veloce perchè invece di fare il transpiling a runtime nel browser verrà
fatto in fase di build in un file js standalone.

````html
<script src="https://unpkg.com/react@17.0.2/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@17.0.2/umd/react-dom.development.js"></script>
<script src="https://unpkg.com/@babel/standalone@7.14.7/babel.js"></script>
````

Ora andiamo a fare la nostra Injection sfruttando al potenza del **JSX** e delle props.
Senza scrivere HTML quindi andiamo a creareci i nostri due elementi *children* e *className* preservando comunque il rootElement


````js
const rootElement = document.getElementById('root')
const children = 'Piacere JSX'
const className = 'propClass'
````

Come abbiamo visto nell'[articolo precedente](https://stanzinofree.tech/articles/starting-learn-react) andiamo a creare il nostro oggetto con *children* e *className* e poi chiamiamo il metodo **render** di ReactDOM

````js
const props = {children, className}
const element = <div {...props} />
ReactDOM.render(element, rootElement)
````
effettivamente andando a guardare la quantità di codice scritto non abbiamo risparmiato molte battiture sulla tastiera ma la struttura utilizzata
permette di poter fare cose come l'aggiunta di elementi o override di altri

````js
const elementAppend = <div id="test" {...props} />
const elementOverride = <div {...props} className="overrided-class"/>
````
Andando a vedere la console di Chrome vedremo che Babel va ad aggiungere al createElement il props _extends con i valori che stiamo passando noi.

Il risultato è il seguente:

![fastify_code](/FD65E903-1589-42A6-9BD6-669CA4235E38.jpg)

La prossima volta andremo a creare un componente Custom

*Stay Tuned*
Alex