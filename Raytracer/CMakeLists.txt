set(ENTITIES_SOURCE_GROUP
    AABB.hpp
    BVHNode.hpp
    BVHLeafNode.hpp
    Entity.hpp
    Renderable.hpp
    Scene.hpp
    Sphere.hpp
    Plane.hpp
    Triangle.hpp
    Mesh.hpp
)

set(LIGHTS_SOURCE_GROUP
    Light.hpp
    PointLight.hpp
    DirectionalLight.hpp
)

set(SHADERS_SOURCE_GROUP
    Shader.hpp
    LambertianShader.hpp
    TexturedLambertianShader.hpp
    PhongShader.hpp
    MirrorShader.hpp
    TexCoordTestShader.hpp
)

source_group("Header Files\\Entities" FILES ${ENTITIES_SOURCE_GROUP})
source_group("Header Files\\Lights" FILES ${LIGHTS_SOURCE_GROUP})
source_group("Header Files\\Shaders" FILES ${SHADERS_SOURCE_GROUP})

add_executable(Raytracer
    Raytracer.cpp

    GeomUtil.hpp

    Ray.hpp
    HitInfo.hpp
    Camera.hpp

    BitMasks.hpp

    ${ENTITIES_SOURCE_GROUP}
    ${LIGHTS_SOURCE_GROUP}
    ${SHADERS_SOURCE_GROUP}
)


if(OpenMP_CXX_FOUND)
    target_link_libraries(Raytracer PUBLIC OpenMP::OpenMP_CXX tgaimage model)
else()
    target_link_libraries(Raytracer tgaimage model)
endif()



