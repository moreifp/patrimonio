# Patrimônio

Banco de dados pessoal de bens: imóveis, veículos, contas e evolução do patrimônio. PWA instalável, mobile-first, em português.

## Como funciona
- **Um arquivo só**: `index.html` (HTML + CSS + JS), mais `manifest.json` e os ícones. Sem build — publicar é subir o arquivo.
- **Dados**: ficam no aparelho (IndexedDB) e sincronizam com o Firebase do projeto `patrimonio-fausto` (Firestore para os registros, Storage para os anexos). Login pelo Google.
- **Anexos**: PDF e Word abrem dentro do app (pdf.js e mammoth carregados sob demanda).
- **Extratos**: botão que busca o último extrato de cada conta na API do BTG-Wealth (`btg-wealth.web.app`), com o mesmo login Google.
- **Câmbio**: `open.er-api.com`, atualizado ao abrir.
- **Versão**: constante `APP_VERSAO` no `index.html`. O app compara com a versão publicada e avisa quando há nova versão — **mude a constante a cada publicação**.

## Segurança
- As chaves `apiKey` do Firebase no `index.html` são públicas por natureza; quem protege os dados são as **regras do Firestore e do Storage**, configuradas no console do Firebase (ainda não estão versionadas aqui).
- Nenhum dado pessoal fica neste repositório.

## Regras para trabalhar aqui
- Português do Brasil em tudo. Poucos cliques, pouco texto, ícones grandes. Não mudar o visual sem o Fausto pedir.
- Nunca gravar chave secreta, senha ou token no código.
