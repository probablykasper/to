# my-bash-scripts

These are the bash scripts I've made for myself. They're made for macOS, so there's no guarantee they'll work on other OSes.

# Install

1. Download the scripts and put them in whatever folder you want. In my case, they are in `~/dev/my-bash-scripts/bin`.
2. Now you need to make the scripts executable. You can do that by running `chmod +x <YOUR_FOLDER>/*`.
3. Lastly, add the folder to your PATH, so you can call the scripts by their filename in your terminal from anywhere. Edit the file named `.bash_profile` (or create it if it does not exist). Add the following line to it: `export PATH=<YOUR_FOLDER>:$PATH`.

# scripts

### welp
Super simple script that lists the files in the same folder as the script is in. In other words, it lists the scripts here.

### chill
Stops execution for a specified amount of time. Useful for scheduling stuff. `chill` shows the syntax:
```
Syntax: chill #h
Syntax: chill #m
Syntax: chill #h #m
```

# d-c
Basic wrapper around the `docker-compose` command (which you should have if you got Docker installed). The command works the same as `docker-compose`, except:
- When running `d-c run`, it automatically adds the `--rm` argument
- When running `d-c up`, it automatically runs `docker-compose down` afterwards.

### render
This will render [After Effects](https://www.adobe.com/products/aftereffects.html) projects, assuming you have After Effects installed in `/Applications/Adobe After Effects CC 2019` (Specifically, the `aerender` file needs to be in there). Running `render` shows the syntax:
```
Syntax: render <path>
    path:    After Effects .aep file for aerender to render.
             Can also be a directory that contains .aep files.
```
It was made to be able to support multiple path arguments, as well as taking folders as path arguments to render every .aep file inside those folders, but I don't think that works. Might fix that someday if I need it.

### reset-permissions
Resets permissions of a directory. You should probably know what you're doing before running this.

Running `reset-permissions` shows the syntax:
```
reset-permissions
usage: reset-permissions <username> <directory>
```

This is the command it will run:
```
sudo chmod -RN <DIRECTORY> && \
sudo chown -R <USERNAME> <DIRECTORY> && \
sudo chmod -R 755 <DIRECTORY>
```

### sleepy
Hibernates your computer. I usually run this after `render` or `chill`.

### to-gif
Converts files into gifs. This works, though if you do this frequently I would probably use some app instead.

Requires [ffmpeg](https://ffmpeg.org) (which I recommend installing using [Brew](https://brew.sh))

Running `to-gif` shows the syntax:
```
Syntax: to-gif <file> [fps] [scale] [duration] [start_at]
    file:     File to convert to gif. Required.
    fps:      Defaults to 15.
    scale:    GIF resolution. Defaults to 1.
    duration: How long the gif will be, in seconds. Defaults to 999999.
    start_at: Where the video starts, in seconds. Defaults to 0
```

