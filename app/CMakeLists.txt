set(RESOURCES_SOURCE_DIR "${CMAKE_CURRENT_SOURCE_DIR}/resources")
set(RESOURCES_DESTINATION_DIR "${CMAKE_CURRENT_BINARY_DIR}/app")

# Add a custom command to copy the resources folder
file(COPY resources DESTINATION "${CMAKE_CURRENT_BINARY_DIR}")
add_executable(Executable main.cpp)
find_package(OpenGL REQUIRED)
find_package(Fontconfig REQUIRED)
target_link_libraries(Executable PUBLIC glfw glad glew OpenGL::GL customClass stb_image glm Fontconfig::Fontconfig)
