cmake_minimum_required(VERSION 3.14)
project(EdgePredictEngine)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(OpenCASCADE REQUIRED)
find_package(Eigen3 REQUIRED)
find_package(nlohmann_json REQUIRED)

include_directories(include ${OpenCASCADE_INCLUDE_DIR} ${EIGEN3_INCLUDE_DIR})

file(GLOB SOURCES "src/*.cpp")

add_executable(edgepredict-engine ${SOURCES})

target_link_libraries(edgepredict-engine PRIVATE 
    ${OpenCASCADE_LIBRARIES}
    Eigen3::Eigen
    nlohmann_json::nlohmann_json
)
