# Configurando a Conexão Bluetooth do ESP32

Este guia detalha como configurar o ESP32 para se conectar a um controle PS4 via Bluetooth. O processo envolve adquirir o endereço MAC do ESP32, emparelhar o controle e gerenciar conexões. Utilizaremos o Arduino IDE para todas as etapas.

---

## **Pré-requisitos**
- Arduino IDE instalado.  
- Drivers necessários para o ESP32.  
- Controle PS4.  

---

OBS: *Drivers utilizados para o projeto:* https://github.com/espressif/esp-idf
Instale a lib em preferencias: https://espressif.github.io/arduino-esp32/package_esp32_index.json
Pode utilizar as placa ESP32 Wrover Module/ESP32 Dev Module/ESP32vn IoT Uno (placas testadas no projeto)
Caso, apresente erros de ou precise alterar a opção PSRAM ou Partition Scheme, utilize ESP32 Dev Module.

## **Passo 1: Adquirindo o MAC do ESP32**

1. Carregue o código do arquivo `src/ESP32DeviceMAC/` no ESP32.  
2. Abra o Monitor Serial na Arduino IDE.  
3. Pressione o botão de reset na placa ESP32.  

### **Exemplo de saída no Monitor Serial**  
```  
ESP Bluetooth MAC address is - XX:XX:XX:XX:XX:XX   (<- SEU MAC)  
```  
4. Guarde o endereço MAC exibido, pois será usado para emparelhar o controle PS4.  

---

## **Passo 2: Emparelhando o Controle PS4 com o ESP32**  

1. Instale o programa de emparelhamento localizado na pasta `output/sixaxispairtoolsetup-0.3.1.exe`.  
2. Execute o programa e conecte seu controle PS4 ao computador.  
3. Insira o endereço MAC do ESP32 no campo indicado e clique em "Pair" para realizar o emparelhamento.  

---

## **Passo 3: Limpando Conexões Existentes**  

Caso o controle não seja reconhecido pelo ESP32, limpe as conexões antigas:  

1. Carregue o arquivo `src/ClearConnections/` no ESP32.  
2. Execute o código para limpar as conexões armazenadas.  

---

## **Passo 4: Conectando o Controle PS4 ao ESP32**  

1. Carregue o programa `src/PS4ControllerBluetooth/` no ESP32.  
2. Abra o Monitor Serial e verifique os logs para confirmar o funcionamento do controle.  

---

Com essas etapas, seu controle PS4 estará configurado e funcionando com o ESP32 via Bluetooth.
