# Smart Lamp com FIWARE Descomplicado, ESP32 e MQTT
---

## Descrição do Projeto

Este projeto implementa uma **Smart Lamp** integrada ao ecossistema **FIWARE Descomplicado**, utilizando **ESP32**, **MQTT**, **Wokwi**, **Postman** e uma **Máquina Virtual (VM)** para simular, monitorar e controlar variáveis do ambiente.

A aplicação permite:

- controlar o **LED onboard** do ESP32
- publicar o estado do LED em um **broker MQTT**
- ler valores de **luminosidade**
- enviar dados para o ambiente FIWARE
- consultar e alterar informações por meio do **Postman**
- validar a comunicação entre dispositivo, broker e serviços FIWARE em execução na VM

O código foi ajustado para funcionar no ambiente **FIWARE Descomplicado**, utilizando a infraestrutura configurada na máquina virtual e integração com broker MQTT.

---

## Objetivo

O principal objetivo deste projeto é demonstrar, na prática, a integração entre um dispositivo IoT e a plataforma FIWARE, aplicando conceitos de:

- **Internet das Coisas (IoT)**
- **Edge Computing**
- **protocolo MQTT**
- **comunicação via API REST**
- **simulação embarcada**
- **monitoramento de variáveis em tempo real**

---

## Ferramentas Utilizadas

- **ESP32**
- **FIWARE Descomplicado**
- **Orion Context Broker**
- **MQTT**
- **Wokwi**
- **Postman**
- **Máquina Virtual Linux**
- **Docker / Docker Compose**
- **Arduino IDE**
- **WiFi.h**
- **PubSubClient.h**

---

## Arquitetura do Projeto

O sistema é composto por três partes principais:

### 1. ESP32 / Wokwi
O **ESP32** é responsável por:

- controlar o LED onboard
- ler a luminosidade do ambiente
- publicar os dados no broker MQTT
- receber comandos para ligar ou desligar o LED

No projeto, esse comportamento pode ser executado de forma simulada no **Wokwi**.

### 2. Máquina Virtual com FIWARE
A **VM** executa os serviços do FIWARE, responsáveis por:

- intermediar a comunicação entre os dispositivos
- receber e gerenciar os dados de contexto
- manter a integração com os testes realizados

### 3. Postman
O **Postman** é utilizado para:

- testar requisições HTTP
- consultar entidades
- validar se os dados enviados estão corretos
- verificar alterações nos atributos monitorados

---
### Você pode alterar as seguintes variaveis

- **Rede Wi-Fi:**
  - SSID: `FIAP-IOT`
  - Senha: `F!@p25.IOT`

- **Broker MQTT:**
  - BROKER IP: `O ip do seu servidor`
  - Porta: `1883`
  - Tópico de comando: `/TEF/lamp051/cmd`
  - Tópico de envio de estado: `/TEF/lamp051/attrs`
  - Tópico de envio de luminosidade: `/TEF/lamp051/attrs/l`
  - ID MQTT: `fiware_001`
---

## Fluxo de Funcionamento

O funcionamento do sistema ocorre da seguinte forma:

1. O **ESP32** ou a simulação no **Wokwi** realiza a leitura da luminosidade.
2. O dispositivo publica os dados em um **broker MQTT**.
3. O ambiente **FIWARE**, executado na VM, recebe e processa essas informações.
4. O **Postman** pode ser usado para consultar ou alterar os dados da entidade.
5. O usuário valida o comportamento do sistema observando as respostas e os valores atualizados.

---
## Integrantes

| Nome | RM |
|------|----|
| Roger De Carvalho Paiva |566949 |
|Pedro Henrique Tavares Viana | 567680 |
| David Ernesto Mogollon Gama | 566949 |

### Para mais informações acesse: https://youtu.be/11VGu5MmitE
---
### Codigo do Wokwi: https://wokwi.com/projects/459566050003197953
---
###Fluxo de Comunicação

```text
ESP32 / Wokwi
      ↓
   Wi-Fi
      ↓
 Broker MQTT
      ↓
FIWARE na VM
      ↓
  Postman
      ↓
Consulta e alteração dos dados
