cmake_minimum_required(VERSION 3.16)
project(OptiSense)

set(CMAKE_CXX_STANDARD 17)

# Path to OpenCV installation
set(OpenCV_DIR "C:/opencv/opencv/build/x64/vc16/lib")
find_package(OpenCV REQUIRED)

# Eigen
include_directories("E:/[2] My Research/My Projects/eigen-3.4.0")

# ONNX Runtime
#find_package(onnxruntime REQUIRED)

# Add your main executable
add_executable(optisense src/main.cpp)

target_include_directories(optisense PRIVATE 
    src 
    ${OpenCV_INCLUDE_DIRS}
)

target_link_libraries(optisense PRIVATE 
    ${OpenCV_LIBS}
    # onnxruntime
)
