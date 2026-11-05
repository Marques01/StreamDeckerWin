# 🎛️ ACM Stream Deck

**Um Stream Deck DIY, desenvolvido com .NET MAUI Blazor Hybrid e ESP32.**

O ACM Stream Deck é um projeto independente que une hardware e software para criar uma central de controle personalizável para Windows. A proposta é oferecer monitoramento do sistema, controle de mídia e volume em uma interface moderna, com comunicação entre um dispositivo ESP32 e uma aplicação desktop.

---

## 📸 Preview

<!-- Adicione aqui uma captura de tela da interface -->
![ACM Stream Deck Preview](docs/images/preview.png)

---

## ✨ Funcionalidades

- **Monitoramento do sistema:** acompanhamento de CPU, memória RAM e GPU.
- **Gráficos em tempo real:** indicadores visuais para acompanhar a utilização dos recursos.
- **Informações de hardware:** possibilidade de expansão para temperaturas e atividade de disco.
- **Controle de mídia:** integração com sessões de mídia do Windows.
- **Controle de volume:** gerenciamento do volume principal do sistema.
- **Relógio:** exibição de horário na interface.
- **Comunicação serial:** integração entre aplicação Windows e ESP32.
- **Interface personalizada:** dashboard desenvolvido com Blazor e Bootstrap.

## 🏗️ Arquitetura

O projeto é dividido em duas partes principais:

### Aplicação Desktop

Desenvolvida em C# com .NET MAUI Blazor Hybrid, é responsável pela interface gráfica, integração com recursos do Windows e envio de informações ao dispositivo.

Responsabilidades:
- Coleta de informações do sistema.
- Integração com sessões de mídia do Windows.
- Controle de volume.
- Gerenciamento da comunicação serial.
- Atualização dos dados apresentados na interface.

### Firmware ESP32

Desenvolvido em C++, utilizando o ambiente Arduino.

Responsabilidades:
- Comunicação serial com a aplicação desktop.
- Recebimento e interpretação dos dados.
- Controle do display TFT.
- Leitura dos botões físicos.
- Execução de comandos e ações configuradas.

### Fluxo de comunicação

```text
┌──────────────────────────────┐
│         Windows PC           │
│                              │
│  ┌────────────────────────┐  │
│  │  ACM Stream Deck App   │  │
│  │  .NET MAUI + Blazor    │  │
│  └────────────┬───────────┘  │
│               │              │
│  ┌────────────▼───────────┐  │
│  │   Windows Services     │  │
│  │ CPU / RAM / GPU / Media│  │
│  └────────────┬───────────┘  │
└───────────────┼──────────────┘
                │
           Serial USB
                │
┌───────────────▼──────────────┐
│            ESP32             │
│                              │
│  ┌────────────────────────┐  │
│  │   Serial Communication │  │
│  └────────────┬───────────┘  │
│               │              │
│  ┌────────────▼───────────┐  │
│  │      TFT Display       │  │
│  └────────────────────────┘  │
│                              │
│       Physical Buttons       │
└──────────────────────────────┘
```

## 🛠️ Tecnologias utilizadas

| Tecnologia | Aplicação |
|---|---|
| C# | Aplicação desktop |
| .NET MAUI | Integração com Windows |
| Blazor Hybrid | Interface gráfica |
| HTML / CSS | Estrutura e estilização |
| Bootstrap 5 | Componentes e layout |
| Bootstrap Icons | Ícones |
| C++ | Firmware do ESP32 |
| Arduino Framework | Desenvolvimento embarcado |
| JSON | Formato de comunicação |
| Serial USB | Comunicação entre PC e ESP32 |

## 🔌 Hardware

Componentes utilizados ou previstos no projeto:

- ESP32 DevKit V1.
- Display TFT 2.4" ILI9341.
- Switches mecânicos Redragon.
- Keycaps personalizadas.
- Gabinete desenvolvido em impressão 3D.
- Conexão USB para alimentação e comunicação.

O gabinete é desenvolvido considerando modularidade, organização dos componentes e facilidade de montagem.

## 🚀 Executando o projeto

### Aplicação Desktop

1. Clone este repositório:

```bash
git clone https://github.com/SEU-USUARIO/ACM-Stream-Deck.git
```

2. Abra a solução no Visual Studio.
3. Restaure os pacotes NuGet.
4. Configure a porta serial correspondente ao ESP32, conforme a implementação.
5. Compile e execute a aplicação.

### Firmware ESP32

1. Abra o projeto do firmware no Arduino IDE ou PlatformIO.
2. Instale as bibliotecas necessárias.
3. Configure as conexões do display conforme o firmware.
4. Compile e grave o código no ESP32.
5. Conecte o dispositivo ao computador via USB.

> As configurações de hardware e comunicação podem variar conforme a versão do dispositivo.

## 🗺️ Roadmap

- [x] Desenvolvimento da interface desktop.
- [x] Estrutura inicial de comunicação serial.
- [x] Integração visual de monitoramento do sistema.
- [x] Indicadores gráficos de utilização de recursos.
- [x] Tela de inicialização personalizada.
- [ ] Integração completa com os botões físicos.
- [ ] Mapeamento de ações personalizadas.
- [ ] Configuração de perfis e atalhos.
- [ ] Expansão das informações de hardware.
- [ ] Aprimoramento do firmware e protocolo de comunicação.

## 💡 Objetivo

O objetivo do ACM Stream Deck é explorar a integração entre desenvolvimento de software desktop, sistemas embarcados e fabricação digital, criando uma alternativa personalizável e acessível aos dispositivos comerciais de controle.

O projeto também busca aplicar conceitos de arquitetura de software, comunicação serial, interfaces gráficas e desenvolvimento de firmware em um produto físico funcional.

---

**Desenvolvido como projeto independente de hardware e software.**
