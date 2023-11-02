CC= gcc
CFLAGS= -Wall -Werror -Wextra -std=c11
SANITIZER = -fsanitize=address -fsanitize=leak

CLANG = clang-format

.PHONY = s21_grep

all: s21_grep

s21_grep: s21_grep.c
	$(CC) $(CFLAGS) s21_grep.c -o s21_grep

test:
	@bash grep_test.sh

clean:
	rm -rf s21_grep

rebuild:
	make clean
	make all

sanitize:
	$(CC) $(SANITIZER) s21_grep.c -o s21_grep

leaks:
	leaks -atExit -- ./s21_grep ../common/test_2.txt

clang_n:
	$(CLANG) -style=Google -n *.[ch]

clang_i:
	$(CLANG) -style=Google -i *.[ch]