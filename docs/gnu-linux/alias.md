# How to use Alias

Alias it is a form to create a "nickname" to a command or group of commands, for example:

```bash

alias hi="echo hello"
```

> if we open the terminal and write that line command, what are we doing? `alias` is the command, `hi` is our "nickname", that means, it is our own command, such command that will execute the echo command, and the `echo` command show to us a text `hello`

Ok, when we write on terminal `hi`, the output will be `hello`, because the `echo` command is inside of the our `hi` command.

## Add the alias command in .bashrc

When we add the alias command inside the file `.bashrc` that personal command will be recorded in the system, so, we gonna write inside the .bashrc this command `alias hi="echo hello"`, and the .bashrc file exist in the /home/username directory, and .bashrc is a hidden file, thus, to find the .bashrc we could use the command
`ls -a` to show hidden files, and using the `sudo nano` command we can write inside that file.

So we will add the alias command in the final line of the .bashrc file, save the changes, close the terminal and open it again. If we put `hi` on the terminal, the output will be hello.
