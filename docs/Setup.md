The examples from this project uses the Build Environment for STM32F746 Discovery board offered by Tara Systems
together with the Platform Package dedicated for this board. The examples are constructed to be able to directly
compile and install to the target board, with all the necessary hardware settings in place.

For some of the examples, however a few changes must be implemented in the the default sources and makefiles,
because not all hardware is enabled by default, only those necessary for running the GUI.

##### Modifications needed to the Application/Project/Gcc/Makefile
- for the ADC

`stm32f7xx_hal_adc.c` must be added to the `BSP_C` sources

- for the RNG

`stm32f7xx_hal_rng.c` must be added to the `BSP_C` sources

##### Modifications to the TargetSpecific/stm32f7xx_hal_conf.h
- for the RNG

`#define HAL_RNG_MODULE_ENABLED` must be uncommented
