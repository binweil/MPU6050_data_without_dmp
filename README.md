# MPU6050_data_without_dmp
Read data from MPU6050 without using the digital motion processor (customized algorithm)

## 实验器材:
	STM32F4 Explore
	
## 实验目的:
	MPU6050 六轴传感器(三轴加速度+三轴陀螺仪)的使用.
	
## 硬件资源:
	1.DS0(连接在PF9)
	2.UART1(波特率:115200,PA9/PA10连接在板载USB转串口芯片CH340上面
	3.MPU6050传感器(连接在PB8(SCL),PB9(SDA)上面,INT(PC0)未用到).

## 实验现象:
	开机后，先初始化MPU6050，然后利用DMP库，初始化MPU6050及使能DMP，最后，在死循环里面不停
	读取：温度传感器、加速度传感器、陀螺仪、DMP姿态解算后的欧拉角等数据，通过串口上报给上位机（温
	度不上报），利用上位机软件（ANO_Tech匿名四轴上位机_V2.6.exe），可以实时显示MPU6050的传感器状
	态曲线，并显示3D姿态，可以通过KEY0按键开启/关闭数据上传功能。同时，在LCD模块上面显示温度和欧拉
	角等信息。DS0来指示程序正在运行。另外,也可以通过USMART调用MPU_Read_Byte/MPU_Write_Byte
	等函数,来实现对MPU6050寄存器的读写操作(仅在UPLOAD OFF状态下).
	
## 注意事项: 
	1.USB供电可能不足,请用外部电源适配器(推荐外接12V 1A电源).
	2.串口波特率保持一致
