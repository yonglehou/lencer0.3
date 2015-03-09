#
# Small/fs/Makefile
#
# (C) 2012-2013 Yafei Zheng
# V0.3 2013-02-23 11:31:15
#
# Email: e9999e@163.com, QQ: 1039332004
#

# --------------------------------------------
# ��������

AS		= 	as
LD		=	ld
ASEFLAGES	=
LDEFLAGES	=	-Ttext 0

CC		=	gcc
# c99��׼֧����forѭ����ʼ������ж������
# -fno-builtin ѡ��ر�GCC�����ú����滻���ܣ������ֹ�� printf("abc\n") �滻Ϊ puts("abc")
# NOTE! ѡ� -fomit-frame-pointer --- ERROR: can't find a register in class 'GENERAL_REGS' while reloading 'asm'.
CEFLAGES		=	-Wall -O0 -std=c99 -I../include -nostdinc -fno-builtin -fomit-frame-pointer
# --------------------------------------------

# --------------------------------------------
all: fs.o

OBJS = buffer.o inode.o alloc.o read_write.o

fs.o: $(OBJS)
	$(LD) -r -o $@ $(OBJS)

buffer.o: buffer.c
	$(CC) $(CEFLAGES) -c $<

inode.o: inode.c
	$(CC) $(CEFLAGES) -c $<

alloc.o: alloc.c
	$(CC) $(CEFLAGES) -c $<

read_write.o: read_write.c
	$(CC) $(CEFLAGES) -c $<
# --------------------------------------------

# --------------------------------------------
# ���
.PHONY: clean
clean:
	-rm *.a *.o
# --------------------------------------------