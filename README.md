# Reporta Aí Protótipo

O "Reporta Aí" é um protótipo de aplicativo cívico inovador que utiliza o poder da Inteligência Artificial para simplificar e otimizar o processo de reporte de problemas urbanos. Ao invés de depender apenas da entrada manual do usuário, o "Reporta Aí" emprega uma arquitetura sofisticada baseada em múltiplos Agentes de IA para analisar informações fornecidas (imagens e descrições), identificar automaticamente o tipo de problema e o órgão responsável, buscar informações de contato relevantes, gerar um relatório completo e, de forma inovadora, criar conteúdo estratégico para redes sociais. O objetivo é não apenas reportar o problema, mas também aumentar sua visibilidade e engajar a comunidade para uma resolução mais rápida.

![Image](https://github.com/user-attachments/assets/6831657a-2eb9-4273-a79d-9a40754238ed)

**Principais Funcionalidades:**

* **Classificação Inteligente de Problemas:** Um Agente de IA analisa imagens e descrições fornecidas pelo usuário para classificar automaticamente o tipo de problema urbano (buraco, vazamento, poste caído, etc.) e identificar o órgão ou empresa responsável por sua solução.
* **Busca Dinâmica de Contatos:** Utilizando a localização do problema e o responsável identificado, um Agente de IA com acesso à pesquisa online (Google Search) busca dinamicamente informações de contato relevantes, como e-mail e telefone.
* **Geração Automatizada de Relatórios:** Um Agente de IA formata as informações coletadas (tipo de problema, descrição, localização, contatos) em um relatório estruturado e simula o envio deste por e-mail ao órgão responsável.
* **Criação de Conteúdo para Redes Sociais:** Um Agente de IA especializado analisa o problema reportado e gera automaticamente sugestões de texto envolventes para publicações em plataformas como o Instagram. Estas publicações podem incluir a imagem do problema, menção ao responsável (quando encontrado) e hashtags relevantes, visando aumentar o engajamento público e a pressão social para a resolução.
* **Chat Livre com Gemini Flash 2.0:** Os usuários podem interagir diretamente com o modelo Gemini Flash 2.0 para explorar suas capacidades e obter respostas para diversas perguntas.

A arquitetura do "Reporta Aí" é baseada em uma colaboração de múltiplos Agentes de IA especializados, cada um otimizado para uma etapa específica do fluxo de trabalho, resultando em um sistema mais inteligente, eficiente e com maior potencial de impacto cívico.

## 2. Arquitetura do Protótipo:

O "Reporta Aí" utiliza uma arquitetura modular baseada em múltiplos Agentes de Inteligência Artificial (IA), cada um com uma função específica dentro do fluxo de reporte de problemas urbanos. Essa abordagem permite uma especialização das tarefas, otimizando a eficiência e a inteligência do sistema. Os principais agentes que compõem a arquitetura do protótipo são:

* **Agente Classificador:**
    * **Responsabilidade:** Analisar a imagem e a descrição fornecidas pelo usuário para identificar o tipo de problema urbano (por exemplo, buraco, vazamento de água, poste caído, acidente, incêndio, animal ferido) e determinar qual órgão ou empresa é o principal responsável pela sua resolução (por exemplo, Prefeitura, Companhia Elétrica, Companhia de Abastecimento de Água, SAMU, Corpo de Bombeiros, ONGs de Proteção Animal).
    * **Entrada:** Link da imagem do problema (no protótipo, simulando a futura captura via câmera do smartphone) e uma descrição textual opcional. Em uma versão oficial, espera-se que a localização via GPS seja integrada automaticamente no momento da captura da imagem, fornecendo dados precisos para o órgão responsável.
    * **Saída:** Classificação do tipo de problema e o nome do responsável identificado.

* **Agente Buscador:**
    * **Responsabilidade:** Utilizar o nome do responsável identificado pelo Agente Classificador e a localização do problema fornecida pelo usuário para buscar informações de contato relevantes. Este agente utiliza a ferramenta de pesquisa online Google Search para encontrar e-mails e telefones de contato do órgão ou empresa responsável na área especificada.
    * **Entrada:** Nome do responsável e a localização do problema (endereço ou coordenadas).
    * **Saída:** E-mail de contato (se encontrado), telefone de contato (se encontrado) e a cidade da localização.

* **Agente Reporte\_Final:**
    * **Responsabilidade:** Consolidar todas as informações coletadas pelos agentes anteriores (tipo de problema, descrição, localização, link da imagem, e-mail e telefone do responsável) para gerar um relatório formal. Este agente simula o processo de envio de um e-mail para o contato do responsável, utilizando um modelo predefinido com as informações relevantes do reporte.
    * **Entrada:** Tipo de problema, descrição, localização, link da imagem, e-mail do responsável e telefone do responsável.
    * **Saída:** Simulação do conteúdo do e-mail enviado ao responsável.

* **Agente Redator\_Redes\_Sociais (Anteriormente Redator\_Instagram):**
    * **Responsabilidade:** Analisar a imagem do problema, o responsável identificado e a cidade para gerar automaticamente uma sugestão de texto envolvente para publicações em diversas plataformas de redes sociais (como Instagram e X). O objetivo é criar uma mensagem informativa e com potencial de engajamento, direcionada ao responsável, buscando aumentar a visibilidade do problema e a pressão social para a resolução. Este agente também pode pesquisar o perfil do responsável nas redes sociais para incluí-lo na postagem.
    * **Entrada:** Link da imagem do problema, nome do responsável e a cidade da localização.
    * **Saída:** Sugestão de texto para a publicação em redes sociais.

    **Integração com Gemini e Potencial Futuro:**

    Além do fluxo principal de reporte, o "Reporta Aí" explora a integração direta com o modelo de linguagem Gemini. Esta funcionalidade pode ser utilizada de diversas maneiras no futuro:

    * **Chatbot Interativo:** Para fornecer suporte ao usuário, responder perguntas frequentes e auxiliar na criação de reportes mais detalhados.
    * **Análise Inteligente de Problemas:** Permitir que o usuário envie imagens de situações potencialmente perigosas, e o aplicativo, utilizando o Gemini e a busca online, possa identificar possíveis soluções preventivas ou alertar sobre riscos em tempo real.
    * **Monitoramento Ativo:** No futuro, o aplicativo poderia implementar tarefas agendadas para monitorar informações online (notícias, redes sociais) sobre possíveis acidentes ou catástrofes em áreas próximas ao usuário, emitindo alertas proativos quando relevante.

    **Fluxo de Interação:**

    1.  O usuário fornece uma imagem do problema (via link no protótipo, futuramente via câmera com localização automática), uma descrição opcional e a localização.
    2.  O **Agente Classificador** analisa a imagem e a descrição para identificar o tipo de problema e o responsável.
    3.  O **Agente Buscador** utiliza o responsável identificado e a localização para pesquisar informações de contato (e-mail e telefone).
    4.  O **Agente Reporte\_Final** utiliza todas as informações para simular o envio de um e-mail de reporte.
    5.  (Opcional) O **Agente Redator\_Redes\_Sociais** gera uma sugestão de post para diversas plataformas.

    Este fluxo de trabalho, aliado ao potencial de integração com o Gemini, demonstra a capacidade do "Reporta Aí" de evoluir para uma ferramenta cívica abrangente e proativa.

## 3. Tecnologias Utilizadas:

O desenvolvimento do protótipo "Reporta Aí" envolveu a utilização das seguintes tecnologias e bibliotecas:

* **Python:** A linguagem de programação principal utilizada para a implementação da lógica dos Agentes de IA e a orquestração do fluxo de trabalho. Sua versatilidade e o rico ecossistema de bibliotecas para aprendizado de máquina e interação com APIs a tornaram uma escolha ideal.
* **Google AI Python SDK (`google-genai`):** Esta biblioteca oficial do Google permite a interação com os modelos de linguagem generativa do Google AI, incluindo o Gemini Flash 2.0 (utilizado na maior parte do protótipo pela sua flexibilidade e acesso gratuito) e o Gemini 2.5 Pro (utilizado especificamente na geração do código HTML, onde demonstrou melhor desempenho na interpretação de referências visuais). Em versões futuras do aplicativo, diferentes versões do Gemini poderão ser empregadas de acordo com a especialidade de cada Agente (por exemplo, modelos mais avançados para análise de imagens).
* **Google ADK (Agent Development Kit) (`google-adk`):** Esta biblioteca fornece as ferramentas e abstrações necessárias para a criação, configuração e execução dos Agentes de IA de forma estruturada e eficiente. Ela simplifica o desenvolvimento de sistemas multiagente, como o que implementamos no "Reporta Aí".
* **Google Search Tool (`google.adk.tools.google_search`):** Integrada ao Google ADK, esta ferramenta permite que os Agentes de IA realizem pesquisas em tempo real no Google, sendo crucial para o `Agente Buscador` encontrar informações atualizadas de contato dos órgãos responsáveis.
* **`IPython.display`:** Módulo utilizado no ambiente Google Colaboratory para exibir conteúdo HTML e Markdown de forma formatada, facilitando a visualização dos resultados e a criação da interface web simulada.
* **`datetime`:** Biblioteca padrão do Python para manipulação de datas e horas, que pode ser útil em futuras funcionalidades como o agendamento de tarefas de monitoramento.
* **`textwrap`:** Biblioteca padrão do Python utilizada para formatar a saída de texto, como a indentação em blocos de Markdown.
* **`requests`:** Biblioteca Python para fazer requisições HTTP, que pode ser utilizada para acessar links de imagens da web ou interagir com outras APIs no futuro.
* **HTML, CSS e JavaScript:** Utilizados para criar a interface web simulada (presente na célula 15 do Colab). O HTML define a estrutura da página, o CSS estiliza os elementos visuais, e o JavaScript fornece interatividade básica no frontend, como a navegação entre as telas simuladas.
* **Font Awesome:** Uma biblioteca de ícones utilizada na interface HTML para fornecer elementos visuais intuitivos (como os ícones de câmera e checkmark).
* **Google Colaboratory:** O ambiente de desenvolvimento em nuvem onde o protótipo foi construído e testado, oferecendo acesso facilitado às bibliotecas do Google AI e GPUs para computação.

**Observação sobre o Desenvolvimento:**

É importante ressaltar que o presente protótipo foi desenvolvido em um período de apenas dois dias. Devido a essa restrição de tempo, a funcionalidade de captura de imagens em tempo real pela câmera do usuário não foi implementada. Em vez disso, o protótipo utiliza links de imagens da web para simular a entrada de dados visuais. Em futuras iterações e em uma versão oficial do aplicativo, a integração com a câmera do smartphone e a captura automática da localização via GPS no momento do reporte são funcionalidades planejadas para fornecer informações mais precisas e contextuais aos órgãos responsáveis.

## 4. Como Funciona (Fluxo do Usuário):

O "Reporta Aí" oferece duas formas principais de interação para o usuário no protótipo atual: através da execução das células de código Python no Google Colaboratory e através da interface web simulada (presente na célula 15).

**Interação via Google Colaboratory (Backend com Agentes de IA):**

1.  **Escolha do Cenário de Teste:** O usuário é apresentado a um menu com diferentes opções para testar o protótipo:
    * **Exemplos Estáticos (Opções 1-4):** Ao escolher uma dessas opções, dados predefinidos de um problema urbano (link da imagem, descrição e localização) são carregados automaticamente.
    * **Fornecer Seus Próprios Dados (Opção 5):** O usuário pode inserir manualmente o link de uma imagem, uma descrição do problema e a localização desejada.
    * **Chat com Gemini Flash 2.0 (Opção 6):** Permite uma conversa livre com o modelo de linguagem Gemini Flash 2.0 para explorar suas capacidades.
    * **Sair (Opção 7):** Encerra a interação.

2.  **Processamento pelos Agentes de IA (Opções 1-5):** Ao selecionar uma das opções de reporte (1-5), o seguinte fluxo é executado:
    * O **Agente Classificador** recebe o link da imagem e a descrição (se houver) e tenta identificar o tipo de problema e o órgão responsável. O resultado da classificação é exibido no Colab.
    * O **Agente Buscador** utiliza a localização fornecida e o responsável identificado para pesquisar informações de contato (e-mail e telefone) do órgão responsável através da Google Search. Os resultados da busca (e-mail, telefone, cidade) são mostrados no Colab.
    * O usuário tem a opção de simular o envio de um e-mail para o contato encontrado através do **Agente Reporte\_Final**. O conteúdo simulado do e-mail é exibido no Colab.
    * O usuário também tem a opção de gerar uma sugestão de post para redes sociais através do **Agente Redator\_Redes\_Sociais**. O texto sugerido é exibido no Colab.

3.  **Chat Livre com Gemini (Opção 6):** Ao escolher esta opção, o usuário pode interagir diretamente com o modelo Gemini Flash 2.0, digitando prompts e recebendo respostas textuais.

**Interação via Interface Web Simulada (Frontend):**

1.  **Tela Inicial:** O usuário é apresentado a uma tela inicial com o logo do "Reporta Aí" e dois botões principais: "Interagir com o Gemini (via Colab)" e "Enviar Reporte". O primeiro botão informa que a interação direta com o Gemini ocorre via Colab, enquanto o segundo direciona para a tela de reporte.

2.  **Tela de Reporte:** Nesta tela, o usuário pode visualizar uma área de simulação de upload de imagem (atualmente apenas visual, sem funcionalidade real de upload), um campo para inserir a descrição do problema e um campo para a localização. Há também um botão "Buscar localização" (sem funcionalidade implementada) e um botão "Classificar problema". Ao clicar em "Classificar problema", dados fixos são utilizados para simular a classificação (tipo de problema e responsável) e a tela de resumo é exibida.

3.  **Tela de Resumo:** Exibe uma imagem de exemplo do problema, a descrição fornecida (ou um texto padrão), o responsável simulado e a localização (ou um texto padrão). Um botão "Contactar Responsáveis" permite navegar para a tela de envio.

4.  **Tela de Enviado:** Simula a confirmação do envio do reporte. Exibe uma mensagem de sucesso e os detalhes do reporte (assunto, tipo de problema, descrição, localização, imagem de exemplo e informações de contato do responsável - dados fixos para simulação).

**Observação:** É importante notar que a interface web (HTML, CSS e JavaScript) presente na célula 15 é uma simulação visual do que um futuro aplicativo poderia parecer. A lógica principal de processamento dos dados utilizando os Agentes de IA (classificação, busca, geração do reporte e sugestão de post) ocorre no backend, através da execução do código Python no Google Colaboratory. A interação via Colab demonstra a funcionalidade completa dos agentes, enquanto a interface web oferece uma visão da experiência do usuário em um aplicativo real.

## 5. Como Executar o Protótipo:

Para experimentar o protótipo "Reporta Aí", siga os passos abaixo utilizando o Google Colaboratory:

1.  **Acesso ao Google Colab:** Abra um navegador web e acesse o Google Colaboratory (colab.research.google.com). Você precisará de uma conta Google para utilizar o Colab.
2.  **Abrir o Notebook:** Você pode abrir este notebook diretamente no Colaboratory. Caso o tenha salvo em seu Google Drive, vá em "Arquivo" -> "Abrir notebook" e selecione o arquivo. Se estiver visualizando-o no GitHub, o Colab geralmente oferece uma opção para abrir notebooks diretamente do GitHub.
3.  **Configurar a API Key do Google Gemini (Célula 3):**
    * Para que o protótipo possa interagir com os modelos Gemini, é necessário configurar uma API Key do Google AI.
    * **Obter a API Key:** Siga as instruções na documentação do Google AI para obter uma API Key.
    * **Armazenar a API Key:** A célula 3 do notebook utiliza o `google.colab.userdata.get('GOOGLE_API_KEY')` para acessar a API Key armazenada de forma segura no Colab. Você precisará adicionar sua API Key aos "dados do usuário" do Colab. Para fazer isso:
        * No menu lateral esquerdo do Colab, procure pelo ícone de chave (geralmente chamado de "Segredos" ou "Dados do usuário").
        * Clique no ícone e adicione uma nova entrada com o nome `GOOGLE_API_KEY` e cole sua API Key no campo de valor.
        * Clique em "Salvar".
    * **Executar a Célula:** Execute a célula 3 (`# Configura a API Key do Google Gemini`) para que a variável de ambiente `GOOGLE_API_KEY` seja configurada.

4.  **Executar as Células de Código Python (Células 4-14):** Execute sequencialmente as células de código Python desde a célula 4 até a célula 14. Estas células instalam as bibliotecas necessárias (`google-genai` e `google-adk`), configuram o cliente da SDK do Gemini e definem as funções dos diferentes Agentes de IA (`agente_classificacao`, `agente_buscador`, `agente_final_de_rerpote`, `agente_redator_redes_sociais`) e as funções auxiliares.

5.  **Interagir com o Protótipo (Célula 14):** A célula 14 contém o código principal para interagir com os Agentes de IA e a opção de chat com o Gemini. Ao executar esta célula, você verá um menu de opções:

    * **Opções 1-4 (Exemplos Estáticos):** Digite o número correspondente ao exemplo que deseja testar. O protótipo carregará os dados predefinidos (imagem simulada via link, descrição, localização) e os processará através dos Agentes de IA. Você pode modificar os links das imagens utilizadas nestes exemplos estáticos editando os valores dentro do dicionário `exemplos_staticos` na célula 12. Para um funcionamento ideal da busca de contatos, certifique-se de que o campo `localizacao` contenha pelo menos o nome da cidade do problema. Você verá no output do Colab os resultados da classificação, da busca de contatos, a simulação do e-mail e a sugestão de post para redes sociais.
    * **Opção 5 (Fornecer Seus Próprios Dados):** Digite `5` e siga as instruções para inserir o link de uma imagem, a descrição do problema e a localização. Estes dados serão então processados pelos Agentes. Novamente, inclua pelo menos a cidade na localização para otimizar a busca de contatos.
    * **Opção 6 (Conversar com o Gemini Flash 2.0):** Digite `6` para entrar em uma sessão de chat direto com o modelo Gemini Flash 2.0. Você poderá digitar suas perguntas e receber respostas até digitar "sair".
    * **Opção 7 (Sair):** Digite `7` para encerrar a execução do protótipo.

6.  **Visualizar a Interface Web Simulada (Célula 15):** A célula 15 contém o código HTML, CSS e JavaScript da interface web simulada. Ao executar esta célula, você verá um output formatado com a interface visual do aplicativo. Esta interface é interativa, permitindo navegar entre as telas (inicial, reporte, resumo, enviado) clicando nos botões. No entanto, lembre-se que a lógica de processamento avançada com IA (classificação, busca, etc.) não está implementada diretamente nesta interface e é simulada com dados fixos para demonstração visual. A funcionalidade completa dos Agentes de IA pode ser experimentada através da interação direta com o código Python na célula 14.

Ao seguir estes passos, você poderá experimentar as funcionalidades do protótipo "Reporta Aí", observar como os Agentes de IA processam diferentes cenários de problemas urbanos e interagir diretamente com o modelo Gemini.

## 6. Próximos Passos (Manter e Adaptar):

O protótipo "Reporta Aí" demonstra o potencial da Inteligência Artificial na automatização e otimização do processo de reporte de problemas urbanos. Para evoluir este protótipo em uma aplicação funcional e de impacto real, diversos passos futuros podem ser considerados:

* **Aprimoramento dos Agentes de IA:**
    * **Classificação Mais Precisa:** Treinar o Agente Classificador com um conjunto de dados mais amplo e diversificado de imagens e descrições para aumentar a precisão na identificação de diferentes tipos de problemas e dos órgãos responsáveis. Explorar o uso de modelos de visão computacional mais avançados.
    * **Busca de Contatos Inteligente:** Refinar o Agente Buscador para priorizar fontes de informação mais confiáveis e recentes, além de lidar com casos onde as informações de contato não estão facilmente disponíveis (por exemplo, buscar em páginas de ouvidoria, redes sociais oficiais, etc.).
    * **Geração de Relatórios Personalizados:** Permitir a personalização dos relatórios com informações adicionais fornecidas pelo usuário e adaptar o formato para diferentes órgãos.
    * **Engajamento em Redes Sociais Estratégico:** Aprimorar o Agente Redator de Redes Sociais para criar posts mais persuasivos, com hashtags relevantes e estratégias de menção para aumentar o engajamento e o alcance das publicações.

* **Implementação de Funcionalidades Essenciais:**
    * **Integração com a Câmera e GPS:** Implementar a funcionalidade de captura de imagens diretamente da câmera do smartphone e a obtenção automática da localização via GPS no momento do reporte.
    * **Interface de Usuário (UI) e Experiência do Usuário (UX) Nativa:** Desenvolver uma interface de usuário intuitiva e agradável para uma experiência de usuário fluida e eficiente.
    * **Sistema de Autenticação e Perfil do Usuário:** Implementar um sistema de autenticação para que os usuários possam criar perfis, acompanhar seus reportes e receber atualizações.
    * **Sistema de Notificações:** Enviar notificações aos usuários sobre o status de seus reportes.
    * **Mecanismo de Feedback:** Implementar um sistema para que os usuários possam fornecer feedback sobre a precisão das classificações, a utilidade dos contatos e a resolução dos problemas.

* **Tratamento de Falhas e Casos Excepcionais:**
    * **Lidar com Classificações Ambíguas:** Desenvolver mecanismos para lidar com casos em que o tipo de problema ou o responsável não podem ser identificados com clareza, talvez solicitando mais informações do usuário ou apresentando opções.
    * **Contatos Indisponíveis:** Melhorar a estratégia para lidar com a falta de informações de contato diretas, talvez sugerindo outras formas de contato (redes sociais, ouvidorias gerais).

* **Integração com Órgãos Públicos:**
    * No longo prazo, buscar a integração direta com os sistemas de gestão de ocorrências dos órgãos públicos, permitindo o envio automático dos reportes e o acompanhamento do status de resolução.

* **Escalabilidade e Manutenção:**
    * Considerar a arquitetura e a infraestrutura necessárias para escalar o aplicativo para um grande número de usuários e garantir a manutenção contínua dos Agentes de IA e do sistema.

* **Aspectos Éticos e de Privacidade:**
    * Garantir a privacidade dos dados dos usuários e o uso ético da Inteligência Artificial, evitando vieses nos modelos e garantindo a transparência do sistema.

A manutenção e a adaptação do "Reporta Aí" exigirão um esforço contínuo de desenvolvimento, testes e coleta de feedback dos usuários. A flexibilidade da arquitetura baseada em Agentes de IA permitirá a incorporação de novas funcionalidades e o aprimoramento dos componentes existentes de forma modular e eficiente.
