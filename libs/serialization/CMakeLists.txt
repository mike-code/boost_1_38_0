#----------------------------------------------------------------------------
# This file was automatically generated from the original CMakeLists.txt file
# Add a variable to hold the headers for the library
set (lib_headers
    serialization
    archive
)

# Add a library target to the build system
boost_library_project(
  serialization
  SRCDIRS  src
  TESTDIRS  test
  HEADERS ${lib_headers}
  #  DOCDIRS 
  DESCRIPTION  "Serialization for persistence and marshalling."
  MODULARIZED 
  AUTHORS  "<ramey -at- rrsd.com>"
  #  MAINTAINERS 
)


