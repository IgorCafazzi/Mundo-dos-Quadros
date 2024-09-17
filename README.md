# Mundo-dos-Quadros

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

O outro botão é o de "Sair". Ao clicar nele, ojogo fecha
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

<h2>CENA 2- AVENIDA PAULISTA</h2>
