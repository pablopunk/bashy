# Bashy

<p align="center">Extremely fast and simple git prompt for bash</p>

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

If we compare `bashy` to other tools like `vcprompt` we can see is much faster:

```bash
$ time $(vcprompt -f "%b%m " -M "\[\e[1;31m\]⨯\[\e[0m\]")

real    0m0.063s
user    0m0.038s
sys     0m0.017s

$ time $(bashy)

real    0m0.024s
user    0m0.010s
sys     0m0.008s
```

> Okay, `bashy` is faster but, come on, `0.063s` is still very fast.

__Yes and no__. While times like those can be indistinguishable for humans, you can totally notice the difference in slower systems and also in fast terminal actions like:

