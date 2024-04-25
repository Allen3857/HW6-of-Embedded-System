# HW6-of-Embedded-System

########################################## **Problem 6-1** ###########################################  
To modify the trigger frequency, we can change the "htim1.Init.Period" term in line 156 of main_6-1.cpp file. In our main_6-1.cpp, we change this value from 1000 - 1 to 10000 - 1.  

The original trigger frequency is 1 / (80M / 4000 (prescaler)) * 1000 = 0.05, so the data will be printed out every 0.05 second. The new trigger frequency is 1 / (80M / 4000 (prescaler)) * 10000 = 0.5, so the data will be printed out every 0.5 second.  

To modify the sampling time of ADC, we can change the "sConfig.SamplingTime" term in line 110 of main_6-1.cpp file. In our main_6-1.cpp, we change this value from ADC_SAMPLETIME_2CYCLES_5 to ADC_SAMPLETIME_640CYCLES_5.  

Note that ADC_SAMPLETIME_XCYCLES_5 stands for "Sampling time X.5 ADC clock cycles", and the X value can be 2, 6, 12, 24, 47, 92, 247,or 640. For example, ADC_SAMPLETIME_2CYCLES_5 means "Sampling time 2.5 ADC clock cycles".  
################################################################################################  
  
########################################## **Problem 6-2** ###########################################  
Not yet completed, still working.  
################################################################################################  

########################################## **Problem 6-3** ###########################################  
Not yet completed, still working.  
################################################################################################  
