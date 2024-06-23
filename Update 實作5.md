## Lab 5-1 請使用兩個伺服馬達同步從 0 度逐步掃描到 180 度之後再逐步掃描回0度, 每步的間隔時間為50ms (0.05秒)
### 這邊只用90度演示

<!-- code -->

<!-- code
#include <Servo.h>

Servo s9, s8;

void setup()
{
  s9.attach(9, 500, 2500);
  s8.attach(8, 500, 2500);
}

void loop()
{
// 從 0 到 90 度逐步掃描伺服, 1度/步
  for (int i = 0; i <= 90; i++) {

    s9.write(i);
    s8.write(i);   

    delay(50); // 等50ms (0.05秒)
  }
  
  for (int i = 90; i >= 0; i--) {
// 從 90 到 0 度逐步掃描伺服, 1度/步
    s9.write(i);
    s8.write(i);    

    delay(50); // 等50ms (0.05秒)
  }
}
-->

https://github.com/henry9456/Micro-Controller_2024/assets/161188122/278bf714-a1a0-488b-be82-7e0bfbb8d1a5

## Lab 5-2 請使用＂伺服馬達＂以及目前所學過的實作，分析與設計一個自己最獨特的實作並簡單的介紹您的作品.
### 這邊參照老師的範例

<!-- code 
#include <Servo.h>
#include <LiquidCrystal.h>

Servo s9, s8, s7;

int seconds = 0;

LiquidCrystal lcd_1(12, 11, 5, 4, 3, 2);

void setup()
{
  s9.attach(9, 500, 2500);
  s8.attach(8, 500, 2500);
  s7.attach(7, 500, 2500);
  
  lcd_1.begin(16, 2); // Set up the number of columns and rows on the LCD.

  // Print a message to the LCD.
  lcd_1.print("hello world!");
}

void loop()
{
  for (int i = 0; i <= 90; i++) {

    s9.write(i);
    s8.write(i); 
    s7.write(i);
    lcd_1.setCursor(0, 1);
  	lcd_1.print(i);

    delay(50); // 等50ms (0.05秒)
  }
  
  for (int i = 90; i >= 0; i--) {
// 從 90 到 0 度逐步掃描伺服, 1度/步
    s9.write(i);
    s8.write(i);   
    s7.write(i);
    lcd_1.setCursor(0, 1);
	lcd_1.print(i);
    
    delay(50); // 等50ms (0.05秒)
  }
  
 
  lcd_1.setCursor(0, 1);
  lcd_1.print(seconds);
  seconds += 1;
}

-->

https://github.com/henry9456/Micro-Controller_2024/assets/161188122/fbdc084a-0cc7-428f-971b-b18e6dc08085


## Lab 5-3 LCD顯示溫度感應器的溫度;若溫度<38 綠LED亮; 若大於38度, 紅色LED亮

https://github.com/henry9456/Micro-Controller_2024/assets/161188122/6089c932-cb87-4943-a5f7-2031c87af7aa


## Lab 5-４ 請使用＂溫度感應器＂以及目前所學過的實作，分析與設計一個自己最獨特的實作並簡單的介紹您的作品.
### 這邊參考老師範例

https://github.com/henry9456/Micro-Controller_2024/assets/161188122/c068c451-fdad-47e6-ad84-b51c707994b4
