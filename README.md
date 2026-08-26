# Pratica-controle-de-dois-leds

# Pratica Conrole de dois LEDs

Discente: Gabriel Maciel Ribeiro

Docente: Amanda Paul Dull

Esse repositório serve de exemplo para a entrega de atividades da matéria de IoT.

[![Simular no Tinkercad](https://www.tinkercad.com/things/0dNkUfwLUEB-atividade-com-varios-leds))](https://www.tinkercad.com/things/0dNkUfwLUEB-atividade-com-varios-leds))](https://www.tinkercad.com/things/0dNkUfwLUEB-atividade-com-varios-leds)

## Enunciado:Atividade 01 - LED

O projeto vai utilizar um botão como entrada para controlar um LED como saída. Ao pressionar o botão, o Arduino altera o estado do LED — cada clique liga ou desliga, funcionando como um interruptor eletrônico.

- O Arduino lê o estado do botão pelo **pino 7**
- Controla o LED pelo **pino 10**

## Materiais necessários

| Qtd | Componente |
|-----|------------|
| 1 | Placa Arduino UNO |
| 1 | Cabo USB |
| 1 | Protoboard |
| 1 | Resistor de 200 Ω ou 220 Ω |
| 1 | Resistor de 10 kΩ |
| 1 | Botão tipo push button |
| 1 | LED vermelho difuso de 5 mm |
| — | Fios de jumper macho-macho |


IMAGEM: <img width="836" height="766" alt="image" src="https://github.com/user-attachments/assets/28705ddd-9cd9-47f1-8012-1800d45fa86c" />

Código: // C++ code
//
// DigitalRead = lê
// DigitalWrite = envia

int led1 = 10;
int led2 = 13;
int botao = 8;
int contador = 0;

void setup()
{
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
  pinMode(botao, INPUT);
}

void loop()
{
 
  if (digitalRead(botao) == HIGH){
   contador++;
    
    if( contador >3){
      contador = 1;
    }
    delay(200);
    while (digitalRead(botao) == HIGH) {
      
    }
    delay(50);
  }
  
  if (contador == 1) {
    digitalWrite(led1, HIGH);
     digitalWrite(led2, LOW);
  }
  
  if (contador == 2) {
    digitalWrite(led2, HIGH);
     digitalWrite(led1, LOW);
  }
  
  if (contador == 3) {
    digitalWrite(led1, LOW);
     digitalWrite(led2, LOW);
  }
}


