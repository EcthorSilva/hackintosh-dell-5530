# hackintosh Dell Precision 5530

![Sem Título](https://github.com/user-attachments/assets/b0bef0fe-5b34-46e2-8ffb-aad4f85f6d49)

### Hardware details

|Item|Description|
|-|:-------|
|CPU|Intel Core i9-8950HK (6 núcleos, 2.9GHz base, 4.8GHz Turbo, 12MB Cache, 45W)|
|iGPU|Intel UHD Graphics 630|
|dGPU|NVIDIA Quadro P2000 (desativada com SSDT patch)|
|Memória|32GB DDR4 2667 MHz (2x 16GB SO-DIMM)|
|Tela|15.6" 3840x2160 (4K UHD)|
|Wi-Fi / Bluetooth|Intel Wireless-AC 9260|
|Touchpad|Synaptics|
|Placa-mãe / Modelo do Laptop|Dell Precision 5530 (Chipset CM246)|
|NVME|null|

### Compatibility Check

1. CPU:
   - Intel(R) Core(TM) i9-8950HK CPU: Up to macOS Sequoia 15
2. GPU:
   - NVIDIA Quadro P2000: Maximum support up to macOS High Sierra 10.13 (requires monitor)
   - Intel(R) UHD Graphics 630: Up to macOS Sequoia 15
      - Connected Monitor: SHP148D (Internal)
3. Sound:
   - Áudio Intel(R) para telas: Up to macOS Sequoia 15
   - Realtek(R) Audio: Up to macOS Sequoia 15
      - Audio Endpoints: Microfone, Fones de ouvido/Alto falantes
4. Biometric:
   - Goodix fingerprint: Unsupported
5. Network:
   - Intel(R) Wireless-AC 9260 160MHz: Up to macOS Sequoia 15
6. Storage Controllers:
   - Cannon Lake Mobile PCH SATA AHCI Controller: Up to macOS Sequoia 15
   - XG5 NVMe SSD Controller: Up to macOS Sequoia 15
7. SD Controller:
   - Realtek PCIE CardReader: Up to macOS Sequoia 15

### Bugs: 

Ao bloquear a tela e esperar uns minutos o macOS coloca a tela em suspensão e ao voltar ela fica com a imagem quebrada, ainda estou investigando isso;  
A saida HDMI não esta funcionando, mas eu não tentei configurar ela ainda;  
Algumas teclas do teclado como insert ou print screen estão bugadas, não respondem ou responde enviam comandos diferentes do normal (exemplo: a tecla F11 com o FN ligado abaixa o brilho, mas com ele desligado ela mostra a area de trabalho).

#### Notas:

Nota: Por algum motivo atualizei os arquivos de opencore e tudo ficou quebrado, tive que retornar a uma EFI antiga que não esta usando o Wi-Fi nativo e sim pelo HeliPort.
A ideia é ir usando o hackintosh, programando e corrigindo os pequenos bugs até conseguir comprar uma placa Wi-Fi nativa ou uma broadcom suportada (como a entrada do network card desse notebook é uma Key A as minhas opções de placas ficam um pouco restritas tendo que encarar outras soluções como adaptadores. Ainda estou maturando essa ideia.)

### Benchmark 

Comparação feita com um Dell Precision 5530 com Windows 11 Pro, versão que anteriormente estava instalada em meu notebook, e com a mesma configuração que esta maquina tem.

<img width="1914" alt="image" src="https://github.com/user-attachments/assets/e190053f-d129-4c18-949c-83c22d15c5f1" />

Meu benchmark: https://browser.geekbench.com/v6/cpu/10457910  
Outro benchmark: https://browser.geekbench.com/v6/cpu/10408128
