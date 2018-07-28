CC=g++
NAME=server
SRC=server.c
OBJ=$(SRC:%.c=%.o)
TMP=*~
CFLAGS= -W -Wall -Werror -Wextra -pedantic -L. -I.
LIB=-lzmq
RM=rm -f

all: $(NAME)

$(NAME): $(OBJ)
	@$(CC) -o $(NAME) $(OBJ) $(CFLAGS) $(LIB)

%.o: %.c
	@$(CC) -o $@ -c $< $(CFLAGS)

run: re
	./$(NAME) localhost 5555
clean:
	@$(RM) $(OBJ)
	@$(RM) $(TMP)
	@$(RM) \#*\#

fclean: clean
	@$(RM) $(NAME)

re: fclean all

.PHONY: all clean fclean re run
