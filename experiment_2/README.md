## آزمایش2

## گزارش کار

هدف ازمایش کلید بسته باشه ، لامپ led روشن شود یعنی در حالتی که کلید بازباشد ولتاژ پایه به آن وارد می شود اما به محض بسته شدن کلید مسیر جریان تغییر کرده و ولتاژ پایه صفر به آن وارد خواهد شدled خاموش میشود.  

---

### کد برنامه 

```cpp
int button = 8;
int led = 7;
int buttonState;
void setup() {
pinMode(button, INPUT);
pinMode(led, OUTPUT);
}
void loop() {
buttonState = digitalRead(button);
if (buttonState == LOW)    
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

![micro and circuit](/media/schematic_4.jpg)
