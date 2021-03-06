# Armoury

A small package manager for [Kakoune](http://kakoune.org).

## Installation

Clone this repo or place `armoury.kak` into your autoloads folder. For example:

```sh
git clone git@github.com:leemachin/armoury.git ~/.config/kak/autoload/armoury
```

Restart and Bob's your uncle.

## Usage

Armoury tries to work similarly to similar package scripts like [vim-plug](https://github.com/junegunn/vim-plug).

To load packages, add this to your `kakrc`:

```kak
armoury-equip %{
  mawww/kak-ycmd
  lenorf/kakoune-extras
}
```

When initialising, Armoury will clone each package from GitHub and make sure it is loaded. This will
happen in the background so it doesn't slow the editor down :)

If something doesn't appear to work as expected, you can check the `*armoury*` buffer for any errors.

## Updating packages

Packages will not be updated by default, but you can trigger this process by calling
`:armoury-update` from normal mode. This will go through each installed package and pull
the latest commits on the master branch.

## Configuration

By default, packages are downloaded to `~/.config/kak/autoload`, but you can change this.

```kak
set global armourydir %sh{ echo ~/my/new/directory }
```

Echoing from a shell is required to expand your home directory.

## Limitations

- Only github repositories are supported
- Specific versions of a package cannot be equipped, only the latest from master
- Using `set` to configure an option will fail when that option hasn't yet loaded
  (Workaround: put your `set` configs inside a `KakBegin` hook)
- Packages must be cleaned up manually with `armoury-clean` for the time being

## Contributing

Pull requests welcome ;) be kind! Be constructive.

## License

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <http://unlicense.org/>
