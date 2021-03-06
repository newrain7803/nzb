# Nzb

[![crates.io](https://img.shields.io/crates/v/nzb.svg?style=flat)](https://crates.io/crates/nzb) [![crates.io](https://img.shields.io/crates/d/nzb.svg?style=flat)](https://crates.io/crates/nzb) [![Build Status](https://gitlab.com/reisub0/nzb/badges/master/build.svg)](https://gitlab.com/reisub0/nzb/badges/master/build.svg?style=flat) [![made-with-rust](https://img.shields.io/badge/made%20with%20♥-rust-dea584.svg)](https://www.rust-lang.org/)



A beautiful CLI front-end for Nozbe written in Rust.

The core functionality of the excellent [Wunderline](https://github.com/wayneashleyberry/wunderline) app for Wunderlist is already present.

## What is Nozbe?

[Nozbe](https://nozbe.com/) is an amazing to-do list and task management system that follows the Getting Things Done (GTD)® philosophy. The basic idea is to have an Inbox where you simply fill ideas and tasks as you get them throughout the day. Tasks in the Inbox are further processed based on their priority and urgency, and then finally, executed.

Nozbe has pretty good apps for web, desktop and mobile. However, I found all these quite lacking in terms of speed and usability. The overhead of switching between my projects to find the certain task I wanted to mark as done was a bit too much to handle. So I took some inspiration from the Wunderline app, and made this!


## Features

- Extremely usable interface

- Takes literally 10 seconds to set up

- Add tasks to your Nozbe inbox in 2 seconds flat

- Mark multiple tasks as done, or star them, with Fuzzy Search. All in a couple of jiffies! Made possible by the [skim library](https://github.com/lotabout/skim)

- Conky integration for printing a nice summary (an Android widget but for your desktop)



![nzb-conky-screenshot-of-desktop](https://user-images.githubusercontent.com/25099244/54476743-e2a60900-4826-11e9-8085-19a6d6e35d23.png)


## Usage

```
$ nzb help
Nozbe front-end written in Rust.

Usage:
  nzb [options] [<command> [<args>...]]
  nzb -h | --help
  nzb --version

Options:
  -a <token> --auth=<token>    Specify an alternate Nozbe authentication token (Refer Nozbe API Documentation)
                               (Note: The default authentication token is at $HOME/.local/.nozbe_token)
  -h --help                    Show this screen
  -V --version                 Show version

Commands:
  add <name>                   Add a task to your Nozbe Inbox
  all                          View all of your tasks (This is the default action)
  cat <category>               View all tasks in a category
  conky                        A conky-friendly, colourful summary of all your tasks
  done                         Mark task(s) as done with fuzzy search
  help                         Show this screen
  inbox                        View your inbox
  link <link>                  Add a link to your inbox (adds a comment with link)
  list [<list>...]             Show specific lists
  login                        Login to Nozbe
  now | priority | starred     View starred tasks
  open                         Open Nozbe in your browser
  overdue                      View tasks that are overdue
  star                         Star task(s) with fuzzy search
  today                        View tasks that are due today
  unstar                       Unstar task(s) with fuzzy search
```

### Logging in

To start using `nzb` please run `nzb login` and follow the instructions.

### Adding tasks

Simply run `nzb add <task title>`

[![gif of add feature](https://user-images.githubusercontent.com/25099244/54518414-33824280-498a-11e9-8df3-54775d6a6b93.gif)](https://asciinema.org/a/234104)

### Starring/Unstarring/Marking tasks as done

Running `nzb <star|unstar|done> [query]` opens a fuzzy search window with all the tasks that match the optional query. Multi-select tasks with Tab and select any one with Enter.

[![gif of done feature](https://user-images.githubusercontent.com/25099244/54518412-32e9ac00-498a-11e9-8032-987c89cbfcd2.gif)](https://asciinema.org/a/234102)

Click on the link above to see a demo.

### Conky integration

In your `conky.conf`, find the `conky.text` section. add
```
${texecpi 60 nzb conky}
```
where 60 is how often(in seconds) you want the view to be updated.


## Installation

### From Binaries

Binary releases can be found at the [Releases](https://gitlab.com/reisub0/nzb/tags) page.  Select the version number, click the download icon and download `linux-x86_64` artifacts. Unzip `artifacts.zip` to obtain your binary at `target/release/nzb`. 

Note: Currently only **`linux-x86_64`** is supported: macOS users can install from `cargo` or from source; support for Windows is unlikely due to a dependency on `termion`. PRs are highly appreciated for getting it working on Windows.

### Arch Linux (From AUR)

Use your favourite AUR Helper and install [`nzb-bin`](https://aur.archlinux.org/packages/nzb-bin/)
```bash
yay -S nzb-bin
```
### From Crates.io

```bash
cargo install nzb
```

### From Source

```bash
git clone https://gitlab.com/reisub0/nzb
cargo install --path nzb
```


## License

Nzb is licensed under the [MIT License](https://choosealicense.com/licenses/mit/).
