drake_add_cc_test(pose_aggregator_test)
target_link_libraries(pose_aggregator_test drakeRendering)

if(lcm_FOUND)
  drake_add_cc_test(drake_visualizer_client_test)
  target_link_libraries(drake_visualizer_client_test drakeRenderingLcm drakeLCMTypes)
endif()
