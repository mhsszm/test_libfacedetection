CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
PROJECT (facedetection)
SET(CMAKE_CXX_STANDARD 11)
SET(CMAKE_CXX_STANDARD_REQUIRED ON)
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O3")
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -march=native")
SET(BUILD_SHARED_LIBS ON)

FIND_PACKAGE(OpenCV REQUIRED)

INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/src
                    ${OpenCV_INCLUDE_DIRS})
ADD_LIBRARY(facedetection src/facedetectcnn.cpp 
                          src/facedetectcnn-floatdata.cpp 
                          src/facedetectcnn-int8data.cpp 
                          src/facedetectcnn-model.cpp)
ADD_EXECUTABLE(face_detect example/libfacedetectcnn-example.cpp)
TARGET_LINK_LIBRARIES(face_detect ${OpenCV_LIBS} facedetection)
