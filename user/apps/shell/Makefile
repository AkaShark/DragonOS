all: shell.o cmd.o cmd_help.o

	ld -b elf64-x86-64 -z muldefs -o $(tmp_output_dir)/shell  $(shell find . -name "*.o") $(shell find $(sys_libs_dir) -name "*.o") -T shell.lds

	objcopy -I elf64-x86-64 -R ".eh_frame" -R ".comment" -O elf64-x86-64 $(tmp_output_dir)/shell $(output_dir)/shell.elf
shell.o: shell.c
	gcc $(CFLAGS) -c shell.c  -o shell.o

cmd.o: cmd.c
	gcc $(CFLAGS) -c cmd.c  -o cmd.o

cmd_help.o: cmd_help.c
	gcc $(CFLAGS) -c cmd_help.c  -o cmd_help.o
