## آزمایش1

## گزارش کار 

با زدن کلید ledخاموش و روشن میشود

---

### کد برنامه 

```cpp
int button = 8;
int led = 7;
int buttonState = 0;   
void setup() {
pinMode(button, INPUT);
pinMode(led, OUTPUT);
}
void loop() {
buttonState = digitalRead(button);  
if (buttonState == HIGH)  
  {
  digitalWrite(led, HIGH);
  }
  else {
    digitalWrite(led, LOW);
  }
}
```

---

### تصویر مدار 

![micro and circuit](/pic/microprocessor_4.jpg)

---

### شماتیک مدار 

![micro and circuit](/media/schematic_3.jpg)
