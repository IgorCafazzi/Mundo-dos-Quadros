# Mundo-dos-Quadros 🎨 🖼️

<h1>Integrantes</h1>
Bruno Queiroz Plata <br>
Igor Cafazzi <br>
Hudson Araujo <br>
Henrique Kenji <br>

<h1>Introdução ao Jogo</h1>

 Nossa ideia é um jogo de ação e plataforma 3D ambientado na São Paulo contemporânea. O jogador inicia sua jornada na Avenida Paulista e explorarando um beco, encontra o MASP. Ao entrar no museu, ele embarca em uma aventura dentro da pintura "A Cidade Iluminada" de Antonio Bandeira, que reflete a metamorfose de São Paulo atual. Dentro do quadro, o jogo se transforma em uma plataforma, onde os principais inimigos são fantasmas repreentando "falhas" na pintura. Após superar duas fases desafiadoras, o jogador consegue escapar. O jogo é inspirado em títulos como Crash Bandicoot, Super Mario Bros. Wonder, Super Mario Odyssey e Epic Mickey. O jogo também utiliza músicas nas fases sendo elas "são paulo, são paulo" do Premê, "Construção" do Chico Buarque, "Luzes" de Arnaldo Antunes e por último "Águas de Março" de Elis Regina e Tom Jobim


<hr>

<h2>PERSONAGEM</h2>

Nosso protagonista Marquinhos é um jovem de 17 anos que estava andando pela paulista. O modelo do marquinhos tem um esilo cartoon em 3d, usando uma camisa verde, calças e suspensorios azuis e cabelo loiro. O viual dele no geral transmite um visual simples porém moderno, misturando fantasia com modernismo.
<br>

