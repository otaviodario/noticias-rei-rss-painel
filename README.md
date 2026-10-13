# 📰 Notícias Rei RSS Painel

---

### 💡 Contexto

A ideia nasceu da experiência acumulada com outros projetos de automação para e-commerce — especialmente após a implementação de painéis de rastreio e BI direto na landing page da loja. 

A pergunta foi simples: **se já temos infraestrutura rodando no GAS, por que não usar o mesmo ecossistema para entregar conteúdo dinâmico ao cliente?**

---

### 🔄 Como o Sistema Funciona

#### 1. Coleta de conteúdo (RSS → JSON)
O **Google Apps Script** realiza requisições periódicas para feeds RSS de portais especializados em fitness, saúde e esporte. O conteúdo retorna em formato XML/JSON e é parseado, normalizado e organizado automaticamente.

#### 2. Google Sheets como banco de dados
Após o processamento, cada notícia é gravada em uma aba da planilha com campos estruturados:
* 📅 Data de publicação
* 🏷️ Título
* 📝 Resumo
* 📄 Matéria completa
* 📂 Categoria
* 🔗 Fonte e URL de origem
* 🖼️ URL da imagem

> *O Google Sheets funciona aqui como um banco de dados leve, acessível e auditável — sem custos e sem necessidade de servidor ou banco de dados externo.*

#### 3. Google Apps Script como API
O GAS expõe um endpoint via `doGet` / `doPost` que retorna os dados da planilha em formato JSON, separando automaticamente as notícias do dia das edições anteriores.

#### 4. Cloudflare como camada de segurança
A URL real do webapp do GAS nunca fica exposta publicamente. O Cloudflare atua como **proxy reverso**, mascarando a origem e adicionando controle e proteção de tráfego.

#### 5. Front-end embarcado na loja
A interface consome o endpoint JSON e renderiza os cards de notícias diretamente no site da loja — 100% responsivo para desktop e mobile, com filtros por categoria e separação por data.

---

### 📈 Impacto no Negócio

| Benefício | Como gera valor |
| :--- | :--- |
| 🔍 **SEO** | Conteúdo novo atualizado diariamente sinaliza relevância aos motores de busca (Google). |
| 🔁 **Retenção** | O cliente ganha um motivo para retornar à loja com frequência, além de apenas comprar. |
| 🏆 **Autoridade** | A marca se posiciona como um portal de referência no segmento. |
| ⏱️ **Tempo de Página** | A leitura de artigos eleva a métrica de tempo médio de sessão do usuário. |

---

### 🛠️ Stack Tecnológica

`Google Apps Script` • `Google Sheets` • `Cloudflare` • `RSS / XML` • `JSON` • `HTML5` • `CSS3` • `JavaScript`

---

### ⚖️ Direitos Autorais

> Todas as notícias exibem a fonte original de publicação e link direto, respeitando integralmente os direitos autorais e propriedade intelectual dos veículos de comunicação produtores do conteúdo.

O que mudou:

1.  Tabela estruturada: O trecho de "Impacto no negócio" que estava quebrado em
    uma frase corrida virou uma tabela legível.
2.  Listas demarcadas: Os campos gravados na planilha foram colocados em lista
    com marcadores (*).
3.  Tags de Stack: A seção de tecnologias foi organizada com separadores visuais
    limpos (•).
4.  Hierarquia visual: Uso de divisores horizontais (---), citações em bloco (>)
    e negrito para destacar termos-chave.
