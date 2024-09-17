# Mundo-dos-Quadros
<h2>PERSONAGEM</h2>
No personagem usamos o asset(https://assetstore.unity.com/packages/3d/characters/kids-character-free-242192) referenciando o nosso protagonista Marquinhos usando uma camisa verde, calças e suspensorios azuis e cabelo loiro.

para colisão usamos um character controller 





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

<h2>CENA 2- AVENIDA PAULISTA</h2>
Para a formação da cena geral (prédios e outras construções), usamos o asset City Voxel Pack
(https://assetstore.unity.com/packages/3d/environments/urban/city-voxel-pack-136141) e no meio de alguns prédios colocamos um asset do MASP (https://sketchfab.com/3d-models/masp-museu-de-arte-de-sao-paulo-simplificado-7eb9d1c77f9b43b088128fc5baa249bb)
