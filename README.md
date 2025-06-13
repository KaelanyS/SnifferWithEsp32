# Wi‑Fi Sniffer 30s: Monitoramento Visual com ESP32

## Descrição
Este projeto é um sniffer Wi‑Fi desenvolvido com ESP32 que opera em modo promíscuo por 30 segundos. Durante esse período, o dispositivo captura pacotes Wi‑Fi, identifica endereços MAC e fornece feedback visual usando LEDs:  
- **LED vermelho:** Indica a detecção de um novo dispositivo.  
- **LED verde:** Indica que o dispositivo já foi registrado.

Ao final dos 30 segundos, um resumo dos dispositivos capturados (MAC, quantidade de detecções, último RSSI e último canal) é impresso no Monitor Serial.

## Funcionalidades
- Captura de pacotes Wi‑Fi em modo promíscuo.
- Identificação e contagem dos endereços MAC.
- Feedback visual através dos LEDs para diferenciar novos e dispositivos já vistos.
- Exibição de um resumo organizado no Monitor Serial após 30 segundos.

## Materiais Necessários

### Hardware
- **ESP32 DEV KIT:**  
  Configurado para operar com os pinos:
  - Pino 25 para LED vermelho.
  - Pino 27 para LED verde.
  - Pino 32 para LED azul (não utilizado nesta versão).
- **LED RGB:** Para feedback visual.
- **Fios:** Para conectar os componentes.
- **Resistores:** Para proteger os LEDs e regular a corrente.
- **Protoboard:** Para montagem e testes do circuito.

### Software
- **Arduino IDE:** Ambiente de desenvolvimento para programar o ESP32.
- **Bibliotecas:**
  - `esp_wifi.h` – Para funções avançadas de Wi‑Fi, como o modo promíscuo.
  - `WiFi.h` – Para configuração básica de conectividade.
  - Suporte à STL (e.g., utilização de `std::vector`) para gerenciar dinamicamente os dados dos dispositivos.

## Instruções para Replicar

1. **Montagem do Hardware:**
   - Conecte os LEDs aos pinos designados do ESP32 (25, 27 e 32).
   - Utilize resistores adequados para garantir a proteção dos LEDs.
   - Monte o circuito na protoboard de forma organizada e segura.

2. **Configuração do Ambiente:**
   - Instale o [Arduino IDE](https://www.arduino.cc/en/software).
   - Configure o Arduino IDE para usar o ESP32 (adicione a URL de gerenciamento de placas ESP32 e instale a placa).
   - Instale as bibliotecas necessárias (`esp_wifi.h` e `WiFi.h`).

3. **Upload do Código:**
   - Abra o arquivo do projeto (por exemplo, `sniffer.ino`) no Arduino IDE.
   - Conecte o ESP32 ao computador e selecione a porta correta.
   - Compile e faça o upload do código para o dispositivo.

4. **Execução e Monitoramento:**
   - Abra o Monitor Serial no Arduino IDE.
   - O protótipo iniciará a captura dos pacotes por 30 segundos, com os LEDs fornecendo feedback visual.
   - Após 30 segundos, um resumo dos dispositivos capturados será exibido no Monitor Serial.
