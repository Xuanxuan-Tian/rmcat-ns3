# c++11 required
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
include_directories(../../../)
include_directories(../../)
set(pacing_FILES
alr_detector.cc
bitrate_prober.cc
interval_budget.cc
paced_sender.cc
packet_queue.cc
packet_queue2.cc
#packet_queue_interface.cc
packet_router.cc
)
add_library(pacing SHARED ${pacing_FILES})
target_link_libraries(pacing logging rtc_base )
