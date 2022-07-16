add_definitions(-DNS3_WOSS_SUPPORT -DWOSS_MULTITHREAD)

link_libraries(WOSS)

include_directories(/opt/WOSS/woss /opt/WOSS/woss/woss_def /opt/WOSS/woss/woss_db)

build_lib(
        LIBNAME woss-ns3
        SOURCE_FILES
        model/definitions/woss-location.cc
        model/definitions/woss-time-reference.cc
        model/definitions/woss-random-generator.cc
        model/woss-prop-model.cc
        model/woss-channel.cc
        model/woss-position-allocator.cc
        model/woss-waypoint-mobility-model.cc
        helper/woss-helper.cc
        HEADER_FILES
        model/definitions/woss-location.h
        model/definitions/woss-time-reference.h
        model/definitions/woss-random-generator.h
        model/woss-prop-model.h
        model/woss-channel.h
        model/woss-position-allocator.h
        model/woss-waypoint-mobility-model.h
        helper/woss-helper.h
        LIBRARIES_TO_LINK
        ${libnetanim}
        ${libnetwork}
        ${libenergy}
        ${libmobility}
        ${libuan}
        #  TEST_SOURCES test/uan-energy-model-test.cc
        #               test/uan-test.cc
)
