if(Bullet_FOUND)
  drake_add_cc_test(rigid_body_plant_test)
  target_link_libraries(rigid_body_plant_test
      drakeMultibodyParsers
      drakeRigidBodyPlant)

  drake_add_cc_test(compute_contact_result_test)
  target_link_libraries(compute_contact_result_test
      drakeRigidBodyPlant
      drakeRBSystem
      )

  drake_add_cc_test(contact_force_formula_test)
  target_link_libraries(contact_force_formula_test
      drakeRigidBodyPlant
      drakeRBSystem
      )

  if (lcm_FOUND)
    drake_add_cc_test(rigid_body_plant_that_publishes_xdot_test)
    target_link_libraries(rigid_body_plant_that_publishes_xdot_test
        drakeLcm
        drakeMultibodyParsers
        drakeRigidBodyPlant)

    drake_add_cc_test(viewer_draw_translator_test)
    target_link_libraries(viewer_draw_translator_test drakeRigidBodyPlant)

    drake_add_cc_test(drake_visualizer_test)
    target_link_libraries(drake_visualizer_test
        drakeRigidBodyPlant
        drakeSystemAnalysis)
  endif()
endif()

drake_add_cc_test(contact_force_test)
target_link_libraries(contact_force_test drakeRigidBodyPlant)

drake_add_cc_test(contact_resultant_force_test)
target_link_libraries(contact_resultant_force_test drakeRigidBodyPlant)

drake_add_cc_test(contact_detail_test)
target_link_libraries(contact_detail_test drakeRigidBodyPlant)

drake_add_cc_test(contact_info_test)
target_link_libraries(contact_info_test drakeRigidBodyPlant)

drake_add_cc_test(kinematics_results_test)
target_link_libraries(kinematics_results_test
    drakeMultibodyParsers
    drakeRigidBodyPlant)
