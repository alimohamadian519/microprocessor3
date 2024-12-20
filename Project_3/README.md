# آزمایش3

### گزارش کار 

در اینجا هدف ما ایجاد یک الگوریتم برای رقص نور LEDهاست. یک آرایه ۴x۴ می‌سازیم که در هر ردیف آن فقط یک درایه ۱ (HIGH) و بقیه درایه‌ها صفر هستند. با یک حلقه تو در تو، وضعیت روشن/خاموش بودن هر LED بر اساس درایه‌های آرایه مشخص می‌شود. حلقه داخلی هر بار یک LED را تنظیم می‌کند و به سراغ بعدی می‌رود. پس از اتمام یک ردیف، حلقه بیرونی به ردیف بعدی آرایه می‌رود و این چرخه تا پایان ردیف‌ها تکرار می‌شود.
---

### کد برنامه
این کد یک الگوریتم رقص نور برای چهار LED ایجاد می‌کنه:1. key1 وضعیت کلید فشاری متصل به پین A0 رو چک می‌کنه.
2. توی setup، پین A0 به‌عنوان ورودی و چهار پین ۰ تا ۳ به‌عنوان خروجی تنظیم می‌شن.
3. توی loop:
   - همه LEDها خاموش می‌شن.
   - اگر کلید فشاری فشار داده بشه (key1 == 0):
     - حلقه‌های تو در تو هر LED رو بر اساس الگوی آرایه dancingLight روشن و خاموش می‌کنن.
     - این چرخه با تاخیر 200 میلی‌ثانیه تکرار می‌شه تا جلوه رقص نور ایجاد بشه.

به این ترتیب، با فشردن کلید فشاری، چهار LED به ترتیب روشن و خاموش می‌شن تا رقص نور جذابی ایجاد کنن.

```cpp
#define key1 digitalRead(A0)    

void setup() {
  pinMode(A0, INPUT);
  for (int i = 0; i < 4; i++) {     
    pinMode(i, OUTPUT);
  }
}
void loop() {
  int i, a;
  int dancingLight[4][4] = {
    {0, 0, 0, 1},
    {0, 0, 1, 0},
    {0, 1, 0, 0},
    {1, 0, 0, 0},
  };

  for (i = 0; i < 4; i++) {     
    digitalWrite(i, 0);
  }

  if (key1 == 0) {      
    for (a = 0; a < 4; a++) {  
      for (i = 0; i < 4; i++) { 
        digitalWrite(i, dancingLight[a][i]);    
      }
      delay(200);   
    }
  }
};
```

---

### تصویر مدار ( بدون متصل بودن کلید ) 

![micro and circuit](/pic/microprocessor_5.jpg)

---

### تصویر مدار ( عملکرد با کلید ) 

![micro and circuit](/pic/microprocessor_6.jpg)

---

### شماتیک مدار 

![micro and circuit](/pic/schematic_5.jpg)
