# Fase2Mercado
Fase 2 do Projeto PUC

Manual de Instruções e Visão Geral do Código do MiniMercado SuperUtil
Este manual serve como um guia abrangente para entender o código-fonte do site do MiniMercado SuperUtil. Ele foi projetado para desenvolvedores, designers e qualquer pessoa que precise compreender a estrutura, funcionalidade e o que o usuário final encontrará ao navegar pela página.

Sumário
Visão Geral do Projeto
Estrutura do Arquivo (HTML)
Estilização (CSS)
Funcionalidades Interativas (JavaScript)
Como Usar/Navegar na Página
Personalização e Desenvolvimento
Considerações Finais
1. Visão Geral do Projeto
O MiniMercado SuperUtil é uma página web estática, desenvolvida em HTML5, CSS3 e JavaScript, com aprimoramentos visuais e de responsividade via Bootstrap 5.3. O objetivo principal é simular a presença online de um minimercado, apresentando seus produtos, serviços, informações de contato, localização e horários de funcionamento. Além disso, a página oferece funcionalidades interativas para agendamento de pedidos e cadastro de clientes.

Principais características:

Design responsivo (via Bootstrap).
Carrossel de imagens para destaque de produtos/promoções.
Listagem de produtos por categoria.
Seção de serviços oferecidos.
Informações de contato, localização e horário de funcionamento.
Formulário de agendamento de pedido (sidebar à esquerda).
Formulário de cadastro de cliente (sidebar à direita).
Relógio dinâmico no rodapé.
2. Estrutura do Arquivo (HTML)
O arquivo HTML (.html) é a espinha dorsal da página, organizando todo o conteúdo.

