BASE=../../../..
include $(BASE)/build/modmake.rules

LOCAL_INSERT_OBJS=echo lws_glue.lo parser.lo audio_pipe.lo
LOCAL_INSERT_LDFLAGS=pkg-config --libs libwebsockets

# Build additional C++ objects
lws_glue.lo: lws_glue.cpp
	$(LTCXXCOMPILE) -std=c++11 -c $< -o $@

parser.lo: parser.cpp  
	$(LTCXXCOMPILE) -std=c++11 -c $< -o $@

audio_pipe.lo: audio_pipe.cpp
	$(LTCXXCOMPILE) -std=c++11 -c $< -o $@

# Make sure C++ objects are built before main target
mod_audio_fork.la: lws_glue.lo parser.lo audio_pipe.lo
