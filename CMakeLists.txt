cmake_minimum_required(VERSION 3.9)
# define library
project(luna_raytracer VERSION 1.0.0 DESCRIPTION "Simple raytracing library")

# Build the library
add_library(luna_raytracer SHARED
	# core
	src/core/Bucket.cpp
	src/core/Core.cpp
	src/core/FifoBucketOrder.cpp
	src/core/FrameBuffer.cpp
	src/core/MultiChannelPixelQuantifier.cpp
	src/core/RandomBucketOrder.cpp
	src/core/Ray.cpp
	src/core/Raytracer.cpp
	src/core/RenderTask.cpp
	src/core/SimplePixelQuantifier.cpp
	src/core/SingleChannelPixelQuantifier.cpp
	src/core/ThreadPool.cpp
	# io
	src/io/LoadASC.cpp
	src/io/PNGWriter.cpp
	# math
	src/math/Random.cpp
	src/math/Transform.cpp
	src/math/Vector.cpp
	# src
	src/scene/AABBox.cpp
	src/scene/Disk.cpp
	src/scene/DiskAreaLight.cpp
	src/scene/GradientBackground.cpp
	src/scene/LensCamera.cpp
	src/scene/LightHasAttenuation.cpp
	src/scene/PinholeCamera.cpp
	src/scene/Plane.cpp
	src/scene/PointLight.cpp
	src/scene/Scene.cpp
	src/scene/SimpleCameraMount.cpp
	src/scene/SkyLight.cpp
	src/scene/SolidBackground.cpp
	src/scene/Sphere.cpp
	src/scene/SphereAreaLight.cpp
	src/scene/Triangle.cpp
	src/scene/TriangleMesh.cpp
)

set_target_properties(luna_raytracer PROPERTIES VERSION ${PROJECT_VERSION})
set_target_properties(luna_raytracer PROPERTIES SOVERSION ${PROJECT_VERSION_MAJOR})

target_include_directories(mylib PRIVATE include)
target_include_directories(mylib PRIVATE src)
