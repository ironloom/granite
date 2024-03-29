
# **granite.**
Granite is our tool to handle working from foreign devices. It uses [Github Access Tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens) to clone, commit and push to your repositories.

## Install ✅
Use the `pip install` command:
```bash
python -m pip install --upgrade graniteloom
```
Install the test version:
```bash
python -m pip install --index-url https://test.pypi.org/simple/ --extra-index-url https://pypi.org/simple --upgrade graniteloom
```
Once the install is complete, check if it worked:
```bash
python -m garniteloom help
```

## How to use?
> The granite CLI uses an eccentric naming system for arguments and argument types:
> - #### **Normals:**
>   ```bash
>   <cmd> <arg1> <arg2> ... <argn>
>   ```
>   Normal args don't have a special syntax, it's just the command.
> - #### **Modifiers:**
>   ```bash
>   <cmd> -modifier <modifier-value> -modifier2 "a modifier accepts strings"
>   ```
>   The modifiers take a value which can be a single word or a string.
> - #### **Tags:**
>   ```bash
>   <cmd> --tag
>   ```
>   Tags modify the command line experience, but they don't take values.

### Show the help menu 📜
The help menu has explanations for all available commands.
```bash
python -m garniteloom help
```

### Clone a repository 📦
If the `-r` and/or `-t` modifiers are not provided, the CLI will prompt you to specify the repository url and the access token.
```bash
python -m garniteloom clone
```

### Workspace ⚗️
The workspace category contains commands which are helpful when managing previously cloned repositories.

1. #### The **`login` / `join`** command:
    You can log into a workspace, this means adding the remote origin by providing the access token and the repository's url. <br>
    If the `-r` and/or `-t` modifiers are not provided, the CLI will prompt you to specify the repository url and the access token.
    ```bash
    python -m garniteloom workspace join
    ```

2. #### The **`logout` / `quit`** command:
    You can logout from a workspace, this removes the remote origin, so you will be able to commit until you sign in again. <br>
    If the `-r` and/or `-t` modifiers are not provided, the CLI will prompt you to specify the repository url and the access token.
    ```bash
    python -m garniteloom workspace quit
    ```

### Modifiers 🛠️
The modifiers used to make managing repositories a bit easier.

1. #### **`-r`** - repository
    The `-r` modifier is used to provide the repository's url.
    > If used alone, without `-t` the CLI will still prompt you for the access token.
    ```bash
    python -m garniteloom clone -r https://github.com/example/repository
    ```

2. #### **`-t`** - token
    The `-t` modifier is used to provide the personal access token.
    > If used alone, without `-r` the CLI will still prompt you for the repository's url.
    ```bash
    python -m garniteloom clone -t <token>
    ```