cmake_minimum_required(VERSION 2.8.5 FATAL_ERROR)
if(POLICY CMP0025)
  cmake_policy(SET CMP0025 NEW) # CMake 3.0
endif()

PROJECT (LabeledMesh)

find_package(VTK COMPONENTS
  vtkCommonCore
  vtkCommonDataModel
  vtkFiltersSources
  vtkInteractionStyle
  vtkRenderingLabel
  vtkRenderingOpenGL
)
include(${VTK_USE_FILE})

add_executable(${PROJECT_NAME} MACOSX_BUNDLE ${PROJECT_NAME}.cxx)
target_link_libraries(${PROJECT_NAME} ${VTK_LIBRARIES})
