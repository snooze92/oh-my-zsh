## Important note

This is simply a fork of the original robbyrussell Oh-my-ZSH repository, where I...
- added some plugins that I found were missing;
- duplicated and customized the theme I use
- checked new zshrc templates in

Feel free to use this repo instead of the original, but I would highly recommend you either __use the original repo or create your own fork__. This fork was created for my personal use and although I will try my best, I cannot guarantee that I will do a great job I staying up to date with upstream...

To learn more about Oh-my-ZSH, visit [ohmyz.sh](http://ohmyz.sh).

## Getting Started

### Prerequisites

__Disclaimer:__ _Oh My Zsh works best on macOS and Linux._

* Unix-like operating system (macOS or Linux)
* [Zsh](http://www.zsh.org) should be installed (v4.3.9 or more recent). If not pre-installed (`zsh --version` to confirm), check the following instruction here: [Installing ZSH](https://github.com/snooze92/oh-my-zsh/wiki/Installing-ZSH)
* `curl` or `wget` should be installed
* `git` should be installed

### Basic Installation

I did update the `tools/install.sh` file to point to this fork's URL, so you can use the basic installation method!
Oh My Zsh is installed by running one of the following commands in your terminal. You can install this via the command-line with either `curl` or `wget`.

#### via curl

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/snooze92/oh-my-zsh/master/tools/install.sh)"
```

#### via wget

```shell
sh -c "$(wget https://raw.githubusercontent.com/snooze92/oh-my-zsh/master/tools/install.sh -O -)"
```

## Using Oh My Zsh

### Plugins

Oh My Zsh comes with a shit load of plugins to take advantage of. You can take a look in the [plugins](https://github.com/snooze92/oh-my-zsh/tree/master/plugins) directory and/or the [wiki](https://github.com/snooze92/oh-my-zsh/wiki/Plugins) to see what's currently available.

#### Enabling Plugins

Once you spot a plugin (or several) that you'd like to use with Oh My Zsh, you'll need to enable them in the `.zshrc` file. You'll find the zshrc file in your `$HOME` directory. Open it with your favorite text editor and you'll see a spot to list all the plugins you want to load.

For example, this line might begin to look like this:

```shell
plugins=(git bundler osx rake ruby)
```

#### Using Plugins

Most plugins (should! we're working on this) include a __README__, which documents how to use them.

### Themes

We'll admit it. Early in the Oh My Zsh world, we may have gotten a bit too theme happy. We have over one hundred themes now bundled. Most of them have [screenshots](https://wiki.github.com/snooze92/oh-my-zsh/themes) on the wiki. Check them out!

#### Selecting a Theme

_Robby's theme is the default one. It's not the fanciest one. It's not the simplest one. It's just the right one (for him)._

Once you find a theme that you want to use, you will need to edit the `~/.zshrc` file. You'll see an environment variable (all caps) in there that looks like:

```shell
ZSH_THEME="robbyrussell"
```

To use a different theme, simply change the value to match the name of your desired theme. For example:

```shell
ZSH_THEME="agnoster" # (this is one of the fancy ones)
# you might need to install a special Powerline font on your console's host for this to work
# see https://github.com/snooze92/oh-my-zsh/wiki/Themes#agnoster
```

Open up a new terminal window and your prompt should look something like this:

![Agnoster theme](https://cloud.githubusercontent.com/assets/2618447/6316862/70f58fb6-ba03-11e4-82c9-c083bf9a6574.png)

In case you did not find a suitable theme for your needs, please have a look at the wiki for [more of them](https://github.com/snooze92/oh-my-zsh/wiki/External-themes).

If you're feeling feisty, you can let the computer select one randomly for you each time you open a new terminal window.


```shell
ZSH_THEME="random" # (...please let it be pie... please be some pie..)
```


## Advanced Topics

If you're the type that likes to get their hands dirty, these sections might resonate.

### Advanced Installation

Some users may want to change the default path, or manually install Oh My Zsh.

#### Custom Directory

The default location is `~/.oh-my-zsh` (hidden in your home directory)

If you'd like to change the install directory with the `ZSH` environment variable, either by running `export ZSH=/your/path` before installing, or by setting it before the end of the install pipeline like this:

```shell
export ZSH="$HOME/.dotfiles/oh-my-zsh"; sh -c "$(curl -fsSL https://raw.githubusercontent.com/snooze92/oh-my-zsh/master/tools/install.sh)"
```

#### Manual Installation

##### 1. Clone the repository:

```shell
git clone git://github.com/snooze92/oh-my-zsh.git ~/.oh-my-zsh
```

##### 2. *Optionally*, backup your existing `~/.zshrc` file:

```shell
cp ~/.zshrc ~/.zshrc.orig
```

##### 3. Create a new zsh configuration file

You can create a new zsh config file by copying the template that we have included for you.

```shell
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

##### 4. Change your default shell

```shell
chsh -s /bin/zsh
```

##### 5. Initialize your new zsh configuration

Once you open up a new terminal window, it should load zsh with Oh My Zsh's configuration.

### Installation Problems

If you have any hiccups installing, here are a few common fixes.

* You _might_ need to modify your `PATH` in `~/.zshrc` if you're not able to find some commands after switching to `oh-my-zsh`.
* If you installed manually or changed the install location, check the `ZSH` environment variable in `~/.zshrc`.

### Custom Plugins and Themes

If you want to override any of the default behaviors, just add a new file (ending in `.zsh`) in the `custom/` directory.

If you have many functions that go well together, you can put them as a `XYZ.plugin.zsh` file in the `custom/plugins/` directory and then enable this plugin.

If you would like to override the functionality of a plugin distributed with Oh My Zsh, create a plugin of the same name in the `custom/plugins/` directory and it will be loaded instead of the one in `plugins/`.

## Getting Updates

By default, you will be prompted to check for upgrades every few weeks. If you would like `oh-my-zsh` to automatically upgrade itself without prompting you, set the following in your `~/.zshrc`:

```shell
DISABLE_UPDATE_PROMPT=true
```

To disable automatic upgrades, set the following in your `~/.zshrc`:

```shell
DISABLE_AUTO_UPDATE=true
```

### Manual Updates

If you'd like to upgrade at any point in time (maybe someone just released a new plugin and you don't want to wait a week?) you just need to run:

```shell
upgrade_oh_my_zsh
```

Magic!

## Uninstalling Oh My Zsh

Oh My Zsh isn't for everyone. We'll miss you, but we want to make this an easy breakup.

If you want to uninstall `oh-my-zsh`, just run `uninstall_oh_my_zsh` from the command-line. It will remove itself and revert your previous `bash` or `zsh` configuration.
