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
|NVME|KXG5AZNV512G NVMe SED TOSHIBA 512GB|

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

### BIOS Config:

Secure boot -> disable  
Intel SGX (software guard extensions) -> disable  
TPM 2.0 -> disable  
Thunderbolt -> disable  
Sata operation -> AHCI  

### Comandos para Post Install

sudo pmset -a hibernatemode 0
sudo rm -f /var/vm/sleepimage
sudo mkdir /var/vm/sleepimage
sudo pmset -a standby 0
sudo pmset -a autopoweroff 0
sudo pmset -a powernap 0
sudo pmset -a proximitywake 0
sudo pmset -b tcpkeepalive 0 (optional)

### Updates

- Fiz um downgrade para a versão 14 Sonoma por ter mais compatibilidade com kexts de hackintosh;
- Corrigido o bug que deixava a tela dividida em 4 partes após despertar;
- Corrigido também a porta HDMI que não estava funcionando;
- Novo bug descoberto - Agora é possivel transmitir a tela usando uma dock dell, mas após isso o displey integrado fica sem imagem. (Acredito que seja algo relacionado a saida DP já que nos testes que fiz a saida de video via USB era reconhecida como DP).

> *Nota:* o bug da tela parou após atualizar o dpcd-max-link-rate de CgAAAA== para FAAAAA== e mandar os comandos de post-install, depois testarei para ver qual foi o responsável por corrigir o erro

#### Notas:

Nota: Por algum motivo atualizei os arquivos de opencore e tudo ficou quebrado, tive que retornar a uma EFI antiga que não esta usando o Wi-Fi nativo e sim pelo HeliPort.
A ideia é ir usando o hackintosh, programando e corrigindo os pequenos bugs até conseguir comprar uma placa Wi-Fi nativa ou uma broadcom suportada (como a entrada do network card desse notebook é uma Key A as minhas opções de placas ficam um pouco restritas tendo que encarar outras soluções como adaptadores. Ainda estou maturando essa ideia.)