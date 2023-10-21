cmake_minimum_required(VERSION 3.24)
project(NS3ku)

set(CMAKE_CXX_STANDARD 17)

file (STRINGS "ns3lib-loc.txt" BUILD_LOC)

set(NS3Ver 3.40)
set(NS3BUILDDIR ${BUILD_LOC}/ns-allinone-${NS3Ver}/ns-${NS3Ver}/build)

link_directories(
        ${NS3BUILDDIR}
        ${NS3BUILDDIR}/lib
)

add_executable(${PROJECT_NAME}
        main.cpp
        )

target_include_directories(${PROJECT_NAME} PUBLIC
        ${NS3BUILDDIR}
        ${NS3BUILDDIR}/include
        )

target_link_libraries(${PROJECT_NAME}
        ns${NS3Ver}-antenna-default
        ns${NS3Ver}-antenna-test-default
        ns${NS3Ver}-aodv-default
        ns${NS3Ver}-aodv-test-default
        ns${NS3Ver}-applications-default
        ns${NS3Ver}-applications-test-default
        ns${NS3Ver}-brite-default
        ns${NS3Ver}-brite-test-default
        ns${NS3Ver}-bridge-default
        ns${NS3Ver}-buildings-default
        ns${NS3Ver}-buildings-test-default
        ns${NS3Ver}-click-default
        ns${NS3Ver}-click-test-default
        ns${NS3Ver}-config-store-default
        ns${NS3Ver}-core-default
        ns${NS3Ver}-core-test-default
        ns${NS3Ver}-csma-default
        ns${NS3Ver}-csma-layout-default
        ns${NS3Ver}-dsdv-default
        ns${NS3Ver}-dsdv-test-default
        ns${NS3Ver}-dsr-default
        ns${NS3Ver}-dsr-test-default
        ns${NS3Ver}-energy-default
        ns${NS3Ver}-energy-test-default
        ns${NS3Ver}-fd-net-device-default
        ns${NS3Ver}-flow-monitor-default
        ns${NS3Ver}-internet-apps-default
        ns${NS3Ver}-internet-apps-test-default
        ns${NS3Ver}-internet-default
        ns${NS3Ver}-internet-test-default
        ns${NS3Ver}-lr-wpan-default
        ns${NS3Ver}-lr-wpan-test-default
        ns${NS3Ver}-lte-default
        ns${NS3Ver}-lte-test-default
        ns${NS3Ver}-mesh-default
        ns${NS3Ver}-mesh-test-default
        ns${NS3Ver}-mobility-default
        ns${NS3Ver}-mobility-test-default
        ns${NS3Ver}-mpi-default
        ns${NS3Ver}-mpi-test-default
        ns${NS3Ver}-netanim-default
        ns${NS3Ver}-netanim-test-default
        ns${NS3Ver}-network-default
        ns${NS3Ver}-network-test-default
        ns${NS3Ver}-nix-vector-routing-default
        ns${NS3Ver}-nix-vector-routing-test-default
        ns${NS3Ver}-olsr-default
        ns${NS3Ver}-olsr-test-default
        ns${NS3Ver}-openflow-default
        ns${NS3Ver}-openflow-test-default
        ns${NS3Ver}-point-to-point-default
        ns${NS3Ver}-point-to-point-layout-default
        ns${NS3Ver}-point-to-point-test-default
        ns${NS3Ver}-propagation-default
        ns${NS3Ver}-propagation-test-default
        ns${NS3Ver}-sixlowpan-default
        ns${NS3Ver}-sixlowpan-test-default
        ns${NS3Ver}-spectrum-default
        ns${NS3Ver}-spectrum-test-default
        ns${NS3Ver}-stats-default
        ns${NS3Ver}-stats-test-default
        ns${NS3Ver}-tap-bridge-default
        ns${NS3Ver}-topology-read-default
        ns${NS3Ver}-topology-read-test-default
        ns${NS3Ver}-traffic-control-default
        ns${NS3Ver}-traffic-control-test-default
        ns${NS3Ver}-uan-default
        ns${NS3Ver}-uan-test-default
        ns${NS3Ver}-virtual-net-device-default
        ns${NS3Ver}-visualizer-default
        #ns3.39-wave-default        # remove
        #ns3.39-wave-test-default   # remove
        ns${NS3Ver}-wifi-default
        ns${NS3Ver}-wifi-test-default
        ns${NS3Ver}-wimax-default
        ns${NS3Ver}-wimax-test-default
        )

add_definitions(-DNS3_LOG_ENABLE)