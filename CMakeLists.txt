cmake_minimum_required ( VERSION 2.8)
project ( stitching )

# sources extension
set(SRCEXT "cpp")

file(
    GLOB_RECURSE
    source_files
    *.${SRCEXT}
)

# required packages
find_package ( OpenCV REQUIRED )

# adding the source files to the executable
add_executable(stitching main.cpp main.h MyDescriptorExtractor.cpp MyDescriptorExtractor.hpp MyDescriptorMatcher.cpp MyDescriptorMatcher.hpp MyFeatureDetector.cpp MyFeatureDetector.hpp)


# linking other libraries
target_link_libraries(stitching  ${OpenCV_LIBS})