Seções Principais:
<head>: Contém metadados da página, como charset (codificação de caracteres), viewport (configuração para responsividade em diferentes dispositivos) e o <title> da página ("MiniMercado SuperUtil"). É aqui que os links para o Bootstrap CSS e o arquivo de estilos personalizado (<style>) são importados, garantindo que a página tenha a aparência desejada.
<header>: A barra superior do site, contendo o título principal <h1>MiniMercado SuperUtil</h1> e uma barra de navegação (<nav>) com links âncora para as principais seções da página (Produtos, Serviços, Contato, Localização).
Carrossel (#carouselExample): Uma galeria de imagens rotativas na parte superior da página, criada com componentes do Bootstrap para apresentar destaques visuais do minimercado.
Conteúdo Principal (.main-content-wrapper): Este é o container principal que organiza o layout de três colunas, utilizando Flexbox para:
Sidebar Esquerda (.sidebar-left): Dedicada ao formulário de Agendamento de Pedido.
Conteúdo Central (.container): Contém as seções de:
Produtos (#produtos): Organizados por categorias (Arroz, Feijão, Macarrão), cada produto com imagem, nome, preço e um botão "Comprar" (atualmente apenas visual).
Serviços (#servicos): Detalhes sobre "TeleEntrega" e "Montagem de Cesta Básica".
Contato (#contato): Informações de telefone e e-mail.
Localização (#localizacao): Endereço físico.
Horário de Funcionamento: Informações sobre os horários de abertura.
Formas de Pagamento: Lista das opções de pagamento aceitas.
Sidebar Direita (.sidebar-right): Dedicada ao formulário de Cadastro de Cliente.
<footer>: O rodapé da página, incluindo informações de direitos autorais, o desenvolvedor, links de navegação repetidos e o relógio dinâmico.
3. Estilização (CSS)
O CSS é responsável por toda a aparência visual da página, desde as cores e fontes até o layout e a responsividade.

Recursos Utilizados:
Importação de Fontes: Utiliza a fonte 'Poppins' do Google Fonts para um visual moderno e limpo.
Reset Básico: * { margin: 0; padding: 0; box-sizing: border-box; } garante que todos os elementos comecem com margens e preenchimentos zerados, facilitando o controle do layout.
body: Define a fonte padrão, um gradiente de fundo suave e cores de texto gerais.
header: Estiliza o cabeçalho com fundo escuro (#790000), texto branco e um layout flexível para alinhar o título e a navegação.
nav a: Estilos para os links de navegação, incluindo efeitos de hover para sublinhado.
main-content-wrapper: O elemento chave para o layout de três colunas. Usa display: flex para organizar as sidebars e o conteúdo central lado a lado, com justify-content: space-between para espaçamento automático.
max-width: 1400px: Define a largura máxima do conteúdo principal, centralizando-o na página.
.container: Estiliza a área de conteúdo central com fundo branco, cantos arredondados, sombra e padding interno.
h2, h3: Cores e tamanhos de fonte específicos para os títulos das seções.
.produto, .servico: Estilos para os blocos de produtos e serviços, incluindo fundo branco, sombras, cantos arredondados e layout flexível para alinhar imagens e informações.
button: Estilização genérica para todos os botões, com gradiente de fundo, cantos arredondados e efeitos de hover para transição suave e um pequeno "levante".
footer: Estiliza o rodapé com um fundo claro, texto centralizado e links.
carousel img: Garante que as imagens do carrossel tenham uma altura máxima e preencham o espaço de forma adequada.
Sidebars (.sidebar-left, .sidebar-right):
width: 380px: Define a largura específica das sidebars para que tenham mais espaço.
background-color: white, border-radius, box-shadow: Estilos para o visual e posicionamento das sidebars.
margin-right / margin-left: Adicionam espaçamento entre as sidebars e o conteúdo central.
form-group: Uma classe CSS crucial para agrupar rótulos e inputs, adicionando um espaçamento vertical consistente entre os campos do formulário.
label dentro de form-group: Agora, os rótulos são display: block por padrão, garantindo que cada um fique em sua própria linha e que haja um pequeno margin-bottom para separá-lo do seu input.
input, select, textarea dentro das sidebars: Mantêm width: 100% para preencher o espaço disponível dentro do form-group e têm estilos de padding, borda e border-radius.
input[type="radio"], input[type="checkbox"] e seus respectivos labels: Estilos específicos para que se alinhem horizontalmente, com os labels adjacentes aos seus inputs.
.relogio: Estilo para o texto do relógio no rodapé.
4. Funcionalidades Interativas (JavaScript)
O JavaScript adiciona dinamismo e interatividade à página.

Principais Funções:
Agendamento de Pedido (#formAgendamento):
Ao submeter o formulário de agendamento, o script captura os valores selecionados (tipo de serviço, data e hora).
Um alert() exibe uma mensagem de confirmação com os dados do agendamento.
O formulário é resetado após a submissão.
Atualização do Relógio (#relogio):
A função atualizarRelogio() obtém a hora atual do sistema.
Formata a hora para exibir horas, minutos e segundos (HH:MM:SS).
Atualiza o textContent do elemento com id="relogio" no rodapé a cada segundo usando setInterval(atualizarRelogio, 1000).
Cadastro de Cliente (#formCadastro):
Ao submeter o formulário de cadastro, um alert() simples exibe uma mensagem de "Cadastro realizado com sucesso!".
O formulário é resetado após a submissão.
5. Como Usar/Navegar na Página
Ao acessar a página do MiniMercado SuperUtil, o usuário encontrará:

No topo: O título do minimercado e uma barra de navegação com links para as principais seções da página.
Abaixo do cabeçalho: Um carrossel de imagens que exibe fotos relacionadas a produtos e ao ambiente do mercado.
No centro da tela:
À esquerda, a "Aba de Agendamento de Pedido" onde é possível selecionar um serviço (retirada ou tele-entrega), data e horário para agendar um pedido.
No meio, o "Conteúdo Principal" com:
"Produtos por Categoria": Apresenta Arroz, Feijão e Macarrão com imagens, nomes, preços e botões "Comprar" (funcionalidade de compra não implementada nesta versão).
"Serviços Oferecidos": Detalha a "TeleEntrega" e a "Montagem de Cesta Básica".
"Contato": Telefone e e-mail para contato.
"Localização": O endereço físico do minimercado.
"Horário de Funcionamento" e "Formas de Pagamento".
À direita, a "Aba de Cadastro de Cliente" onde novos clientes podem preencher seus dados como nome, endereço, CPF, sexo, telefone, e-mail, idade e preferências, além de um campo para observações.
No rodapé: Informações de direitos autorais, o desenvolvedor, links de navegação e um relógio em tempo real mostrando o horário atual.
Interações do Usuário:
Navegação: Clicar nos links do cabeçalho ou rodapé levará o usuário para a seção correspondente na página.
Carrossel: Os botões de navegação "Anterior" e "Próximo" permitem controlar a visualização das imagens.
Formulário de Agendamento: Preencher os campos e clicar em "Agendar" exibirá um pop-up de confirmação.
Formulário de Cadastro: Preencher os campos e clicar em "Cadastrar" exibirá um pop-up de confirmação.
6. Personalização e Desenvolvimento
Este código é um ponto de partida. Sinta-se à vontade para personalizá-lo e expandi-lo!

Para Desenvolvedores:
HTML: Adicione novas seções, produtos, serviços ou refine a estrutura existente. Lembre-se de manter a semântica do HTML.
CSS: Modifique cores, fontes, espaçamentos, layouts e efeitos para alterar a identidade visual. As classes CSS estão bem definidas para facilitar a estilização.
Sidebars: Para ajustar a largura das sidebars, modifique o valor de width nas classes .sidebar-left e .sidebar-right.
Alinhamento de Formulários: As classes .form-group e as regras CSS para label, input[type="radio"], input[type="checkbox"] são cruciais para a organização dos formulários. Ao adicionar novos campos, utilize a estrutura div.form-group para manter o alinhamento.
JavaScript:
Validação de Formulários: Implemente validações mais robustas para os campos dos formulários (ex: verificar formato de e-mail/CPF, datas futuras, etc.) antes de exibir os alerts.
Integração Backend: Atualmente, os formulários apenas exibem mensagens. Para torná-los funcionais (ex: salvar agendamentos em um banco de dados, enviar e-mails de cadastro), será necessário integrar com uma linguagem de backend (Node.js, Python, PHP, etc.) e APIs.
Interatividade: Adicione mais funcionalidades interativas, como um carrinho de compras para os produtos, filtros ou busca.
Imagens: Substitua as imagens do carrossel e dos produtos/serviços pelas suas próprias para personalizar o visual.
7. Considerações Finais
Este projeto serve como uma demonstração de como construir uma página web responsiva e interativa usando HTML, CSS e JavaScript, com o auxílio do Bootstrap. É um excelente ponto de partida para quem busca criar uma presença online simples e eficaz para um pequeno negócio.
