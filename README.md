💡 Contexto
A ideia nasceu da experiência acumulada com outros projetos de automação para e-commerce — especialmente após a implementação de painéis de rastreio e BI direto na landing page da loja. A pergunta foi simples: se já temos infraestrutura rodando no GAS, por que não usar o mesmo ecossistema para entregar conteúdo dinâmico ao cliente?

🔄 Como o sistema funciona
1. Coleta de conteúdo (RSS → JSON)
O Google Apps Script realiza requisições periódicas para feeds RSS de portais especializados em fitness, saúde e esporte. O conteúdo retorna em formato XML/JSON e é parseado, normalizado e organizado automaticamente.
2. Google Sheets como banco de dados
Após o processamento, cada notícia é gravada em uma aba da planilha com campos estruturados:

Data de publicação
Título
Resumo
Matéria completa
Categoria
Fonte e URL de origem
URL da imagem

O Sheets funciona como um banco de dados leve, acessível e auditável — sem necessidade de servidor ou banco externo.
3. Google Apps Script como API
O GAS expõe um endpoint via doGet / doPost que retorna os dados da planilha em JSON, separando automaticamente as notícias do dia das edições anteriores.
4. Cloudflare como camada de segurança
A URL real do webapp do GAS nunca fica exposta. O Cloudflare atua como proxy reverso, mascarando a origem e adicionando controle de tráfego.
5. Front-end embarcado na loja
A interface consome o endpoint JSON e renderiza os cards de notícias diretamente no site da loja — responsivo para desktop e mobile, com filtros por categoria e separação por data.

📈 Impacto no negócio
BenefícioComo gera valor🔍 SEOConteúdo novo diariamente sinaliza relevância ao Google🔁 RetençãoCliente tem motivo para voltar ao site além de comprar🏆 AutoridadeLoja se posiciona como referência no segmento⏱️ Tempo na páginaLeitura aumenta o tempo médio de sessão

🛠️ Stack
Google Apps Script Google Sheets Cloudflare RSS/XML JSON HTML CSS JavaScript

⚖️ Direitos Autorais
Todas as notícias exibem a fonte original de publicação, respeitando os direitos autorais dos veículos de comunicação.
