#
# This file was taken from RakNet 4.082 without any modifications.
# Please see licenses/RakNet license.txt for the underlying license and related copyright.
#

project(MySQLInterface)
IF(NOT WIN32 AND UNIX)
	FILE(GLOB ALL_HEADER_SRCS *.h)
	FILE(GLOB ALL_CPP_SRCS *.cpp)
	FINDMYSQL()
	include_directories(./ ${RAKNETHEADERFILES} ${MYSQL_INCLUDE_DIR}) 
	add_library(LibMySQLInterface STATIC ${ALL_CPP_SRCS} ${ALL_HEADER_SRCS})
	target_link_libraries (LibMySQLInterface ${RAKNET_COMMON_LIBS} ${MYSQL_LIBRARIES})
	VSUBFOLDER(LibMySQLInterface "DependentExtensions")
ENDIF(NOT WIN32 AND UNIX)
