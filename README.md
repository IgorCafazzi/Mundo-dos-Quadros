# Mundo-dos-Quadros 🎨 🖼️

<h1>Introdução ao Jogo</h1>

 Nossa ideia é um jogo de ação e plataforma 3D ambientado na São Paulo contemporânea. O jogador inicia sua jornada na Avenida Paulista e explorarando um beco, encontra o MASP. Ao entrar no museu, ele embarca em uma aventura dentro da pintura "A Cidade Iluminada" de Antonio Bandeira, que reflete a metamorfose de São Paulo atual. Dentro do quadro, o jogo se transforma em uma plataforma, onde os principais inimigos são fantasmas repreentando "falhas" na pintura. Após superar duas fases desafiadoras, o jogador consegue escapar. O jogo é inspirado em títulos como Crash Bandicoot, Super Mario Bros. Wonder, Super Mario Odyssey e Epic Mickey.


<hr>

<h2>PERSONAGEM</h2>

Nosso protagonista Marquinhos é um jovem de 17 anos que estava andando pela paulista. O modelo do marquinhos tem um esilo cartoon em 3d, usando uma camisa verde, calças e suspensorios azuis e cabelo loiro. O viual dele no geral transmite um visual simples porém moderno, misturando fantasia com modernismo.


asset usado: (https://assetstore.unity.com/packages/3d/characters/kids-character-free-242192)


Colisão: Usamos um character controller para fazer a Movimentação do personagem. Esse componente permite controlar o movimento sem a necesidade de aplicar física diretamente. Com o character Controller podemos fazer uma movimentação mais suave, evitando problemas comuns como colisões incorretas e perda de controle do personagem.

<br>

![character](https://github.com/user-attachments/assets/c1fc80e1-f5ef-4d8c-85a8-0745a61031d1)

Na Movimentação usamos esse script de C#
(imagem com o script)

Camera: Na camera usamos a ferramenta Cinemachine no unity, usando a opção <strong>Free Look Camera</strong>, com ela conseguimos fazer uma camera em 3°pessoa que segue o jogador colocando as opções "follow" e "look at" para seguir o objeto com tag "player", trazendo assim um movimento suave para a camera permitindo o jogador rotacionar a camera em volta do personagem.

Checkpoint: Para implementação de um sistema de respawn colocamos um GameObject cubo invisivel com tag "respawn" onde o jogador devia respawnar, assim o jogador não corre o risco de errar o pulo e ficar preso no void do unity, por que quando ele passa -20f no eixo y ele é chamdo denovo a posição do cubo com tag "respawn". Isso impede de trazer uma gameplay frustrante e punitiva, afinal mesmo que ele erre ele ainda vai ser chamado ao checkpoint.

![Screenshot_20240918_113320_Chrome.jpg](https://github.com/user-attachments/assets/cd536471-4c4d-4bf9-a0fb-81801cade4f3)

<hr>

<h2>CENA 1- MENU</h2>
Para o menu principal do jogo, usamos 2 botões que deixaram ele interativo. Botão 1: "Jogar". Ao clicar nesse botão, ocorre uma troca de cena que direciona o player para a cena 2- Avenida Paulista
Script: using UnityEngine;
using UnityEngine.SceneManagement;

public class SceneSwitcher : MonoBehaviour
{
    // Variável pública para definir o nome da cena no Inspector
    public string nomeCena;

    private void OnTriggerEnter(Collider other)
    {
        if (other.CompareTag("Player"))
        {
            // Carrega a cena com o nome especificado
            SceneManager.LoadScene(nomeCena);
        }
    }
}

O outro botão é o de "Sair". Ao clicar nele, o jogo fecha
Script:using UnityEngine;

public class QuitGame : MonoBehaviour
{
    public void Quit()
    {
        // Fecha o jogo quando estiver em um build (fora do editor)
        Application.Quit();
        #endif
    }
}

Para a imagem de fundo criamos um painel, pegamos a imagem, deixamos como sprite e aplicamos nos painel.
![WhatsApp Image 2024-09-12 at 16 57 10](https://github.com/user-attachments/assets/9634a90f-0a2d-44cb-b9c3-fb10513cf9ba)

<hr>

<h2>CENA 2- AVENIDA PAULISTA</h2>
Para a formação da cena geral (prédios e outras construções), usamos o asset City Voxel Pack
(https://assetstore.unity.com/packages/3d/environments/urban/city-voxel-pack-136141) e no meio de alguns prédios colocamos um asset do MASP (https://sketchfab.com/3d-models/masp-museu-de-arte-de-sao-paulo-simplificado-7eb9d1c77f9b43b088128fc5baa249bb), que será usado na próxima cena. Andando no mapa e encontrando o MASP, o jogador deve subir as escadas e ao encostar na porta ele é levado para a próxima cena. Para fazer isso usamos um código para a transição das cenas (finge q tem o código).
Ruas largas de mão dupla e diversos prédios para representar a Avenida Paulista. O MASP foi colocado no fim de um beco para causar estranheza, pois ele não fica naquele local normalmente.

<h2>CENA 3- MASP</h2>
Agora o jogador está dentro do MASP. Representamos essa parte de dentro como um corredor reto e usamos quadros emoldurados acima de cubos, assim como realmente é no MASP

![Museu-Masp-Sao-Paulo-18](https://github.com/user-attachments/assets/4d610717-a904-41e9-b753-de743bcb1091)

No final do corredor o player encontra o quadro da Cidade Iluminada, que ao encostar nele é teletransportado para a próxima cena. Ao lado desse quadro está o inspetor, um homem de poucas palavras presente na cena (asset: https://assetstore.unity.com/packages/3d/characters/humanoids/character-pack-free-sample-79870 )

<hr>

<h2>CENA 4- CIDADE ILUMINADA</h2>
Na cena cidade iluminada nos inspiramos no quadro de mesmo nome e usamos molduras de quadro como plataforma que modelamos no blender, além disso usamos um asset de fantasma(https://assetstore.unity.com/packages/3d/characters/creatures/ghost-character-free-267003) e colocamos um collider no fantasma juntamente a um script c# de 
