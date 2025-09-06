# EchoRider

## Objetivo

Intercomunicador por voz para motos, com **latência baixíssima**, usando celulares como host ou peers, comunicação via **rede ad hoc** (Wi-Fi P2P / Nearby Connections), eliminando necessidade de internet.

## Stack / Tecnologias

- **Frontend / App:** Flutter
- **Áudio / Voz:** `flutter_webrtc` (captura, codificação Opus, playback)
- **Signaling / Descoberta de peers:** **Nearby Connections API** (modo ad hoc, P2P)
- **Rede:** Wi-Fi P2P (ad hoc) → host e clientes conectados direto
- **Extras:** Push-to-talk, full-duplex, múltiplos peers
- **Bluetooth:** só pra conexão do capacete

## Estrutura do app

- **Modo Host / Peer iniciador:**
    - Cria rede ad hoc via Nearby Connections
    - Descobre peers próximos e gerencia conexões
    - Transmite e recebe áudio via WebRTC (P2P)
- **Modo Cliente / Peer receptor:**
    - Descobre host/peers via Nearby Connections
    - Conecta automaticamente
    - Transmite e recebe áudio via WebRTC