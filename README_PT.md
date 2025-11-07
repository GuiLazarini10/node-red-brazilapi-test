# Node-RED BrazilAPI Demo

> **Requisitos do teste:**
> - **Catálogo de Corretoras**: `/brokers` → lista todas as corretoras da BrazilAPI no formato `${Nome} - ${Cidade} / ${CNPJ}`
> - **Buscador de CEP (Zip Code Searcher)**:
>   - Opção 1: `/cep/:cep` (parâmetro na rota)
>   - Opção 2: `/cep?cep=01001000` (campo de formulário simples em `/cep`)
>
> _Extra_: estilo básico com Bootstrap. Nenhuma empresa é mencionada.

---

## 1. Pré-requisitos
- Node.js (versão LTS recomendada)  
- npm (já incluso no Node.js)  
- Node-RED instalado globalmente:
  ```bash
  npm install -g --unsafe-perm node-red
  ```

---

## 2. Como executar
Inicie o Node-RED:
```bash
node-red
```
Abra o editor em: <http://localhost:1880>

---

## 3. Importar os fluxos
No editor do Node-RED:  
**Menu → Importar → Selecionar arquivo** e escolha `flows.json` deste repositório.  
Depois clique em **Deploy**.

---

## 4. Endpoints disponíveis
- **GET /brokers** → lista de corretoras da BrazilAPI em formato HTML  
- **GET /cep/:cep** → busca de CEP via parâmetro de rota (exemplo: `/cep/01001000`)  
- **GET /cep** → formulário HTML para digitar o CEP  
- **GET /cep?cep=01001000** → busca de CEP via query string

---

## 5. Notas técnicas
- Documentação da BrazilAPI:
  - Corretoras: <https://brasilapi.com.br/docs#tag/Corretoras>
  - CEP v2: <https://brasilapi.com.br/docs#tag/CEP-V2>
- Estilização via CDN: Bootstrap 5.  
- Nenhum backend adicional é necessário — o projeto usa apenas nós do Node-RED (`http in`, `http request`, `function`, `template`, `http response`).

---

## 6. Exportar seus próprios fluxos (opcional)
No Node-RED → **Menu → Exportar → Clipboard → Todos os fluxos**  
Salve como `flows.json`.

---

## 7. Estrutura do projeto
```
.
├─ flows.json      # Arquivo para importar no Node-RED
└─ README.md       # Este arquivo
```

---

## 8. Licença
MIT
