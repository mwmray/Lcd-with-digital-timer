################################################################################
# Automatically-generated file. Do not edit!
# Toolchain: GNU Tools for STM32 (10.3-2021.10)
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include Drivers/STM32F1xx_HAL_Driver/Src/subdir.mk
-include Drivers/Device_Drivers/HD44780_LCD/subdir.mk
-include Drivers/ARM_Drivers/Delay_Micros/subdir.mk
-include Core/Startup/subdir.mk
-include Core/Src/subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

OPTIONAL_TOOL_DEPS := \
$(wildcard ../makefile.defs) \
$(wildcard ../makefile.init) \
$(wildcard ../makefile.targets) \


BUILD_ARTIFACT_NAME := LECTURE_ACTIVITY
BUILD_ARTIFACT_EXTENSION := elf
BUILD_ARTIFACT_PREFIX :=
BUILD_ARTIFACT := $(BUILD_ARTIFACT_PREFIX)$(BUILD_ARTIFACT_NAME)$(if $(BUILD_ARTIFACT_EXTENSION),.$(BUILD_ARTIFACT_EXTENSION),)

# Add inputs and outputs from these tool invocations to the build variables 
EXECUTABLES += \
LECTURE_ACTIVITY.elf \

MAP_FILES += \
LECTURE_ACTIVITY.map \

SIZE_OUTPUT += \
default.size.stdout \

OBJDUMP_LIST += \
LECTURE_ACTIVITY.list \

OBJCOPY_HEX += \
LECTURE_ACTIVITY.hex \


# All Target
all: main-build

# Main-build Target
main-build: LECTURE_ACTIVITY.elf secondary-outputs

# Tool invocations
LECTURE_ACTIVITY.elf LECTURE_ACTIVITY.map: $(OBJS) $(USER_OBJS) D:\EMBEDDED\ MATERIAL\LECTURE_ACTIVITY\STM32F103C8TX_FLASH.ld makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-gcc -o "LECTURE_ACTIVITY.elf" @"objects.list" $(USER_OBJS) $(LIBS) -mcpu=cortex-m3 -T"D:\EMBEDDED MATERIAL\LECTURE_ACTIVITY\STM32F103C8TX_FLASH.ld" --specs=nosys.specs -Wl,-Map="LECTURE_ACTIVITY.map" -Wl,--gc-sections -static --specs=nano.specs -mfloat-abi=soft -mthumb -Wl,--start-group -lc -lm -Wl,--end-group
	@echo 'Finished building target: $@'
	@echo ' '

default.size.stdout: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-size  $(EXECUTABLES)
	@echo 'Finished building: $@'
	@echo ' '

LECTURE_ACTIVITY.list: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objdump -h -S $(EXECUTABLES) > "LECTURE_ACTIVITY.list"
	@echo 'Finished building: $@'
	@echo ' '

LECTURE_ACTIVITY.hex: $(EXECUTABLES) makefile objects.list $(OPTIONAL_TOOL_DEPS)
	arm-none-eabi-objcopy  -O ihex $(EXECUTABLES) "LECTURE_ACTIVITY.hex"
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) LECTURE_ACTIVITY.elf LECTURE_ACTIVITY.hex LECTURE_ACTIVITY.list LECTURE_ACTIVITY.map default.size.stdout
	-@echo ' '

secondary-outputs: $(SIZE_OUTPUT) $(OBJDUMP_LIST) $(OBJCOPY_HEX)

fail-specified-linker-script-missing:
	@echo 'Error: Cannot find the specified linker script. Check the linker settings in the build configuration.'
	@exit 2

warn-no-linker-script-specified:
	@echo 'Warning: No linker script specified. Check the linker settings in the build configuration.'

.PHONY: all clean dependents main-build fail-specified-linker-script-missing warn-no-linker-script-specified

-include ../makefile.targets
