# Mundo-dos-Quadros 🎨 🖼️
<h1>Introdução ao Jogo</h1>
<p>
    Nossa ideia foi um jogo de ação e plataforma 3d, que se passa em São paulo atual onde o jogador começara na paulista e entrando em um beco encontrara o Masp, entrando no masp ele podera se aventurar dentro do quadro "A cidade Ilumina" por Antonio Bandeira, assim mostrando a metamorfose de São paulo atual. O jogo dentro do quadro é um jogo de plataforma com fantasmas da pintura sendo os principais inimigos, o jogador após passar por duas fases dentro do quadro consegue sair e pode finalmente sair do quadro. O jogo foi inspirado nos jogos Crash Bandicoot, Super Mario Bros. Wonder, Super Mario Odyssey e Epic Mickey,
</p>
<h2>PERSONAGEM</h2>
Nosso protagonista Marquinhos usando uma camisa verde, calças e suspensorios azuis e cabelo loiro.

asset usado: (https://assetstore.unity.com/packages/3d/characters/kids-character-free-242192)

para colisão usamos um character controller que faz...
![character](https://github.com/user-attachments/assets/c1fc80e1-f5ef-4d8c-85a8-0745a61031d1)

em movimentação usamos um script C#
(imagem com o script)

Camera: Usamos o gameobject cinemachine, usando a opção <strong>Free Lock Camera</strong> e colocando para a camera olhar e seguir o gameobject com tag "Player"

renascer: Utilizamos um gameobject com tag "respawn" e um script c# fazendo que quando o jogador caia ele seja transportado até o gameobject "respawn", servindo como um checkpoint

using UnityEngine;

public class PlayerFall : MonoBehaviour
{
    public float fallLimit = -20f;

    public Transform respawnPoint;

    void Update()
    {
        if (transform.position.y < fallLimit)
        {
            Respawn();
        }
    }

    void Respawn()
    {
        transform.position = respawnPoint.position;
    }
}




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

<h2>CENA 4- CIDADE ILUMINADA</h2>
Na cena cidade iluminada nos inspiramos no quadro de mesmo nome e usamos molduras de quadro como plataforma que modelamos no blender, além disso usamos um asset de fantasma(https://assetstore.unity.com/packages/3d/characters/creatures/ghost-character-free-267003) e colocamos um collider no fantasma juntamente a um script c# de 
