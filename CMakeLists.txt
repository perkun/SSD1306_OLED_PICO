cmake_minimum_required(VERSION 3.20)

include($ENV{PICO_SDK_PATH}/external/pico_sdk_import.cmake)
pico_sdk_init()

add_library(ssd1306_oled_pico INTERFACE)

file(GLOB_RECURSE SRC_FILES "src/ssd1306/*.cpp")

target_sources(ssd1306_oled_pico INTERFACE ${SRC_FILES})
target_include_directories(ssd1306_oled_pico INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/include)


## uncomment if you want to compile examples

# # Set name of project (as PROJECT_NAME) and C/C++ standards
# project(ssd1306 C CXX ASM)
# set(CMAKE_C_STANDARD 11)
# set(CMAKE_CXX_STANDARD 20)


# # turn on all compiler warnings
# add_compile_options(-Wall -Wextra)

# # Tell CMake where to find the executable source file
# add_executable(${PROJECT_NAME}
#   examples/SSD1306_HELLO/main.cpp
#   #examples/SSD1306_HELLO_128_32/main.cpp
#   #examples/SSD1306_TEXT/main.cpp
#   #examples/SSD1306_GRAPHICS/main.cpp
#   #examples/SSD1306_FUNCTIONS/main.cpp
#   #examples/SSD1306_BITMAP/main.cpp
#   #examples/SSD1306_CLOCK_DEMO/main.cpp
#   #examples/SSD1306_SPEED_TEST/main.cpp
#   #examples/SSD1306_I2C_TEST/main.cpp
# )

# # Create map/bin/hex/uf2 files
# pico_add_extra_outputs(${PROJECT_NAME})

# target_link_libraries(${PROJECT_NAME} pico_stdlib hardware_i2c pico_ssd1306 )
# # Enable usb output, disable uart output
# pico_enable_stdio_usb(${PROJECT_NAME} 1)
# pico_enable_stdio_uart(${PROJECT_NAME} 0)

