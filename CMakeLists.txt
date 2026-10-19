cmake_minimum_required(VERSION 3.18)
project(GloverAndroidPort C CXX)

set(CMAKE_CXX_STANDARD 17)

# Incluir archivos de cabecera y librerías del juego
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src)

# Escanear todos los archivos C y C++ del proyecto
file(GLOB_RECURSE SOURCES "src/*.c" "src/*.cpp")

# Crear la librería nativa (.so) para Android
add_library(main SHARED ${SOURCES})

# Enlazar con las librerías gráficas y del sistema Android
target_link_libraries(main log GLESv2 EGL z)
