AUTOMAKE_OPTIONS=foreign

lib_LTLIBRARIES=libjsonxx.la
libjsonxx_la_SOURCES= jsonxx.cc
libjsonxx_la_CFLAGS = -g  -Werror -Wall
##是供其它程序包含用的header，make install时会复制到安装目录的include 目录中。
include_HEADERS=jsonxx.h


##INCLUDES= -I../include     #依赖的头文件目录  


noinst_PROGRAMS=test 
test_SOURCES=jsonxx_test.cc
test_LDADD =  -L${srcdir} libjsonxx.la 