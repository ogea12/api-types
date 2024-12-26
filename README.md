# @ogea12/api-types

<div align="center">

![Version](https://img.shields.io/npm/v/@ogea12/api-types?style=for-the-badge&colorA=4c566a&colorB=5382a1&logo=npm&logoColor=white)
![Code Size](https://img.shields.io/github/languages/code-size/ogea12/api-types?style=for-the-badge&colorA=4c566a&colorB=ebcb8b&logo=github&logoColor=white)
![License](https://img.shields.io/github/license/ogea12/api-types?style=for-the-badge&colorA=4c566a&colorB=a3be8c)

</div>

`@ogea12/api-types` est un package permettant d'accéder à la description des types utilisés dans l'API de l'OGEA 12.

## Premiers pas

### Installation

Pour utiliser le package, vous devez d'abord l'intégrer dans votre projet.

```bash
npm install @ogea12/api-types
```

### Usage

Ce dernier peut être ensuite couplé avec les librairies [`openapi-fetch`](https://www.npmjs.com/package/openapi-fetch) et [`openapi-react-query`](https://www.npmjs.com/package/openapi-react-query) afin de bénéficier d'un typage sûr et d'une autocomplétion améliorée pour éviter les erreurs syntaxiques.

```ts
import type { paths } from '@ogea12/api-types'

import createClient from 'openapi-fetch'

const client = createClient<paths>({
  baseUrl: 'https://test.ogea12.com/api',
  headers: {
    Accept: 'application/json',
  },
})

const {
  response,
  data, // Seulement présent avec une réponse 2XX
  error, // Seulement présent avec une réponse 4XX ou 5XX
} = await client.GET('/v1/auth/ping')
```
