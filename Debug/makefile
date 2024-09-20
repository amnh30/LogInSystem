################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include MDIO/subdir.mk
-include HLCD/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
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

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
LogInSystem.lss \

FLASH_IMAGE += \
LogInSystem.hex \

SIZEDUMMY += \
sizedummy \


# All Target
all: LogInSystem.elf secondary-outputs

# Tool invocations
LogInSystem.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,LogInSystem.map -mmcu=atmega32 -o "LogInSystem.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

LogInSystem.lss: LogInSystem.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S LogInSystem.elf  >"LogInSystem.lss"
	@echo 'Finished building: $@'
	@echo ' '

LogInSystem.hex: LogInSystem.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex LogInSystem.elf  "LogInSystem.hex"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: LogInSystem.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega32 LogInSystem.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) LogInSystem.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
