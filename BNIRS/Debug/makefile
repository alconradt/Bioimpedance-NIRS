################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include Drivers/STM32F3xx_HAL_Driver/Src/subdir.mk
-include Core/Startup/subdir.mk
-include Core/Src/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
EXECUTABLES += \
BNIRS.elf \

SIZE_OUTPUT += \
default.size.stdout \

OBJDUMP_LIST += \
BNIRS.list \

OBJCOPY_BIN += \
BNIRS.bin \


# All Target
all: BNIRS.elf secondary-outputs

# Tool invocations
BNIRS.elf: $(OBJS) $(USER_OBJS) /home/andre/Cloud/LIEB/Bioimpedance-NIRS/BNIRS/STM32F303ZETX_FLASH.ld
	arm-none-eabi-gcc -o "BNIRS.elf" @"objects.list" $(USER_OBJS) $(LIBS) -mcpu=cortex-m4 -T"/home/andre/Cloud/LIEB/Bioimpedance-NIRS/BNIRS/STM32F303ZETX_FLASH.ld" --specs=nosys.specs -Wl,-Map="BNIRS.map" -Wl,--gc-sections -static --specs=nano.specs -mfpu=fpv4-sp-d16 -mfloat-abi=hard -mthumb -Wl,--start-group -lc -lm -Wl,--end-group
	@echo 'Finished building target: $@'
	@echo ' '

default.size.stdout: $(EXECUTABLES)
	arm-none-eabi-size  $(EXECUTABLES)
	@echo 'Finished building: $@'
	@echo ' '

BNIRS.list: $(EXECUTABLES)
	arm-none-eabi-objdump -h -S $(EXECUTABLES) > "BNIRS.list"
	@echo 'Finished building: $@'
	@echo ' '

BNIRS.bin: $(EXECUTABLES)
	arm-none-eabi-objcopy  -O binary $(EXECUTABLES) "BNIRS.bin"
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) *
	-@echo ' '

secondary-outputs: $(SIZE_OUTPUT) $(OBJDUMP_LIST) $(OBJCOPY_BIN)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
