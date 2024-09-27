# lcd1602a-i2c-driver

## Overview

Common **LCD1602A-I2C** driver for my projects. **PCF8574 I2C Expander** needed along with LCD1602A. Compatible with STM32CubeIDE. Multiple lcds can be attached with different I2C ports.

- Tested on STM32F446RE

## Use Locally

Clone the project

```bash
  git clone https://github.com/TaskinOkmen/lcd1602a-i2c-driver.git
```

## Usage/Examples

```c
#include "main.h"
#include "lcd1602a.h"

I2C_HandleTypeDef hi2c1;

LCD1602A lcd;

...

/**
  * @brief  The application entry point.
  * @retval int
  */
int main(void) {

    /* other init functions */
    MX_I2C1_Init();

    // call after i2c init
    LCD_Init(&lcd, &hi2c1);

    LCD_SetCursor(&lcd, 0, 0);
    LCD_WriteString(&lcd, "TEST MESSAGE");

    ...
}

```

## References
- [LCD1602A Datasheet](https://www.alldatasheet.com/datasheet-pdf/pdf/1574132/CRYSTAIFONTZ/LCD-1602A.html)

- [PCF8574 I2C Expander Datasheet](https://www.alldatasheet.com/view.jsp?Searchword=Pcf8574%20datasheet&gad_source=1&gclid=Cj0KCQjwr9m3BhDHARIsANut04bxH2tIj1KUDg6ses6e1XJSxptad1srrdCgAEn4j_PyJfiuNnPwXFcaAld3EALw_wcB)

## Authors

- [@TaskinOkmen](https://www.github.com/TaskinOkmen)