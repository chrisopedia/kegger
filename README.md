# kegger(1)

[Homebrew][homebrew] and [Cask][caskroom] have made it their life's work to automate the installation of various software for Mac OS X developers, either via Brew formulas or Casks.  Their hard work inspired me to create kegger, which is designed to automate the installation of more than 1 cask at a time. You may think to yourself,

> You can already do this with cask by passing it several casks such as `brew cask install alfred dropbox`, what makes this any easier?

The simple answer is nothing.  I have several machines, work, personal, server, etc,. I wanted to be able to install different software without having to remember what was that one line.  Or better yet, I wanted to group the software by its purpose so that I could install them by "categories". Or even better, I could maintain a list of software to update in its own repository and kegger would update and install anything that was new. Ideally this is meant to run alongside your initial machine configuration or setup, such as what I'm doing with [eighth-inning](https://github.com/iamnewton/eighth-inning).

## Requirements

* [Git][git] and [Github account][github]
* [Homebrew][homebrew] (for package installation of the following)
* [jq][jq] (for JSON to bash manipulation)
* [roundup][roundup] (for testing, only required if you are contributing)


## How to install

kegger(1) is a [shell script][bin], so installation is simple.  [Download][download], extract and copy the script in the `bin` directory over to the `/usr/local/bin` directory and make sure it's in your `$PATH`.  The man page, `man kegger`, can be installed by copying over the `kegger.1` file to `/usr/share/man/man1`.

## One-line installation

```bash
$ bash -c "$(curl -#fL raw.github.com/iamnewton/kegger/go/install)"
```

N.B. - using the one-line installation will download and install all of the dependencies, including the man page.

## Usage

```bash
$ kegger [options] <github_gist_id>
```

### Options

| Flag                 | Meaning                                                        |
| :--------------------| :------------------------------------------------------------- |
| `-h, --help`         | Print out help text                                            |
| `-v, --version`      | Print out version                                              |

### How to Create a Keg?

When passing `kegger(1)` a Gist ID, there is a specific format that should be adhered to in order to ensure the script works correctly; I've named this format 'keg'. While a keg file is simply a text file with the extension `.keg`, it doesn't have to be.  What does have to happen? Each file stored on Github's Gist platform should have a single cask on each line.  If you want to see an example, I have created 4 different ones that I currently use, listed below.  If you need to find the name of a Cask, then  you can run `brew cask search <term>`.

* [personal.keg](https://gist.github.com/iamnewton/0b61a78ed66fd94d8277)
* [developer.keg](https://gist.github.com/iamnewton/5ec0bc278d368187cdff)
* [gamer.keg](https://gist.github.com/iamnewton/63e5cc70f0ad92615242)
* [server.keg](https://gist.github.com/iamnewton/57bba889c6017e6f99d7)

## Contributing

Suggestions and contributions are always welcome.  If you'd like to see a new keg and don't feel comfortable creating your own, you can get involved by either [creating an issue](https://github.com/iamnewton/kegger/issues/new), or [forking the code](https://github.com/iamnewton/kegger/fork) and [creating a pull request](https://github.com/iamnewton/kegger/compare/). For more information on how to work with the code, please see the [CONTRIBUTING.md](https://github.com/iamnewton/kegger/blob/master/CONTRIBUTING.md) documentation.

[bin]: https://github.com/iamnewton/kegger/blob/master/bin/kegger
[download]: https://github.com/iamnewton/kegger/archive/master.zip
[github]: https://github.com/join
[git]: http://git-scm.com
[homebrew]: http://brew.sh
[caskroom]: http://caskroom.io
[jq]: https://stedolan.github.io/jq/
[roundup]: https://github.com/bmizerany/roundup
