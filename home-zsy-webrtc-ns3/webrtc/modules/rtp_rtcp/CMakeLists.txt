# c++11 required
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
include_directories(../../../)
include_directories(../../)
set(rtp_rtcp_format_FILES
include/rtp_rtcp_defines.cc
source/rtcp_packet.cc
source/rtcp_packet/app.cc
source/rtcp_packet/bye.cc
source/rtcp_packet/common_header.cc
source/rtcp_packet/compound_packet.cc
source/rtcp_packet/dlrr.cc
source/rtcp_packet/extended_jitter_report.cc
source/rtcp_packet/extended_reports.cc
source/rtcp_packet/fir.cc
source/rtcp_packet/nack.cc
source/rtcp_packet/pli.cc
source/rtcp_packet/psfb.cc
source/rtcp_packet/rapid_resync_request.cc
source/rtcp_packet/receiver_report.cc
source/rtcp_packet/remb.cc
source/rtcp_packet/report_block.cc
source/rtcp_packet/rrtr.cc
source/rtcp_packet/rtpfb.cc
source/rtcp_packet/sdes.cc
source/rtcp_packet/sender_report.cc
source/rtcp_packet/target_bitrate.cc
source/rtcp_packet/tmmb_item.cc
source/rtcp_packet/tmmbn.cc
source/rtcp_packet/tmmbr.cc
source/rtcp_packet/transport_feedback.cc
source/rtcp_packet/voip_metric.cc
source/rtp_header_extension_map.cc
source/rtp_header_extensions.cc
source/rtp_packet.cc
source/rtp_packet_received.cc
)
add_library(rtp_rtcp_format SHARED ${rtp_rtcp_format_FILES})
target_link_libraries(rtp_rtcp_format system_wrappers rtc_base api)
