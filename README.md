# Detector de Chamas com Arduino Uno 🔥  

## Descrição  

Este projeto utiliza um **Arduino Uno** para detectar a presença de fogo através de um **sensor detector de chamas**. Quando uma chama é identificada, o sistema aciona um **buzzer** e dois **LEDs** (amarelo e vermelho) como sinal de alerta.  

Esse sistema pode ser utilizado para monitoramento de incêndios em pequenos ambientes ou como um estudo introdutório sobre sensores de detecção de fogo.  

## Sumário  

- [Pré-requisitos](#pré-requisitos)  
- [Materiais Necessários](#materiais-necessários)  
- [Esquema de Ligação](#esquema-de-ligação)  
- [Instalação e Configuração](#instalação-e-configuração)  
- [Código](#código)  

## Pré-requisitos  

Para rodar este projeto, você precisará de:  

- **Arduino IDE** (versão mais recente recomendada)  
- **Arduino Uno**  
- **Bibliotecas padrão do Arduino (nenhuma biblioteca extra necessária)**  

## Materiais Necessários  

Você precisará dos seguintes componentes eletrônicos:  

- 1x **Arduino Uno**  
- 1x **Sensor detector de chamas**  
- 1x **Protoboard**  
- 1x **Buzzer ativo**  
- 1x **LED amarelo**  
- 1x **LED vermelho**  
- 2x **Resistores de 220Ω**  
- 5x **Cabos macho-macho**  

## Esquema de Ligação  

### Conexões do Sensor Detector de Chamas  
- **VCC** → 5V do Arduino  
- **GND** → GND do Arduino  
- **D0** → Pino **7** do Arduino  

### Conexões do Buzzer  
- **Anodo (+)** → Pino **3** do Arduino  
- **Catodo (-)** → GND  

### Conexões dos LEDs  
- **Anodo do LED amarelo** → Pino **8** do Arduino  
- **Anodo do LED vermelho** → Pino **9** do Arduino  
- **Catodos dos LEDs** → GND (com resistores de **220Ω**)  

## Instalação e Configuração  

1. **Monte o circuito** conforme o esquema acima.  
2. **Baixe e instale o Arduino IDE** caso ainda não tenha.  
3. **Conecte o Arduino ao computador via cabo USB**.  
4. **Copie o código abaixo** e cole no Arduino IDE.  
5. **Selecione a placa "Arduino Uno" e a porta correta** no menu "Ferramentas".  
6. **Carregue o código para o Arduino** clicando no botão de upload.  

## Código  

int pino_D0 = 7;

int valor_d = 0;
int buzzerPin = 3;
int ledPin_1 = 8;
int ledPin_2 = 9;
 
void setup()
{
  Serial.begin(9600);
  pinMode(pino_D0, INPUT);
  pinMode(buzzerPin, OUTPUT);
  pinMode(ledPin_1, OUTPUT);
  pinMode(ledPin_2, OUTPUT);
}
 
void loop()
{
  int valor_d = digitalRead(pino_D0);
  Serial.print(" Porta digital: ");
  Serial.println(valor_d);
 
  if (valor_d != 1)
  {
    Serial.println("Fogo detectado !!!");
  }
  delay(500);
  {
    if (valor_d != 1)
 { digitalWrite(buzzerPin, HIGH);}
  
  else {digitalWrite(buzzerPin, LOW);}
  }
  if (valor_d != 1)
  {digitalWrite (ledPin_1, HIGH);
  delay(50);
  digitalWrite (ledPin_1, LOW);
  delay(50);}
  else {digitalWrite(ledPin_1, LOW);}
  if (valor_d != 1)
   {digitalWrite(ledPin_2, LOW);
   delay(500);
   digitalWrite(ledPin_2,HIGH);
   delay(50);}
  else  {digitalWrite(ledPin_2, LOW);}
}
