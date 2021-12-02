#define F_CPU 16000000

#include <avr/io.h>

uint8_t top_switch_state;
uint8_t bottom_switch_state;

void floatSwitchInit(void)
{
 /* top sensor */ DDRD &= ~(1<<0); //set pinD0 as input
 PORTD |= (1<<0); //use pull-up resistor on pinD0
 
 /* bottom sensor */ DDRD &= ~(1<<1); //set pinD1 as input
 PORTD |= (1<<1); //use pull-up resistor on pinD1
}

void relayInit(void)
{
 DDRB |= (1<<1); //set pinB1 as output
 PORTB &= ~(1<<1); //set portB1 low
}

int main(void)
{
 //Initialize the components
    floatSwitchInit();
    relayInit();
 
    while (1)
 {   
  //if water is above top level, turn off pump
  top_switch_state = PIND & (1<<0);
  if (top_switch_state == 0)
  {
   PORTB &= ~(1<<PORTB1); 
  }
  //if water is below bottom level, turn on pump
  bottom_switch_state = PIND & (1<<1);
  if (bottom_switch_state == (1<<1))
  {
   PORTB |= (1<<PORTB1);
  }
 }
}
