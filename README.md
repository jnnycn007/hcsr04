<div align=center>
<img src="/doc/image/logo.png"/>
</div>

## LibDriver DHT11

[English](/README.md) | [ 简体中文](/README_CN.md)

### Table of Contents

  - [Description](#Description)
  - [Instruction](#Instruction)
  - [Install](#Install)
  - [Usage](#Usage)
    - [example basic](#example-basic)
  - [Document](#Document)
  - [Contributing](#Contributing)
  - [License](#License)
  - [Contact Us](#Contact-Us)


### Description

HCSR04 ultrasonic ranging module can provide a non-contact distance sensing function of 2cm-400cm.The ranging accuracy can reach 3mm. The module includes ultrasonic transmitter, receiver and control circuit.

LibDriver HCSR04 is the HCSR04 full function driver launched by LibDriver.It provides the function of ultrasonic ranging.

### Instruction

/src includes LibDriver HCSR04 source files.

/interface includes LibDriver HCSR04 onewire platform independent template。

/test includes LibDriver HCSR04 driver test code and this code can test the chip necessary function simply。

/example includes LibDriver HCSR04 sample code.

/doc includes LibDriver HCSR04 offline document.

/datasheet includes HCSR04 datasheet。

/project includes the common Linux and MCU development board sample code. All projects use the shell script to debug the driver and the detail instruction can be found in each project's README.md.

### Install

Reference /interface gpio platform independent template and finish your platform gpio driver.

Add /src, /interface and /example to your project.

### Usage

#### example basic

```C
uint8_t res;
uint8_t i;
float m;

res = hcsr04_basic_init();
if (res)
{
    return 1;
}

...
    
for (i = 0; i < 3; i++)
{
    res = hcsr04_basic_read((float *)&m);
    if (res)
    {
        hcsr04_basic_deinit();

        return 1;
    }
    hcsr04_interface_delay_ms(1000);
    hcsr04_interface_debug_print("hcsr04: distance is %0.4fm.\n", m);
    
    ...
    
}

...

hcsr04_basic_deinit();

return 0;
```

### Document

Online documents: https://www.libdriver.com/docs/hcsr04/index.html

Offline documents: /doc/html/index.html

### Contributing

Please sent an e-mail to lishifenging@outlook.com

### License

Copyright (C) LibDriver 2015-2021 All rights reserved 



The MIT License (MIT) 



Permission is hereby granted, free of charge, to any person obtaining a copy

of this software and associated documentation files (the "Software"), to deal

in the Software without restriction, including without limitation the rights

to use, copy, modify, merge, publish, distribute, sublicense, and/or sell

copies of the Software, and to permit persons to whom the Software is

furnished to do so, subject to the following conditions: 



The above copyright notice and this permission notice shall be included in all

copies or substantial portions of the Software. 



THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR

IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,

FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE

AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER

LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,

OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE

SOFTWARE. 

### Contact Us

Please sent an e-mail to lishifenging@outlook.com