asset do Marquinhos: (https://assetstore.unity.com/packages/3d/characters/kids-character-free-242192)


Colisão: Usamos um character controller para fazer a Movimentação do personagem. Esse componente permite controlar o movimento sem a necesidade de aplicar física diretamente. Com o character Controller podemos fazer uma movimentação mais suave, evitando problemas comuns como colisões incorretas e perda de controle do personagem.

<br>

![character](https://github.com/user-attachments/assets/c1fc80e1-f5ef-4d8c-85a8-0745a61031d1)

Na Movimentação usamos esse script de C# <br>
script:

![movi](https://github.com/user-attachments/assets/e1c90c0f-f7f7-4768-9b96-f32792c0f2a0)

Camera: Na camera usamos a ferramenta Cinemachine no unity, usando a opção <strong>Free Look Camera</strong>, com ela conseguimos fazer uma camera em 3°pessoa que segue o jogador colocando as opções "follow" e "look at" para seguir o objeto com tag "player", trazendo assim um movimento suave para a camera permitindo o jogador rotacionar a camera em volta do personagem. <br>
imagem:

![Screenshot_20240918_150240_YouTube.jpg](https://github.com/user-attachments/assets/15a65cc0-01ae-435f-91ca-6f88c6eb3847)


Checkpoint: Para implementação de um sistema de respawn colocamos um GameObject cubo invisivel com tag "respawn" onde o jogador devia respawnar, assim o jogador não corre o risco de errar o pulo e ficar preso no void do unity, por que quando ele passa -20f no eixo y ele é chamdo denovo a posição do cubo com tag "respawn". Isso impede de trazer uma gameplay frustrante e punitiva, afinal mesmo que ele erre ele ainda vai ser chamado ao checkpoint. <br>
Script:

![IMG-20240919-WA0057.jpg](https://github.com/user-attachments/assets/19a42be7-0fee-4272-a0c7-e89d7fce70e7)

<hr>

<h2>CENA 1- MENU</h2>
Para o menu principal do jogo, usamos 2 botões que deixaram ele interativo. Botão 1: "Jogar". Ao clicar nesse botão, ocorre uma troca de cena que direciona o player para a cena 2- Avenida Paulista. <br>
Script: 

![trocadecena](https://github.com/user-attachments/assets/fa0f4fa6-5302-465f-b77e-787ae3b065e3)

O outro botão é o de "Sair". Ao clicar nele, o jogo fecha. <br>
Script:

![Screenshot_20240918_114143_Chrome.jpg](https://github.com/user-attachments/assets/29075cdd-fae6-437e-8271-47bf6a168910)

Para a imagem de fundo criamos um painel, pegamos a imagem, deixamos como sprite e aplicamos nos painel. <br> Imagem:

![WhatsApp Image 2024-09-18 at 18 03 33](https://github.com/user-attachments/assets/6b81e950-3d56-4aed-8dc5-8f9472af45aa)

<hr>

<h2>CENA 2- AVENIDA PAULISTA</h2>

![tudo-sobre-avenida-paulista.jpg](https://github.com/user-attachments/assets/8cd0252c-ad73-4d71-97ba-e55474288531)

Na primeira cena o jogador andando pela Avenida Paulista,encontra o MASP, sobe as escadas e, ao encostar na porta, é levado para a próxima fase. Utilizamos assets urbanos para representar São Paulo e modificamos o MASP no Blender para abrir um caminho acessível. A Avenida Paulista foi criada com ruas largas e prédios altos. Posicionamos o MASP no fim de um beco para causar estranheza, e a transição de cenas foi realizada utilizando um código c#. <br>
script:


<br>
asset City Voxel Pack: (https://assetstore.unity.com/packages/3d/environments/urban/city-voxel-pack-136141)
<br>
asset do MASP: (https://sketchfab.com/3d-models/masp-museu-de-arte-de-sao-paulo-simplificado-7eb9d1c77f9b43b088128fc5baa249bb)

barricadas:
(https://assetstore.unity.com/packages/3d/props/street-props-prototype-collection-291021)

<hr>

<h2>CENA 3- MASP</h2>
Já no Masp usamos o asset do masp novamente para representar uma sala com diversos quadros emoldurados acima de um cubo (asset dos quadros: https://assetstore.unity.com/packages/3d/props/interior/picture-frames-with-photos-106907), tal qual como realmente é no Masp. <br>

![Museu-Masp-Sao-Paulo-18](https://github.com/user-attachments/assets/4d610717-a904-41e9-b753-de743bcb1091)

<br>
No final do corredor o jogador encontra o quadro da Cidade Iluminada, ao encostar nele o jogador sera teletransportado para a próxima cena. Ao lado desse quadro está o inspetor que tem falas.

o inspetor usa um collisor de cubo para quando o jogador entrar em contato ativar o painel de fala dele, assim mostrando a fala do inspetor. essa mecânica também é usada quando Marquinhos vê o masp na Avenida Paulista.

![IMG-20240919-WA0055.jpg](https://github.com/user-attachments/assets/ae3be496-e3d6-4571-930e-10455e30c9a3)

<br>
asset: (https://assetstore.unity.com/packages/3d/characters/humanoids/character-pack-free-sample-79870)

<hr>

<h2>CENA 4- CIDADE ILUMINADA</h2>

![WhatsApp Image 2024-09-18 at 17 53 37](https://github.com/user-attachments/assets/d86bdcec-9124-4e59-b15d-c33baa0c7eba)

Na cena cidade iluminada nos inspiramos no quadro de mesmo nome e usamos molduras de quadro, que modelamos no blender, como plataforma além disso colocamos fantasmas como inimigos e adicionamos colliders, com a opção "is Trigger" ligada, em cada fantasma assim fazendo com que quando o jogador toque no fantasma ele vá para uma cena de fim de jogo. Na cena no geral foi utilizado somente as plataformas representando a pintura "Cidade Iluminada", os fantasmas representando erros nas pinturas, também colocamos um fundo de noite na cena e para representar a iluminação da cidade colocamos luzes do tipo <strong>Spotlight</strong>.
<br>
script:

![patrulha](https://github.com/user-attachments/assets/3de6fa7e-8b68-451a-b2e3-2ad56d1ba472)

<br>
asset de fantasma: (https://assetstore.unity.com/packages/3d/characters/creatures/ghost-character-free-267003)

<h2>Narrativa</h2>
Título: Mundo dos Quadros - A Cidade Iluminada
Abertura
Marquinhos, um jovem de 17 anos da periferia de São Paulo, caminha pela 
movimentada Avenida Paulista em um dia comum. Ele é um garoto de aparência 
juvenil e curiosa, com cabelos loiros curtos, óculos redondos, uma camisa verde 
com suspensórios e uma calça azul. Durante o passeio, algo incomum chama sua 
atenção: ao final de uma viela pouco iluminada, ele avista o MASP (Museu de Arte 
de São Paulo) em um local onde não deveria estar. Movido por sua curiosidade e 
forte senso de justiça, Marquinhos decide investigar e adentra a viela.
O Museu Misterioso
Ao se aproximar do museu, Marquinhos percebe que a estrutura é idêntica ao 
MASP, mas algo parece fora do lugar. O ar está denso, quase surreal. Ele decide 
entrar no museu, onde encontra várias obras de arte icônicas brasileiras. O 
ambiente é imersivo, e as pinturas parecem ter vida própria.
No interior do museu, Marquinhos encontra o Inspetor, uma figura jovem, enigmática 
e de aparência simples, vestida com roupas azuis e brancas. Com um sorriso 
misterioso, o Inspetor convida Marquinhos a observar de perto a obra "Cidade 
Iluminada" de Antônio Bandeira. 
Curioso, Marquinhos se inclina para observar a pintura e, de repente, é sugado para 
dentro dela. Ele agora está imerso no mundo vibrante e abstrato da "Cidade 
Iluminada", onde pinceladas de luz e cor formam o ambiente ao seu redor.
A Jornada na Obra
Dentro do quadro, o cenário é abstrato e fascinante, mas também perigoso. 
Marquinhos precisa navegar por plataformas e enfrentar inimigos fantasmas . A música 
ambiente muda conforme o cenário, ajudando a intensificar a experiência imersiva.
O Clímax
Na última fase, dentro da "Cidade Iluminada", Marquinhos enfrenta seu maior desafio:
Plataformas agora se movem, fazendo com que Marquinhos tenha que dar grandes saltos para não cair no abismo.
Encerramento
Após vencer a fase final, Marquinhos encontra uma porta que o leva de volta a seu mundo. Marquinhos está confuso,porém com um sentimento de realização

<br>

<h2>Paleta de Cores</h2>

<h3>Cena Masp:</h3>

![AdobeColor-Masp.jpeg](https://github.com/user-attachments/assets/b6cc1e96-aad5-4955-9f78-2c4000cea711)


#5E90F2 (RGB 94, 144, 242):

Um azul claro e vibrante, que transmite uma sensação de calma e profundidade. Pode remeter ao céu ou à ideia de espaço aberto dentro do MASP, com suas grandes janelas e vistas da cidade.

#768BA6 (RGB 118, 139, 166):

Um azul acinzentado, que é mais suave e discreto. Esse tom neutro pode ser usado para elementos de fundo ou objetos dentro do museu, trazendo um ar de sofisticação e modernidade.

#3F4B59 (RGB 63, 75, 89):

Um cinza escuro azulado, que evoca uma sensação de solidez e estabilidade. Ideal para áreas estruturais, como as colunas ou a estrutura metálica do MASP, dando um toque mais industrial e urbano.

#72808C (RGB 114, 128, 140):

Um cinza azulado médio, que adiciona suavidade e uma transição natural entre os outros tons. Pode ser usado em superfícies ou detalhes, oferecendo um aspecto moderno sem ser muito chamativo.

#9DD962 (RGB 157, 217, 98):

Um verde vibrante, que contrasta com os tons mais frios e cria uma sensação de vitalidade e natureza. Pode representar o verde das plantas nas áreas externas ou até trazer uma energia revitalizante dentro do ambiente do MASP, sugerindo crescimento ou inovação.

<br>

<h3>Cena Cidade Iluminada</h3>

![AdobeColor-City1.jpeg](https://github.com/user-attachments/assets/acb5d24f-a247-4a69-9a26-779af28c7007)


#181D26 (RGB 24, 29, 38):

Um azul muito escuro, quase preto. Ele evoca a ideia de uma noite profunda ou sombras urbanas. Pode ser usado para o céu noturno ou áreas sombrias da cidade, dando um ar misterioso e introspectivo.



#0A0B0D (RGB 10, 11, 13):

Um preto puro com leve toque de azul. Ideal para representar o asfalto, edifícios ou estruturas metálicas em um ambiente urbano à noite. Traz uma sensação de peso e solidez, perfeito para áreas industriais ou escuras.



#575759 (RGB 87, 87, 89):

Um cinza metálico, que remete a superfícies de concreto ou metal, como postes, edifícios e elementos urbanos. Esse tom neutro ajuda a equilibrar as cores mais intensas e criar uma base sólida para a cena.



#F89F63 (RGB 248, 159, 99):

Um laranja vibrante, que contrasta fortemente com os tons escuros. Pode representar luzes da cidade, como letreiros de neon ou o brilho das janelas. Ele adiciona calor e energia à cena, capturando a ideia de uma cidade viva e iluminada.



#A0F266 (RGB 160, 242, 102):

Um verde neon brilhante, que traz um ar futurista e tecnológico. Perfeito para representar luzes artificiais, como sinais de trânsito, hologramas ou outros elementos high-tech. Ele injeta um toque de modernidade e inovação, contrastando com o ambiente mais escuro.
<br>
<h3>Cena Cidade Iluminada parte 2</h3>

![AdobeColor-City2.jpeg](https://github.com/user-attachments/assets/9da9820a-eb59-44e5-85aa-229153006a44)

#766865 (RGB 118, 104, 101):

Um marrom acinzentado suave, que transmite uma sensação de estabilidade e neutralidade. Esse tom pode ser utilizado para representar superfícies desgastadas, como paredes ou pisos antigos, ou até elementos naturais como troncos de árvores ou rochas.



#181D26 (RGB 24, 29, 38):

O azul escuro quase preto já mencionado anteriormente. Ele traz um ar noturno ou misterioso à paleta, sendo ideal para fundos ou sombras, fornecendo profundidade à cena.



#9CD95F (RGB 156, 217, 95):

Um verde vibrante e fresco, que pode representar a vegetação ou elementos de natureza viva. Ele adiciona uma energia mais leve e positiva à paleta, quebrando um pouco os tons mais terrosos e escuros, sugerindo crescimento ou vida.



#A66D3C (RGB 166, 109, 60):

Um marrom alaranjado, que evoca a sensação de madeira ou tijolos. Ele traz uma sensação de calor e rusticidade, ideal para representar materiais tradicionais ou orgânicos em um cenário.



#F2AE72 (RGB 242, 174, 114):

Um laranja pêssego claro, que sugere calor e aconchego. Ele pode ser usado para destacar elementos com iluminação suave, como o pôr do sol refletindo em superfícies, ou para criar uma atmosfera convidativa.

<br>
<h3>Avenida Paulista</h3>

![AdobeColor-Avenida Paulista.jpeg](https://github.com/user-attachments/assets/2a46f7e1-f9a8-437c-9c71-481900e46f3b)


#4F4F4D (RGB 79, 79, 77):

Um cinza escuro com leve toque de marrom, que traz uma sensação de neutralidade, seriedade e estabilidade. Pode ser usado em superfícies de fundo ou para representar materiais como concreto, metal ou pedras.



#5F5F5D (RGB 95, 95, 93):

Um cinza médio, que é um pouco mais claro e equilibrado. Essa cor pode ser usada para criar transições suaves entre elementos mais escuros e os tons vibrantes da paleta, fornecendo uma base sólida para o cenário.



#D92929 (RGB 217, 41, 41):

Um vermelho vibrante e intenso, que chama muita atenção. Ele pode ser usado para destacar áreas importantes, como elementos de perigo, ação ou algo que precisa ser enfatizado na cena. Traz uma sensação de urgência e energia.



#BF2626 (RGB 191, 38, 38):

Um vermelho escuro, menos brilhante que o anterior, mas ainda poderoso. Ele pode ser usado para detalhes de fundo ou para criar um contraste dramático com os tons mais neutros. Passa uma sensação de seriedade e intensidade.



#30383A (RGB 48, 56, 58):

Um cinza muito escuro com toque azulado, que quase se aproxima do preto. É ideal para áreas de sombra ou para criar profundidade na cena, ajudando a enfatizar os elementos mais claros e vibrantes.
<br>
<h3>Game Over</h3>

![AdobeColor-Game over.jpeg](https://github.com/user-attachments/assets/d8122ad9-bb43-4d3a-ba73-92204045c3eb)

#D1D1D1 (RGB 209, 209, 209):

Um cinza claro, que traz leveza e suavidade. Pode ser usado para superfícies ou elementos de fundo, criando uma base neutra e elegante.



#E9E7DA (RGB 233, 231, 218):

Um cinza muito claro com um toque quente, quase um bege. Essa cor pode transmitir uma sensação de calor e acolhimento, ideal para áreas que desejam criar uma atmosfera convidativa.



#F2F2F2 (RGB 242, 242, 242):

Um branco acinzentado, que é ainda mais suave. Pode ser utilizado para detalhes de destaque ou para iluminar espaços, ajudando a criar um contraste leve com os tons mais escuros.



#191617 (RGB 25, 22, 23):

Um preto quase absoluto, que traz profundidade e seriedade à paleta. Ideal para elementos de fundo, sombras ou para destacar áreas importantes, proporcionando um contraste forte com os tons mais claros.



#0D0D0D (RGB 13, 13, 13):

Um preto intenso, que complementa o anterior, mas com um toque mais profundo. É excelente para criar áreas de forte contraste e drama na cena, especialmente em combinações com as cores mais claras.
<br>
<h3>Menu Principal</h3>

![AdobeColor-Menu.jpeg](https://github.com/user-attachments/assets/579f992a-c74e-4e4b-be1a-2275af75ce4b)

#000000:

O preto puro. Ele traz profundidade e serve como base sólida para a paleta. Ideal para áreas de sombra, fundo ou elementos que precisam de destaque.



#D5241A (RGB 213, 36, 26):

Um vermelho vibrante e intenso. Essa cor chama atenção e pode ser usada para elementos que exigem foco, como alertas ou ações importantes no jogo. Transmite energia e urgência.



#D99923 (RGB 217, 153, 35):

Um amarelo-alaranjado quente, que adiciona uma sensação de calor e otimismo. Pode ser usado para detalhes que precisam se destacar, como ícones ou iluminação, complementando o vermelho.



#736866 (RGB 115, 107, 102):

Um cinza acinzentado, que traz um toque de neutralidade e rusticidade. Essa cor pode ser utilizada para superfícies ou elementos de fundo, criando um equilíbrio com as cores mais vibrantes.



#263645 (RGB 38, 54, 69):

Um azul-escuro, que adiciona profundidade e um toque de sofisticação. Ele pode ser usado para representar áreas mais sombrias ou industriais, ajudando a criar um contraste com os tons mais quentes da paleta.
<br>
links drive: 

<br>

Jogo: 
https://drive.google.com/file/d/1ysOo7WZfQ6gEMb4ZVbHp9X5czNQuLA7C/view?usp=sharing

<br>

Jogo Editável:
https://drive.google.com/file/d/1KOMe5FFUKkn4hJ648sLqcK4J2dBTSlTj/view?usp=sharing

Vídeo YouTube:
https://youtu.be/5MrfINzB6Vc?si=MYR16HhV8Ftlv9LF
