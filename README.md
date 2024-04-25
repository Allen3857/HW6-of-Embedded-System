# HW6-of-Embedded-System

#################### **Problem 6-1** ####################  
To modify the trigger frequency, we can change the "htim1.Init.Period" term in line 156 of main_6-1.cpp file. In our main_6-1.cpp, we change this value from 1000 - 1 to 10000 - 1.  

Since 1 / (80M / 4000 (prescaler)) * 1000 = 0.05, the data will be printed out every 0.05 seconds. Similarly, from 1 / (80M / 4000 (prescaler)) * 10000 = 0.5, the data will be printed out every 0.5 seconds.  

To modify the sampling time of ADC, we can change the "sConfig.SamplingTime" term in line 110 of main_6-1.cpp file. In our main_6-1.cpp, we change this value from ADC_SAMPLETIME_2CYCLES_5 to ADC_SAMPLETIME_640CYCLES_5.  

Note that ADC_SAMPLETIME_XCYCLES_5 stands for "Sampling time X.5 ADC clock cycles", and the X value can be 2, 6, 12, 24, 47, 92, 247,or 640. For example, ADC_SAMPLETIME_2CYCLES_5 means "Sampling time 2.5 ADC clock cycles".  
###################################################  
  
#################### **Problem 6-2** ####################  
For the first todo in function "HAL_ADC_ConvCpltCallback", we just write "event_queue.call(Upper_Printed);". The Upper_Printed function will print the data in buffer[128:255] when this part is filled.  

For the second todo in function "HAL_ADC_ConvHalfCpltCallback", we just write "event_queue.call(Lower_Printed);". The Lower_Printed function will print the data in buffer[0:127] when this part is filled.  

For the last todo in function "HAL_ADC_Start_DMA", just write "&hadc1, (uint32_t *)sample_buffer, SAMPLE_BUFFER_SIZE".  

Since 1 / (80M / 4000 (prescaler)) * 1000 * 128 = 6.4, the data will be printed out every 6.4 seconds.  
###################################################  

#################### **Problem 6-3** ####################  
In this part, we choose D2 and D3 as pin1 and pin2, respectively. If the buffer is half-filled, toggle pin1; if the buffer is filled, toggle pin2.  

Note that after the buffer is full, use "BSP_AUDIO_IN_Stop" function and call the eventqueue.  

Run the code and connect to the logic analyzer, then you can see the toggling of pin1 and pin2.  
###################################################  
