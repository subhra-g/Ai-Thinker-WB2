#
# This is a project Makefile. It is assumed the directory this Makefile resides in is a
# project subdirectory.
#

PROJECT_NAME := demo_ssd1306
PROJECT_PATH := $(abspath .)
PROJECT_BOARD := evb
export PROJECT_PATH PROJECT_BOARD
#CONFIG_TOOLPREFIX :=

-include ./proj_config.mk

ifeq ($(origin BL60X_SDK_PATH), undefined)
BL60X_SDK_PATH_GUESS ?= $(shell pwd)
BL60X_SDK_PATH ?= $(BL60X_SDK_PATH_GUESS)/../../..
$(info ****** Please SET BL60X_SDK_PATH ******)
$(info ****** Trying SDK PATH [$(BL60X_SDK_PATH)])
endif

COMPONENTS_BLSYS   := bltime blfdt blmtd bloop loopset looprt
COMPONENTS_VFS     := romfs

INCLUDE_COMPONENTS += freertos_riscv_ram
INCLUDE_COMPONENTS += bl602 bl602_std
INCLUDE_COMPONENTS += hosal mbedtls_lts lwip cli vfs yloop utils blog blog_testc newlibc
INCLUDE_COMPONENTS += rfparam_adapter_tmp
INCLUDE_COMPONENTS += $(COMPONENTS_NETWORK)
INCLUDE_COMPONENTS += $(COMPONENTS_BLSYS)
INCLUDE_COMPONENTS += $(COMPONENTS_VFS)
INCLUDE_COMPONENTS += $(PROJECT_NAME)

include $(BL60X_SDK_PATH)/make_scripts_riscv/project.mk
