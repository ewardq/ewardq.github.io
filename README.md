## My GitHub page

```markdown
#define MASK(x) ((unsigned char)(1<<x)) 

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

