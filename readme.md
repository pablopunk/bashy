# Bashy ⚡️⌨️

<p align="center">Extremely fast and simple git prompt for bash</p>

![main](https://raw.githubusercontent.com/pablopunk/art/master/bashy/main.png)

## Install

You need `bashy` to run as any other command, so install it in any directory in your $PATH. I like to use `/opt/bin`:

```bash
$ cp bashy /opt/bin/bashy
$ echo export PATH=$PATH:/opt/bin >> ~/.bashrc       # Linux
$ echo export PATH=$PATH:/opt/bin >> ~/.bash_profile # MacOS
```

## Usage

In your `bashrc` (linux) or `bash_profile` (MacOS) you need to add `bashy` to your `$PS1`:

```bash
export PS1='\[$(bashy)\] $'
```

This example will give you the next prompt:

```bash
repo at branch✓ $ # if you are in a git repo
folder $ # otherwise
```

## Benchmarks

I've been a `zsh` user for a long time just for the prompts of `oh-my-zsh`. But because `oh-my-zsh` started to slow my prompt so much I decided to go back to `bash`  and make my own customizations.

The first tool I used to do so was `vcprompt`, but the speed was not improving a lot.

If we compare `bashy` to other tools like `vcprompt` we can see is much faster:

```bash
$ time vcprompt
real    0m0.094s
user    0m0.037s
sys     0m0.024s

$ time bashy
real    0m0.024s
user    0m0.010s
sys     0m0.008s
```

> Okay, `bashy` is faster but, come on, `0.094s` is still very fast.

__Yes and no__. While times like those can be indistinguishable for humans, you can totally notice the difference in slower systems and also in fast terminal actions like:

![vs_vcprompt](https://github.com/pablopunk/art/raw/master/bashy/vs_vcprompt.gif)

## Customization

Okay okay, you don't care so much about the performance because you love customization, and tools like `vcprompt` are very good at that. While `bashy` does not have a built in customization option, __it's extremely easy to customize__. Just edit the script, purely bash, and write your own icons there, add more colors,  or even rearrange the branch name and directory. Your imagination is the limit here.


## Author

© 2017 [Pablo Varela](https://twitter.com/pablopunk)
