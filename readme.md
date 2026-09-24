# ⇄ Conversor CSV & Excel Pro — 100% Local

Conversor bidirecional **CSV → Excel (.xlsx)** e **Excel (.xlsx/.xls) → CSV** que roda 100% no navegador. Sem upload, sem cadastro, sem servidor.

🌐 **Demo:** `https://<seu-usuario>.github.io/conversor-csv-excel/` *(troque pelo seu usuário após publicar)*
📁 **Arquivo único:** `index.html` (HTML + CSS + JS inline)

---

## ✨ Funcionalidades

- **2 modos:** CSV → XLSX e XLSX/XLS → CSV
- **Parsing robusto:** PapaParse (respeita aspas, quebras de linha, escape `""`) + SheetJS
- **Delimitador automático** (`, ; TAB |`) com detecção + seleção manual
- **Codificação:** UTF-8 / Latin-1 / Windows-1252 na leitura + **toggle BOM** na saída (ideal p/ Excel BR)
- **Pré-visualização única do arquivo a converter:**
  - Tabela com nº da linha, cabeçalho, scroll horizontal
  - Paginação 8 / 15 / 30 / 50 por página (mostra todas as linhas da página, sem corte)
  - Filtro em tempo real + aba **Texto bruto**
  - Contador: `Exibindo N nesta página (Pág A/B) • arquivo • linhas • colunas`
- **Resultado:** estatísticas (linhas, colunas, abas, tamanho), barra de progresso, log com timestamp, download com nome personalizado
- **Seletor de aba** para Excel com múltiplas abas
- **Privacidade:** nada sai do navegador. Limite de segurança 100 MB
- **Acessível:** sem bloqueio de botão direito/cópia/DevTools, `:focus-visible`, `aria-live`, teclado navegável, impressão liberada

## 🚀 Como usar

1. Baixe ou clone o repositório
2. Abra `index.html` no navegador — **ou** sirva localmente:
   ```bash
   npx serve conversor-csv-excel
   # ou
   python -m http.server 8000 --directory conversor-csv-excel
   ```
3. Escolha o modo → arraste o arquivo → confira a pré-visualização → **Converter** → **Baixar**

> Necessita internet na primeira carga (CDNs do SheetJS, PapaParse e Google Fonts). A conversão em si é local.

## 📦 Publicar no GitHub Pages

```bash
git init
git add index.html README.md
git commit -m "feat: conversor csv-excel v3.1"
git branch -M main
git remote add origin https://github.com/<usuario>/conversor-csv-excel.git
git push -u origin main
```

Depois: **Settings → Pages → Deploy from branch → `main` / `/ (root)`**. Aguarde ~1 min e acesse a URL pública.

## 🛠️ Tecnologias

| Lib | Versão (CDN) | Uso |
|---|---|---|
| SheetJS `xlsx` | 0.18.5 (cdnjs) | Ler/gerar `.xlsx`/`.xls` |
| PapaParse | 5.4.1 (cdnjs) | Parse/unparse CSV robusto |
| Google Fonts | Inter | Tipografia |
| Sem build | — | Arquivo único, sem dependência de build |

Paleta: `--bg-dark:#0f172a`, cards `#ffffff`, `--accent-blue:#2563eb`, `--accent-green:#059669`, `--border-light:#e2e8f0`, `--subtitle:#94a3b8`.

## 📂 Estrutura

```text
conversor-csv-excel/
├── index.html   # app completo (único arquivo)
└── README.md    # este arquivo
```

## ⚠️ Limitações conhecidas

- Prévia limitada a 2000 linhas (conversão usa o arquivo completo)
- Arquivos > 100 MB são recusados para não travar a aba
- Excel → CSV exporta **1 aba por vez** (escolha no seletor); formatação/fórmulas viram valores
- CSV → XLSX grava tudo em 1 aba `Dados`, sem preservar tipos avançados
- Se o CDN cair, as libs não carregam (há aviso no log)

## 🗺️ Roadmap

- [ ] Detecção automática de encoding
- [ ] Exportar todas as abas (multi-CSV / ZIP)
- [ ] Web Worker p/ arquivos grandes
- [ ] Arrastar múltiplos arquivos + modo offline (PWA)

## 📄 Licença

MIT — use, modifique e compartilhe livremente.
