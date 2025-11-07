
# Node-RED BrazilAPI Demo

> **Requirements** test:
> - **Broker Catalog**: `/brokers` -> lists all brokers from BrazilAPI in the format `${Name} - ${City} / ${CNPJ}`
> - **Zip Code Searcher (CEP)**:
>   - Option 1: `/cep/:cep` (route param)
>   - Option 2: `/cep?cep=01001000` (input via query / simple form at `/cep`)
>
> _Extra_: basic styling with Bootstrap. No company names are mentioned.

## 1. Prerequisites
- Node.js (LTS recommended)  
- npm (bundled with Node.js)  
- Node-RED installed globally:
  ```bash
  npm install -g --unsafe-perm node-red
  ```

## 2. Run
Start Node-RED:
```bash
node-red
```
Open the editor: <http://localhost:1880>

## 3. Import the flows
In the Node-RED editor: **Menu → Import → Select a file** and choose `flows.json` from this repo. Then **Deploy**.

## 4. Endpoints
- **GET /brokers** → BrazilAPI CVM brokers, rendered as HTML list  
- **GET /cep/:cep** → CEP details via route parameter (e.g. `/cep/01001000`)  
- **GET /cep** → HTML form for CEP input (submit as query)
- **GET /cep?cep=01001000** → CEP details via query

## 5. Tech notes
- BrazilAPI docs:
  - Corretoras: <https://brasilapi.com.br/docs#tag/Corretoras>
  - CEP v2: <https://brasilapi.com.br/docs#tag/CEP-V2>
- Styling via CDN: Bootstrap 5.
- No backend persistence required; pure Node-RED flow using `http in`, `http request`, `function`, `template`, and `http response` nodes.

## 6. How to export your own flows (optional)
Node-RED → **Menu → Export → Clipboard → All Flows** and save as `flows.json`.

## 7. Project structure
```
.
├─ flows.json      # Import into Node-RED
└─ README.md       # This file
```

## 8. License
MIT
