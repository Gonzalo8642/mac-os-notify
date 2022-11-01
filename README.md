# mac-os-notify

Create a notification from the command line on MacOS.
Great for getting a notification when a long running task is complete

# Setup

Run the setup script. This will install it in your local path

> This will only install it for the current user, this is means root is not required

```shell
chmod +x setup.sh
./setup.sh
```

# Usage

Once you run the setup script, you should be able to use the `notify` command from your terminal

## Just a notification

```shell
notify
```

## Notification with a custom description

```shell
notify "my description"
```

## Notification with a custom description and title

```shell
notify "my description" "my title"
```

## Notify me when a command succeeds or fails

Paste the following in your `bash_profile` or `zshrc` file

```shell
function notifyMe {
    $* && notify "Task succeeded" || notify "Task failed"
}
```

restart your terminal then run the following to test it

```shell
# should succeed
notifyMe which ls

# should fail
notifyMe which someCommandThatDoesNotExist
```
