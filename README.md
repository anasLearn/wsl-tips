# wsl-tips

## To update WSL

```
wsl --update
```

## To list the installed distributions

```
wsl -l
```

## To list the available distributions online

```
wsl -l -o
```

## To install a distribution

```
wsl --install distribution-name
```

## To remove a distribution

```
wsl --unregister distribution-name
```

## To shutdown WSL

```
wsl --shutdown
```

# To backup an image of your distibution in your storage drive

```
wsl --export distribution-name .\wsl-backup-images\image-name.tar
```

# To import a saved image and create a new distribution from it

```
wsl --import new-distro-name  installation-folder  backup-image-location
# Example:
wsl --import Ubuntu-18-2nd-distro  .\wsl-installed-distros\ubuntu-18-2nd  .\wsl-backup-images\ubuntu-18-initialized.tar
```

## Usage

Normally Windows Terminal will automatically create a new profile for your new distribution. If that's not the case, you can always run your distribution like this:

```
wsl -d new-distro-name
```

## Setting the default user for your new distribution

By default, when you create a distribution from the backedup image, it will by default run with root whenever you start it. To fix this behaviour:

* Inside your distribution, open `/etc/wsl.conf`
* Add the following lines inside it:
    > ```
    > [user]
    >
    > default=username_you_would_like_to_use
    > ```
* Then shutdown the distribution for the changes to take effect:
    ```
    wsl --terminate new-distro-name
    ```

## Usage with VS Code

* In VS Code in Windows, install the plugin "WSL"
* In your distribution, you can open any folder with VS code by accessing the folder then running:
    ```
    code .
    ```
