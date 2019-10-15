VPATH=../../ref_gl ../../linux ../../game

CFLAGS+=-fPIC $(shell sdl-config --cflags)

ref_gl_SRC:=gl_draw.c gl_image.c gl_light.c gl_mesh.c gl_model.c gl_rmain.c\
			gl_rmisc.c gl_rsurf.c gl_warp.c gl_sdl.c glob.c q_shared.c\
			q_shlinux.c qgl_linux.c

ref_gl_OBJ:=$(ref_gl_SRC:.c=.o)

default: ref_gl.so

#include ../make.inc

LDFLAGS+=$(shell sdl-config --libs) -lm -lGL -ljpeg -lpng

ref_gl.so: $(ref_gl_OBJ)
	$(CC) -shared -g -o $@ $^ $(LDFLAGS)
	
