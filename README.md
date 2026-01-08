# Blog da Evolv

## 📋 Descrição
Blog da Evolv é uma interface front‑end estática que consome uma API REST pública (api-fake-blog.onrender.com) para listar e exibir postagens. A aplicação é implementada com AngularJS 1.x, Bootstrap (via CDN) e CSS customizado, oferecendo um layout responsivo com cards de publicações e visualização de postagem individual.

## ✨ Funcionalidades
* Listagem de publicações em cards com título, descrição curta, autor e data.
* Visualização detalhada de uma postagem ao clicar em "LER MAIS".
* Navegação de volta à lista de publicações.
* Estilização responsiva e tema escuro/dourado.
* Consumir API REST via $http (GET) — lógica central em app.js.
* Sem dependências de build (puro HTML/CSS/JS), pronto para servir como site estático.

## 🚀 Tecnologias Utilizadas
* HTML5, CSS3 e JavaScript
* AngularJS 1.4.9 (cliente) — controller único para consumo REST
* Bootstrap 5 (CDN) — layout e componentes responsivos
* Arquivos principais:
  - index.html — estrutura e marcação
  - app.js — lógica de consumo da API e controle de estados (AngularJS controller)
  - style.css — estilo visual e customizações

## 📦 Instalação
O projeto é estático — não há build. Você pode abrir localmente ou servi‑lo por um servidor HTTP simples.

```bash
# clonar repositório
git clone https://github.com/Paulo-H-B/Blog-Evolv.git
cd Blog-Evolv

# abrir localmente (opção rápida)
# - abra index.html diretamente no navegador (file://)
# OU (recomendado) servir via HTTP:

# Python 3
python3 -m http.server 8000

# Node (serve)
npx serve .

# Live server (opcional)
npm install -g live-server
live-server
Abra http://localhost:8000 (ou a URL fornecida pela ferramenta de server) no navegador.

💻 Como Usar
Com o servidor rodando, acesse a página principal — a lista de publicações será carregada automaticamente via requisição HTTP.
Clique em "LER MAIS" em qualquer card para abrir a visualização da postagem individual.
Use o botão de voltar (implementado na UI) para retornar à lista.
Configuração da API:

Endpoints utilizados (definidos em app.js):
GET https://api-fake-blog.onrender.com/postagens — lista de publicações
GET https://api-fake-blog.onrender.com/postagem/{id} — detalhe da publicação
Para apontar para outra API, edite app.js (substitua a URL base). Garanta que a API permita CORS para que o navegador consiga realizar as requisições.
Exemplo de alteração rápida (app.js):

JavaScript
// alterar BASE_URL conforme seu backend
const BASE_URL = 'https://api-fake-blog.onrender.com';
$http.get(`${BASE_URL}/postagens`)...
Considerações técnicas:

A aplicação depende de recursos externos via CDN (AngularJS e Bootstrap). Em ambientes corporativos ou produção, considere hospedá‑los localmente ou usar versões empacotadas.
Tratamento de erros já possui logs no console; recomenda‑se exibir mensagens de erro amigáveis ao usuário em produção.
Verifique políticas de CORS do backend ao conectar APIs externas.
🎯 Objetivo do Projeto
Este projeto serve como protótipo e material educacional para demonstrar:

Consumo de APIs REST em uma Single Page Application simples.
Estruturação rápida de interface com AngularJS e Bootstrap.
Boas práticas de layout responsivo e separação de responsabilidades (HTML/CSS/JS). É adequado como base para migrar para frameworks modernos (React/Vue/Angular) ou para integrar a um backend real.
