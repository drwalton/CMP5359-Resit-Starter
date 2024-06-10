cmake_minimum_required(VERSION 3.6)

project(CMP5359-Resit LANGUAGES CXX)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

include_directories(3rdParty/tgaimage)
include_directories(3rdParty/model)
include_directories(3rdParty/eigen-3.4.0)
include_directories(3rdParty/nlohmann)


find_package(OpenMP)

add_library(tgaimage
    3rdParty/tgaimage/tgaimage.cpp
    3rdParty/tgaimage/tgaimage.h
)

add_library(model
    3rdParty/model/Model.cpp
    3rdParty/model/Model.hpp
)

add_subdirectory(Rasteriser)
add_subdirectory(Raytracer)