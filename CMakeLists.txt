# Copyright (C) 2007-2012 LuaDist.
# Submitted by David Manura
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

# warning: compilation options might not be optical

project ( infozip C )
cmake_minimum_required ( VERSION 2.8 )
include ( cmake/dist.cmake )

set ( SRC_UNZIP crc32.c crypt.c envargs.c explode.c extract.c fileio.c globals.c 
  inflate.c list.c match.c process.c ttyio.c ubz2err.c unreduce.c unshrink.c unzip.c 
  zipinfo.c )
if ( WIN32 AND NOT CYGWIN )
  set ( SRC_UNZIP ${SRC_UNZIP} win32/crc_i386.c win32/nt.c win32/win32.c win32/win32i64.c )
else ( )
  add_definitions ( -DUNIX )
  set ( SRC_UNZIP ${SRC_UNZIP} unix/unix.c )
endif ( )

include_directories ( . )

include ( CheckFunctionExists )
check_function_exists ( lchmod HAVE_LCHMOD )
if ( NOT HAVE_LCHMOD )
  add_definitions ( -DNO_LCHMOD )
endif ( )

add_executable ( unzip ${SRC_UNZIP} )

install_executable ( unzip )
install_data ( README LICENSE )
