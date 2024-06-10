add_executable(Rasteriser
    Rasteriser.cpp
)

target_link_libraries(Rasteriser tgaimage model)
