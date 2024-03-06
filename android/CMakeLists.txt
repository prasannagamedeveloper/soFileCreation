# android/CMakeLists.txt
cmake_minimum_required(VERSION 3.4.1)

add_library(
    your_library
    SHARED
    ../src/your_library.cpp
)

# Include header files from src directory
target_include_directories(your_library PRIVATE ../src)

# Specify additional libraries or dependencies if needed
# target_link_libraries(your_library dependency_library)

# Set the Android ABI (Architecture) for which to build
set_target_properties(your_library PROPERTIES
    ANDROID_ABI armeabi-v7a arm64-v8a x86 x86_64
)

# Specify the minimum Android version
set_target_properties(your_library PROPERTIES
    ANDROID_VERSION 21
)

# Link against necessary Android libraries
target_link_libraries(your_library
    log
    android
)
