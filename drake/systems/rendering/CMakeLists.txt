add_library_with_exports(LIB_NAME drakeRendering SOURCE_FILES
    pose_aggregator.cc
    pose_bundle.cc)
target_link_libraries(drakeRendering
    drakeRBM
    drakeSystemFramework)

drake_install_libraries(drakeRendering)
drake_install_headers(
    pose_aggregator.h
    pose_bundle.h)
drake_install_pkg_config_file(drake-rendering
    TARGET drakeRendering
    LIBS -ldrakeRendering
    REQUIRES
        drake-rbm
        drake-system-framework
)

if(lcm_FOUND)
  add_library_with_exports(LIB_NAME drakeRenderingLcm SOURCE_FILES
      drake_visualizer_client.cc)

  drake_install_libraries(drakeRenderingLcm)
  target_link_libraries(drakeRenderingLcm
      drakeLCMTypes drakeShapes)
  drake_install_headers(
      drake_visualizer_client.h)
  drake_install_pkg_config_file(drake-rendering-lcm
      TARGET drakeRenderingLcm
      LIBS -ldrakeRenderingLcm
      REQUIRES
          drake_lcmtypes
          drake-shapes
  )
endif()

if(BUILD_TESTING)
    add_subdirectory(test)
endif()
