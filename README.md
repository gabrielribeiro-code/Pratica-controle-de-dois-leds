# Pratica-controle-de-dois-leds

# Pratica Conrole de dois LEDs

Discente: Gabriel Maciel Ribeiro

Docente: Amanda Paul Dull

Esse repositório serve de exemplo para a entrega de atividades da matéria de IoT.

[![Simular no Tinkercad](https://www.tinkercad.com/things/0dNkUfwLUEB-atividade-com-varios-leds))](https://www.tinkercad.com/things/0dNkUfwLUEB-atividade-com-varios-leds))](https://www.tinkercad.com/things/0dNkUfwLUEB-atividade-com-varios-leds)

## Enunciado:Atividade 02 - LED's

O projeto vai utilizar um botão como entrada para controlar dois LED como saída. Ao pressionar o botão, primeiro vai acender o led1, após clicar a segunda vez desliga um e acende o outro, depois fica os dois apagados e depois volta toda o processo no quarto aperto.

- O Arduino lê o estado do botão pelo **pino 8**
- Controla o LED1 pelo **pino 10**
- - Controla o LED2 pelo **pino 13**

## Materiais necessários

| Qtd | Componente |
|-----|------------|
| 1 | Placa Arduino UNO |
| 1 | Cabo USB |
| 1 | Protoboard |
| 2 | Resistor de 200 Ω ou 220 Ω |
| 1 | Resistor de 10 kΩ |
| 1 | Botão tipo push button |
| 1 | LED vermelho difuso de 5 mm |
| 1 | LED verde difuso de 5 mm |
| 9 | Fios de jumper macho-macho |


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


