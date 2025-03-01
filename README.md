# hackintosh Dell Precision 5530

![Sem Título](https://github.com/user-attachments/assets/b0bef0fe-5b34-46e2-8ffb-aad4f85f6d49)

## EFI Details
**Latest working macOS:** 14.7.1 (parcialmente funcionando no Sequoia)  
**Current OpenCore:** 1.0.3  
**Release date:** 01/2025  

## Hardware details

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

## BIOS Config:

Secure boot -> disable  
Intel SGX (software guard extensions) -> disable  
TPM 2.0 -> disable  
Thunderbolt -> disable  
Sata operation -> AHCI  

## Comandos para Post Install

sudo pmset -a hibernatemode 0  
sudo rm -f /var/vm/sleepimage  
sudo mkdir /var/vm/sleepimage  
sudo pmset -a standby 0  
sudo pmset -a autopoweroff 0  
sudo pmset -a powernap 0  
sudo pmset -a proximitywake 0  
sudo pmset -b tcpkeepalive 0 (optional)  

## Working

- Wi-Fi/Bluetooth;
- Audio e Microfone;
- Todas as portas USB;
- Webcam;
- UHD Graphics 630 (2048MB);
- Leitor de cartão SD/SDHC;
- TouchScreen;
- Gestos do trackpad.

## Don't Working

- Nvidia P2000;
- Goodix Fingerprint;
- Bluetooth Low Energy (BLE).


> *Nota:* Percebi que após sair do modo sleep todos os USBs são desconectados, por esse motivo o Bluetooth pode parar de funcionar por alguns minutos, mas volta, se não voltar é só conectar um USB que ele retorna. 
