---
title: Basic Api Server in Node
tags: nodejs, js, fastify, api
excerpt: Un webserver leggero per prototipare API in maniera istantanea
createdAt: 2021-09-07 16:33:00
---

## Fastify

Dopo anni passati a usare Express ho deciso di migrare a qualcosa di più veloce e pratico e mi sono imbattuto in [Fastify](https://fastify.io).

Ne parlerò più approfonditamente in un altro articolo ma intanto volevo condividere il codice per partire ad usarlo.

Come riportato dalla [documentazione ufficiale](https://www.fastify.io/docs/latest/):

Inizzializare il repository, installare fastify e creare il file vuoto *server.js*

```bash
yarn init --yes
yarn add fastify
touch server.js
```

Inserire nel file **server.js** il seguente codice:

```js
// Require the framework and instantiate it
const fastify = require('fastify')({ logger: true })

// Declare a route
fastify.get('/', async (request, reply) => {
  return { hello: 'world' }
})

// Run the server!
const start = async () => {
  try {
    await fastify.listen(3000)
  } catch (err) {
    fastify.log.error(err)
    process.exit(1)
  }
}
start()
```
E quindi digitare i seguenti comandi per avviare il webserver sulla porta 3000

```bash
node server
```

Il risultato è il seguente:

![fastify_code](/12624DFD-DF1C-40F2-B8DC-DCAAF195D6F0.jpg)

Nei prossimi giorni vediamo come scrivere qualche API che sfrutti a pieno le fuzionalità di Fastify anche in relazione ad Express.

*Stay Tuned*
Alex