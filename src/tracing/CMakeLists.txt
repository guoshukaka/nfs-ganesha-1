include_directories(
  ${LTTNG_INCLUDE_DIR}
)

set(ganesha_trace_LIB_SRCS
  logger.c
  nfs_rpc.c
)

add_library(ganesha_trace MODULE ${ganesha_trace_LIB_SRCS})

target_link_libraries(ganesha_trace
  ${LTTNG_LIBRARIES}
)

install(TARGETS ganesha_trace COMPONENT tracing DESTINATION ${FSAL_DESTINATION} )
