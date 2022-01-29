## My GitHub page

```markdown
#define MASK(x) ((unsigned char)(1<<x))    //La rotación se hace en el compilador. No consume recursos de procesador.

// En puerto B: Set bits 2 and 5, clear bits 0, 3 and 7
//              If bit 4 is high, then invert bit 1

void manage_PORTB(){
  unit8 temp;
  temp = PTBD;
  temp = temp | (MASK(2) | MASK(5));
  temp = temp & ~(MASK(0) | MASK(3) | MASK(7));
  if(temp & MASK(4))
    temp = temp ^ MASK(1);
  PTBD = temp; 
}
```

