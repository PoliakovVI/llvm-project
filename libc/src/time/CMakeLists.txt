add_object_library(
  time_utils
  SRCS
    time_utils.cpp
  HDRS
    time_utils.h
)

add_entrypoint_object(
  gmtime
  SRCS
    gmtime.cpp
  HDRS
    gmtime.h
  DEPENDS
    .time_utils
    libc.include.errno
    libc.include.time
    libc.src.errno.__errno_location
)

add_entrypoint_object(
  mktime
  SRCS
    mktime.cpp
  HDRS
    mktime.h
  DEPENDS
    .time_utils
    libc.include.errno
    libc.include.time
    libc.src.errno.__errno_location
)
