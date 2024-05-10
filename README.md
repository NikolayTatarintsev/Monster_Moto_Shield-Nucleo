# Monster_Moto_Shield-Nucleo
###### Monster Moto Shield &amp; Nucleo H743ZI2
####     ОБОРУДОВАНИЕ
###### 1. Nucleo-H743ZI2 (на базе микроконтроллера STM32H743ZIT6U , 32-разрядный, 480 МГц, ARM Cortex, RISC, 2 МБ флэш;
[Документация:]( https://github.com/NikolayTatarintsev/Monster_Moto_Shield-Nucleo/blob/main/um2407-stm32h7-nucleo144-boards-mb1364-stmicroelectronics.pdf) um2407-stm32h7-nucleo144-boards-mb1364-stmicroelectronics.pdf
</div>

###### 2. Monster Moto Shield (на базе двух драйверов VNH2SP30).
[Документация:]( https://github.com/NikolayTatarintsev/Monster_Moto_Shield-Nucleo/blob/main/VNH2SP30-E.pdf) VNH2SP30-E.pdf
###### На рисунке представлена Nucleo-H743ZI2 с установленным Monster Moto Shield, схематично показано подключение электродвигателя (мотора) постоянного тока М и источника питания 12 VDC.

<div style="display: flex; justify-content: center;">
 <img src="https://github.com/NikolayTatarintsev/Monster_Moto_Shield-Nucleo/blob/main/MMSh_Nucleo_motor.jpg" alt="Image 1" style="width: 600px; height: auto;">
</div>
<br>

###### Monster Moto Shield устанавливается на плату Nucleo-H743ZI2 в коннекторы  ST Zio (совместимы с Arduino). Таблица соединений приведена в файле NuclH743ZI2_MonstMSh_tabl.pdf.
[Таблица соединений:]( https://github.com/NikolayTatarintsev/Monster_Moto_Shield-Nucleo/blob/main/NuclH743ZI2_MonstMSh_tabl.pdf
) NuclH743ZI2_MonstMSh_tabl.pdf
</div>
<br>


###### Для управления электродвигателем с помощью Monster Moto Shield требуется:
- разрешить работу требуемого драйвера;
- задать требуемое направление вращения электродвигателя: разрешить  работу на вращение по часовой стрелке CW и запретить работу против часовой стрелки CCW (для реверса соответственно наоборот);
- задать требуемую скорость электродвигателя: с помощью ШИМ (PWM) сформировать требуемую величину напряжения для электродвигателя.

####   ПРОГРАММА 
###### Программа запускает электродвигатель (мотор М1) на 5 секунд, осуществляет его останов на 1 секунду и затем осуществляет реверс (производится вращение электродвигателя в обратном направлении в течении 5 секунд), после этого цикл работы повторяется.
[Пограмма:]( https://github.com/NikolayTatarintsev/Monster_Moto_Shield-Nucleo/blob/main/main.c) main.c, разработана в STM32CubeIDE
</div>

###### Параметры ШИМ (PWM),  отвечающие за период ШИМ и коэффициент заполнения, соответственно:
Counter Period (16 bits value): 30000; Pulse (16 bits value): 7000

######
<div style="display: flex; justify-content: center;"> 
<img src="https://github.com/NikolayTatarintsev/Monster_Moto_Shield-Nucleo/blob/main/akip_osc1.jpg" alt="Image 1" style="width: 600px; height: auto;">
</div>
<br>
