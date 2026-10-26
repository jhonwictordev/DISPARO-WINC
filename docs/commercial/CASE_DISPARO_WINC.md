# Case Comercial — DISPARO WINC: Plataforma SaaS de Campanhas e Automação WhatsApp

## PROBLEMA
Empresas varejistas, consultórios, imobiliárias e agências de marketing perdem oportunidades de venda diárias devido à baixa taxa de abertura de e-mails (menos de 20%) e custos proibitivos de SMS tradicional. No entanto, o envio em massa manual pelo WhatsApp resulta em banimento rápido de números telefônicos por algoritmos anti-spam, perda de histórico de conversas e total falta de métricas sobre quem recebeu e quem respondeu às mensagens.

## SOLUÇÃO
O **DISPARO WINC** é uma plataforma SaaS com design moderno *dark neon*, desenvolvida para gerenciar e executar disparos estratégicos no WhatsApp com máxima segurança operacional. A arquitetura combina um painel web central para importação de listas, controle de filas persistentes e relatórios analíticos, a uma extensão para Google Chrome (Manifest v3) que atua como worker de envio cadenciado diretamente na sessão do usuário no WhatsApp Web, simulando comportamento humano com intervalos randômicos.

## FUNCIONALIDADES COMPROVADAS
- **Gerenciamento de Fila Persistente**: Armazenamento seguro de mensagens pendentes em banco de dados local com tolerância a quedas de conexão e recuperação automática.
- **Higienização e Normalização de Listas**: Identificação de números repetidos, formatação com código de país (DDI/DDD) e remoção de caracteres inválidos.
- **Controle de Cadência Anti-Ban**: Algoritmo de temporização com intervalos programáveis e pausas entre lotes para manter o número em conformidade e evitar bloqueios.
- **Worker Desacoplado via Extensão Chrome**: A extensão executa os envios em segundo plano diretamente pela aba ativa do WhatsApp Web, sem requerer servidores caros de emulação de navegador.
- **Dashboard de Métricas em Tempo Real**: Contadores visuais de mensagens entregues, pendentes e com falha, permitindo acompanhamento do progresso da campanha minuto a minuto.

## TECNOLOGIAS VERIFICADAS
- **Backend**: Node.js moderno (ESM), Express, SQLite estruturado para persistência de fila.
- **Frontend**: Dashboard responsivo, estilização personalizada *dark neon* com gráficos e feedback visual imediato.
- **Extensão do Navegador**: Google Chrome Extension (Manifest v3), scripts de injeção de conteúdo seguros.
- **Implantação**: Scripts automatizados de instalação (`install.ps1`, `install.sh`) e Docker Compose.

## DIFERENCIAIS
- **Zero Custo por Mensagem Enviada**: Diferente de brokers oficiais ou APIs terceiras que cobram centavos de dólar por disparo, a operação roda pela própria infraestrutura do cliente.
- **Operação Descentralizada**: O cliente conecta seu próprio WhatsApp Web via extensão, mantendo as conversas salvas no seu aparelho com total privacidade.
- **Interface Intuitiva para Usuários Não Técnicos**: Permite que operadores de telemarketing e recepcionistas operem campanhas sem necessidade de conhecimentos em programação.

## STATUS
**MVP Funcional com Módulo de Extensão Integrado** — Dashboard operacional, modelos de fila persistente estruturados e pacote de extensão Chrome pronto para uso.

## VALOR COMERCIAL
- **Multiplicação de Engajamento**: O WhatsApp possui taxas de abertura superiores a 90%, garantindo retorno imediato em avisos de promoção, cobrança e confirmações.
- **Automação de Confirmação de Consultas e Agendamentos**: Reduz o no-show (faltas) em clínicas médicas, salões e imobiliárias enviando lembretes automáticos na véspera.
- **Recuperação de Vendas**: Permite contatar instantaneamente leads que abandonaram carrinhos em e-commerces com mensagens personalizadas.
