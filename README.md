# Janela 3D

Página que mostra uma cena em **Gaussian Splatting** com efeito de "janela": a câmera frontal acompanha o rosto e a perspectiva muda conforme você se move. Funciona no Safari do iPad (e em computadores com webcam). Tudo roda no aparelho; nada é gravado ou enviado.

## Como abrir

O navegador só libera a câmera em sites **HTTPS**, então a página precisa estar publicada:

1. No GitHub: **Settings → Pages → Build and deployment**, em *Source* escolha **Deploy from a branch**, selecione o branch e a pasta `/ (root)`, e salve.
2. Depois de 1–2 minutos o link aparece no topo da mesma tela (algo como `https://<usuario>.github.io/livro-emilia/`).
3. Abra no Safari do iPad, toque em **Começar** e permita o acesso à câmera.

Sem câmera, o botão **Sem câmera (usar o dedo)** deixa arrastar o dedo na tela para mover o ponto de vista.

## Ajustes (botão ⚙︎)

- **Intensidade**: quanto a cena reage ao movimento da cabeça.
- **Profundidade da janela**: quanto a "tela" fica para dentro da cena.
- **Suavização**: reduz tremidas (valores altos deixam o movimento mais lento).
- **Inverter direção**, **Mostrar câmera**, **Centralizar** (recalibra a posição neutra do rosto).

## Trocar o fundo

1. Gere um splat (por exemplo, com o app **Scaniverse** no iPad/iPhone) e exporte em `.spz` ou `.ply`.
2. Coloque o arquivo na pasta `cenas/`.
3. Abra a página com `?cena=nome-do-arquivo.spz` no fim do endereço, ou troque o nome padrão em `index.html` (`quarto-pintado.spz`).

Parâmetro opcional: `?fov=70` muda a abertura da visão com o rosto centralizado.

## O que tem aqui

| Pasta | Conteúdo |
|---|---|
| `index.html` | A página inteira (cena, rastreamento de rosto e projeção off-axis) |
| `cenas/quarto-pintado.spz` | Cena de exemplo publicada pela World Labs nos exemplos do Spark. Use só para testes; para o livro, troque por uma cena própria |
| `vendor/three` | [Three.js](https://threejs.org) r180, licença MIT |
| `vendor/spark` | [Spark](https://github.com/sparkjsdev/spark) 2.3.1 (renderizador de splats da World Labs), licença MIT |
| `vendor/mediapipe` | [MediaPipe Tasks Vision](https://ai.google.dev/edge/mediapipe) 1.1.0 (Google), licença Apache 2.0 |
| `modelos/face_landmarker.task` | Modelo de detecção de rosto do MediaPipe |

As bibliotecas estão copiadas no repositório para a página não depender de CDNs externas.
