# exp2ledblink
## CODE:
Don't write comment lines
```
#include <lpc214x.h>

void delay_ms(unsigned int count)
{
  unsigned int j=0,i=0;
  for(j=0;j<count;j++)
  {
    for(i=0;i<3000;i++);
  }
}

int main() 
{
    PINSEL0 = 0x00000000;  //Configure the P1 Pins for GPIO;
    IO0DIR = 0xffffffff; //Configure the P1 pins as OUTPUT;

  while(1)
    {
       IO0SET = 0xffffffff;     // Make all the Port pins as high  
				//IO0SET=1<<16; // if they ask seperate pin then use this(if p0.16 then put 1<<16 likewise replace 16)
			//IO0SET=1<<31;  //it selects p0.31
			//IO0SET=1<<1;   //it selects p0.1
         delay_ms(1000);

       IO0CLR = 0xffffffff;     // Make all the Port pins as low  
         delay_ms(1000);
    }
}
```
