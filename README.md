# Minishell Project
This project is a minimal shell implementation in C, supporting various built-in functions like `cd`, `echo`, `env`, `exit`, `export`, `pwd`, and `unset`, as well as the ability to execute other commands, handle signals, and manage environment variables. The project includes lexer and parser modules to process and execute commands, a tree structure to represent the commands, and several utility functions.

## Features
- Built-in functions: `cd`, `echo`, `env`, `exit`, `export`, `pwd`, `unset`.
- Execution of external commands.
- Signal handling (SIGINT, SIGQUIT).
- Redirections (input, output, append) and pipes.
- Environment variable expansion.
- Syntax error handling.
- Command history.

## Directory Structure
```
.
├── built-in/
│   ├── cd.c
│   ├── echo.c
│   ├── env.c
│   ├── exit.c
│   ├── export.c
│   ├── export_helper.c
│   ├── pwd.c
│   └── unset.c
├── env/
│   ├── env_init.c
│   └── env_utils.c
├── exec/
│   ├── exec_cmd.c
│   ├── exec_cmd_utils.c
│   └── exec_redir.c
├── lexer/
│   ├── check_for_heredoc.c
│   ├── check_quotes.c
│   ├── dollar_sign.c
│   ├── expand_quotes.c
│   ├── expand_var.c
│   ├── lexer.c
│   ├── split_line.c
│   ├── split_utils.c
│   ├── split_utils2.c
│   ├── syntax.c
│   ├── syntax_utils.c
│   ├── token_utils.c
│   └── var_finder.c
├── tree/
│   ├── create_tree.c
│   ├── free_tree.c
│   ├── parse_args_list.c
│   ├── parse_cmd_node.c
│   ├── parse_redir_node.c
│   └── utils.c
├── utils/
│   ├── free_double_ptr.c
│   ├── ft_atol.c
│   ├── ft_listsize.c
│   └── ft_strcmp.c
├── heredoc_signals.c
├── main.c
├── signals.c
```

## File Descriptions

### built-in
- `cd.c`: Contains the `ft_cd` function to change the current working directory and update the environment variables.
- `echo.c`: Contains the `ft_echo` function to print its arguments to the standard output.
- `env.c`: Contains the `ft_env` function to print the current environment variables.
- `exit.c`: Contains the `ft_exit` function to terminate the shell.
- `export.c`: Contains the `ft_export` function to export environment variables.
- `export_helper.c`: Contains helper functions for the `export` built-in.
- `pwd.c`: Contains the `pwd` function to print the current working directory.
- `unset.c`: Contains the `ft_unset` function to unset environment variables.

### env
- `env_init.c`: Contains functions to initialize the environment variables.
- `env_utils.c`: Contains utility functions for managing environment variables.

### exec
- `exec_cmd.c`: Contains functions to execute commands.
- `exec_cmd_utils.c`: Contains utility functions for command execution.
- `exec_redir.c`: Contains functions to handle redirections.

### lexer
- `check_for_heredoc.c`: Contains functions to check for and handle heredocs.
- `check_quotes.c`: Contains functions to check the validity of quotes in the input.
- `dollar_sign.c`: Contains functions to handle dollar sign expansion.
- `expand_quotes.c`: Contains functions to expand quotes in the input.
- `expand_var.c`: Contains functions to expand variables in the input.
- `lexer.c`: Contains the main lexer functions to tokenize the input.
- `split_line.c`: Contains functions to split the input line into tokens.
- `split_utils.c`: Contains utility functions for splitting the input.
- `syntax.c`: Contains functions to check the syntax of the input.
- `syntax_utils.c`: Contains utility functions for syntax checking.
- `token_utils.c`: Contains utility functions for managing tokens.
- `var_finder.c`: Contains functions to find and extract variables from the input.

### tree
- `create_tree.c`: Contains functions to create the command tree from tokens.
- `free_tree.c`: Contains functions to free the command tree.
- `parse_args_list.c`: Contains functions to parse arguments into a list.
- `parse_cmd_node.c`: Contains functions to parse command nodes.
- `parse_redir_node.c`: Contains functions to parse redirection nodes.
- `utils.c`: Contains utility functions for the tree module.

### utils
- `free_double_ptr.c`: Contains a function to free a double pointer.
- `ft_atol.c`: Contains a function to convert a string to a long integer.
- `ft_listsize.c`: Contains a function to get the size of a list.
- `ft_strcmp.c

`: Contains a function to compare two strings.

### root
- `heredoc_signals.c`: Contains functions to handle signals during heredoc processing.
- `main.c`: Contains the `main` function to start the shell.
- `signals.c`: Contains functions to handle signals during the main shell execution.

## Usage
1. Clone the repository.
2. Run `make` to compile the source files.
3. Run `./minishell` to start the shell.

## Example
```
$ ./minishell
minishell> echo Hello, world!
Hello, world!
minishell> pwd
/home/user/minishell
minishell> cd ..
minishell> pwd
/home/user
minishell> exit
$
```

## Conclusion
The Minishell project is a challenging and rewarding exercise in systems programming, requiring a deep understanding of various aspects of the C programming language, as well as knowledge of shell behavior, environment variables, and signal handling. The final result is a functional shell with support for various built-in functions, command execution, redirections, and pipes. This project provides a strong foundation for further exploration and development in the field of systems programming.
