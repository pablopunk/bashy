# Bashy ⚡️⌨️

<p align="center">
  <a href="https://www.npmjs.com/package/bashy"><img src="https://img.shields.io/npm/dt/bashy.svg" /></a>
</p>
<p align="center">Extremely fast and simple git prompt for bash</p>
<p align="center"><img src="https://raw.githubusercontent.com/pablopunk/art/master/bashy/main.png" /></p>

## Install

You can use the executable from this repo or install it with [npm](https://www.npmjs.com/)

```bash
npm install -g bashy
```

## Usage

In your `~/.bashrc` (linux) or `~/.bash_profile` (MacOS) you need to add `bashy` to your `$PS1`:

```bash
export PS1='$(bashy) $ '
```

This example will give you the next prompt:

```bash
repo at branch✓ $ # if you are in a git repo
folder $ # otherwise
```

You can also choose a path relative to your home folder with the option `-r`:

```bash
export PS1='$(bashy -r) $ '
# results in
~/repos/bashy at master $
```

NOTE: Since version *2.5.0* `bashy` does not support branch status on subdirectories of a repo. This decision meant a 2x increase in performance.

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
real    0m0.010s
user    0m0.004s
sys     0m0.003s
```

> Okay, `bashy` is faster but, come on, `0.094s` is still very fast.

__Yes and no__. While times like those can be indistinguishable for humans, you can totally notice the difference in slower systems and also in fast terminal actions like:

![vs_vcprompt](https://github.com/pablopunk/art/raw/master/bashy/vs_vcprompt.gif)

## Customization

Okay okay, you don't care so much about the performance because you love customization, and tools like `vcprompt` are very good at that. While `bashy` does not have a built in customization option, __it's extremely easy to customize__. Just edit the script, purely bash, and write your own icons there, add more colors, or even rearrange the branch name and directory. Your imagination is the limit here.

You can use your own modified version of bashy cloning this repo and linking it with npm:

```bash
npm remove -g bashy                          # Uninstall the global bashy
git clone https://github.com/pablopunk/bashy # Clone this repo
cd bashy
npm link                                     # Link
bashy                                        # Use it!
```

## Zsh

If you still wanna use ZSH, __`bashy` will work as well as in bash__, but you need to set this option on your `.zshrc`: `setopt PROMPT_SUBST`.


## Author

| ![me](https://www.gravatar.com/avatar/fa50aeff0ddd6e63273a068b04353d9d?s=100) |
| ----------------------------------------------------------------------------- |
| © 2017 [Pablo Varela](https://twitter.com/pablopunk)                          |
