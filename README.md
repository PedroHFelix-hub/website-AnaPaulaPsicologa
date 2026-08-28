# Site profissional — Ana Paula Gonçalves, Psicóloga

Site pessoal de **Ana Paula Gonçalves**, psicóloga com abordagem em Terapia Cognitivo-Comportamental (TCC). O projeto apresenta sua atuação e funciona como uma ferramenta de qualificação para o primeiro contato, sem posicionar a Ampla.mente como marca principal.

## Visão do projeto

Criar uma experiência digital acolhedora, clara e ética para que a pessoa certa reconheça se o atendimento individual e online faz sentido para ela antes de entrar em contato. Quando a demanda não se encaixar, o site deve orientar e, quando aplicável, encaminhar para a equipe da Ampla.mente.

## Problema e objetivo

Os contatos recebidos por WhatsApp, Instagram e indicação chegam frequentemente sem contexto, incluindo demandas fora do escopo de atendimento. O objetivo não é aumentar a quantidade de mensagens, mas **qualificar melhor os contatos** e reduzir o tempo gasto antes de um possível agendamento.

Indicadores de sucesso:

- Percentual de contatos que chegam à primeira sessão;
- Tempo médio dedicado a cada contato antes do agendamento.

## Público-alvo

Adultos de **18 a 40 anos**, para atendimento psicológico **individual e online**.

O recorte contempla, em especial:

- Jovens adultos em primeira terapia, com questões de autoconhecimento, relacionamentos, carreira e comparação social;
- Adultos com demandas de relacionamento, propósito, carreira e exaustão;
- Brasileiros no exterior que buscam terapia em português.

Não faz parte do escopo o atendimento a crianças, adolescentes, casais ou famílias.

## Proposta e funcionamento

O conteúdo deve começar pela experiência de quem chega — por exemplo, tristeza, ansiedade, insônia, autoestima ou dificuldades nos relacionamentos — e então apresentar a profissional, a TCC e o atendimento. A linguagem deve ser humana e acolhedora, sem diagnosticar, rotular ou prometer resultados.

O WhatsApp é o canal principal e único de agendamento. Não haverá sistema de agendamento na primeira versão. O site também informa Instagram, horário de resposta e o aviso de que não é um serviço de emergência.

## Escopo da Release 1

- Home;
- Sobre;
- Como funciona a terapia online;
- Perguntas frequentes e conteúdo de acolhimento;
- Contato;
- Página 404.

A Release 1 também inclui identidade e credibilidade da profissional, explicação da TCC, qualificação explícita de público e serviço, seção “para quem este trabalho é”, encaminhamento quando aplicável e informações de segurança para visitantes em crise.

## Releases futuras

- **Triagem:** formulário estruturado para verificar elegibilidade, contextualizar o contato e direcioná-lo ao WhatsApp sem persistir dados;
- **Conteúdo e artigos:** lista e páginas de artigos para SEO e demonstração prática da abordagem.

O documento de descoberta registra quatro releases, mas a alocação final da triagem entre elas deve ser consolidada na próxima etapa do projeto.

## Requisitos e restrições principais

- Mobile-first, com prioridade para tráfego vindo do Instagram;
- Site leve, com imagens otimizadas e boa experiência em conexões limitadas;
- Acessibilidade conforme WCAG 2.1 AA;
- Sem back-end, banco de dados próprio ou persistência de dados nas Releases 1 e 2;
- Rastreamento mínimo e nenhuma análise de campos de formulário;
- HTML semântico e SEO específico para o nicho;
- CRP visível e conferível;
- Sem promessas de resultado, sensacionalismo ou depoimentos de pacientes;
- Conteúdo de segurança com aviso de não emergência e referências a CVV 188, CAPS e SAMU 192.

## Fluxos relevantes

- **Instagram → contato:** home → para quem é → como funciona → WhatsApp;
- **Busca no Google → descoberta:** home → sobre → perguntas frequentes → contato;
- **Indicação → credibilidade:** busca pelo nome → CRP e formação → contato;
- **Brasileiro no exterior:** busca → informações sobre atendimento, fuso e pagamento → contato;
- **Visitante em crise:** acesso rápido a recursos de emergência;
- **Visitante fora do público:** identificação rápida da incompatibilidade e encaminhamento, quando aplicável.

## Princípios de UX, acessibilidade e privacidade

- Projetar a partir de aproximadamente 360 px, com alvos de toque de ao menos 44 px e texto legível sem zoom;
- Usar landmarks semânticos, headings consistentes, contraste AA, navegação por teclado e foco visível;
- Associar labels e mensagens de erro aos campos; usar texto alternativo descritivo e ARIA somente quando necessário;
- Respeitar `prefers-reduced-motion`;
- Tratar informações sobre sofrimento psíquico como dados sensíveis: a triagem futura transmite os dados diretamente ao canal da profissional, sem armazenamento.

## Status e decisões

Decidido:

- O site é pessoal, centrado em Ana Paula; a Ampla.mente é vínculo profissional e possível destino de encaminhamento;
- A abordagem é TCC;
- O atendimento é individual, online, para adultos;
- O WhatsApp é o único canal de agendamento;
- Não haverá sistema de agendamento;
- O projeto seguirá em quatro releases.

Em definição ou confirmação:

- Arquitetura: página única longa ou páginas separadas;
- Stack tecnológica;
- Domínio;
- Política de faltas e remarcação;
- Critérios de expectativa e encaminhamento;
- Informações institucionais que dependem de confirmação da profissional.

## Documentação

A base de decisões deste projeto está em [Etapa 0 — Descoberta do Produto](docs/00-descoberta.md).
