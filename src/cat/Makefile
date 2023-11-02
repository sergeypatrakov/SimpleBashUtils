CC= gcc
CFLAGS= -Wall -Werror -Wextra -std=c11
SANITIZER = -fsanitize=address -fsanitize=leak

CLANG = clang-format

.PHONY = s21_cat

all: s21_cat

s21_cat: s21_cat.c
	$(CC) $(CFLAGS) s21_cat.c -o s21_cat

test:
	@bash cat_test.sh

clean:
	rm -f s21_cat

rebuild:
	make clean
	make all

sanitize:
	$(CC) $(SANITIZER) s21_cat.c -o s21_cat

leaks:
	leaks -atExit -- ./s21_cat ../common/test_2.txt

clang_n:
	$(CLANG) -style=Google -n *.[ch]

clang_i:
	$(CLANG) -style=Google -i *.[ch]