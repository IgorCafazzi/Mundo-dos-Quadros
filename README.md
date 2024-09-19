# Mundo-dos-Quadros 🎨 🖼️

<h1>Introdução ao Jogo</h1>

 Nossa ideia é um jogo de ação e plataforma 3D ambientado na São Paulo contemporânea. O jogador inicia sua jornada na Avenida Paulista e explorarando um beco, encontra o MASP. Ao entrar no museu, ele embarca em uma aventura dentro da pintura "A Cidade Iluminada" de Antonio Bandeira, que reflete a metamorfose de São Paulo atual. Dentro do quadro, o jogo se transforma em uma plataforma, onde os principais inimigos são fantasmas repreentando "falhas" na pintura. Após superar duas fases desafiadoras, o jogador consegue escapar. O jogo é inspirado em títulos como Crash Bandicoot, Super Mario Bros. Wonder, Super Mario Odyssey e Epic Mickey.


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

Checkpoint: Para implementação de um sistema de respawn colocamos um GameObject cubo invisivel com tag "respawn" onde o jogador devia respawnar, assim o jogador não corre o risco de errar o pulo e ficar preso no void do unity, por que quando ele passa -20f no eixo y ele é chamdo denovo a posição do cubo com tag "respawn". Isso impede de trazer uma gameplay frustrante e punitiva, afinal mesmo que ele erre ele ainda vai ser chamado ao checkpoint. <br>
Script:

![Screenshot_20240918_113320_Chrome.jpg](https://github.com/user-attachments/assets/cd536471-4c4d-4bf9-a0fb-81801cade4f3)

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

Na primeira cena, o jogador encontra o MASP, sobe as escadas e, ao encostar na porta, é levado para a próxima fase. Utilizamos assets urbanos para representar São Paulo e modificamos o MASP no Blender para abrir um caminho acessível. A Avenida Paulista foi criada com ruas largas e prédios altos. Posicionamos o MASP no fim de um beco para causar estranheza, e a transição de cenas foi realizada utilizando um código c#. <br>
script:


<br>
asset City Voxel Pack: (https://assetstore.unity.com/packages/3d/environments/urban/city-voxel-pack-136141)
<br>
asset do MASP: (https://sketchfab.com/3d-models/masp-museu-de-arte-de-sao-paulo-simplificado-7eb9d1c77f9b43b088128fc5baa249bb)

<hr>

<h2>CENA 3- MASP</h2>
Já no Masp usamos o asset do masp novamente para representar uma sala com diversos quadros emoldurados acima de um cubo (asset dos quadros: https://assetstore.unity.com/packages/3d/props/interior/picture-frames-with-photos-106907), tal qual como realmente é no Masp. <br>

![Museu-Masp-Sao-Paulo-18](https://github.com/user-attachments/assets/4d610717-a904-41e9-b753-de743bcb1091)

<br>
No final do corredor o jogador encontra o quadro da Cidade Iluminada, ao encostar nele o jogador sera teletransportado para a próxima cena. Ao lado desse quadro está o inspetor, um homem de poucas palavras presente na cena. <br>
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

<br>

Paleta Paulista (Transformação de São Paulo ao longo do tempo):

#DAFDBA (Verde Claro): Representa renovação e o começo de algo novo.

#9AEBA3 (Verde Vitalidade): Sugere crescimento e representa a natureza dentro da cidade.

#45C4B0 (Verde-Azulado): Indica modernidade e o dinamismo da metrópole.

#13678A (Azul Profundo): Transmite estabilidade e seriedade da cidade.

#012030 (Tom Escuro): Evoca mistério e a complexidade de São Paulo.

<br>

Cena 'A Cidade Iluminada' (Inspirada em 'A Cidade Iluminada' de Antônio Bandeira):

#8C3041 (Vermelho Escuro): Simboliza a intensidade da cidade.

#BF2A2A (Vermelho Profundo): Reforça a intensidade urbana.

#1469D9 (Azul): Representa modernidade.

#B0D973 (Verde Claro): Sugere crescimento e renovação.

#F26938 (Laranja Vibrante): Destaca a energia e o calor da metrópole.

<br>

Paleta Paulista (Inspirada em São Paulo durante o dia):

#738BBF (Azul Claro): Representa o céu e a modernidade da cidade.

#012626 (Verde Escuro): Evoca as áreas verdes de São Paulo.

#A3D9D3 (Verde Claro): Simboliza as árvores e plantas.

#022601 (Verde Escuro): Representa as sombras e profundidade das áreas verdes.

#D9B79A (Bege): Evoca o calor do sol iluminando as ruas da cidade.

<br>

links drive: <br>
Jogo: https://drive.google.com/file/d/17swtILI3SFxxlAQYAHaBnnhLDMhN2TTj/view?usp=sharing

<br>
Jogo Editável:
https://drive.google.com/file/d/14t8xrI_jGDbsbNWJVvcvzWBaKy4VCB6U/view?usp=sharing


Vídeo YouTube:
https://youtu.be/UuGwjS3-63I?si=L8QQladvt_WmlxAt