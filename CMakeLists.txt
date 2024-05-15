#
# Copyright (c) 2019 Nordic Semiconductor ASA
#
# SPDX-License-Identifier: LicenseRef-Nordic-5-Clause
#
cmake_minimum_required(VERSION 3.20.0)

find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(light_switch)

# NORDIC SDK APP START
target_sources(app PRIVATE
	src/main.c
	src/model_handler.c
	src/lib/model/prov_helper_cli.c
	src/lib/model/prov_helper_srv.c
	src/lib/prov_stage/provisioner_stage.c)
target_include_directories(app PRIVATE include)
target_include_directories(app PRIVATE src/lib/model)
target_include_directories(app PRIVATE src/lib/prov_stage)

# NORDIC SDK APP END
