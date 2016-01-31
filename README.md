# Mac Development Ansible Playbook

This playbook installs and configures most of the software I use on my Mac for web and software development. Some things in OS X are difficult to automate (notably, the Mac App Store and certain tools from Apple), so I still have some manual installation steps, but at least it's all documented here.

This is a work in progress, and is mostly a means for me to document my current Mac's setup. I'll be adding settings and packages to this set of playbooks over time.

## Installation

  1. Run the bootstrap script `\curl -sSL https://raw.githubusercontent.com/bobbrez/mac-playbook/master/script/bootstrap | bash`
  2. Clone this repository to your local drive.
  3. Run the command `$ ansible-galaxy install -r requirements.txt` inside this directory to install required Ansible roles.
  4. Run `ansible-playbook main.yml -i inventory --ask-sudo-pass` from the same directory as this README file.

My [dotfiles](https://github.com/bobbrez/dotfiles) are also installed into the current user's home directory, including the `.osx` dotfile for configuring many aspects of Mac OS X for better performance and ease of use.

Finally, there are a few other preferences and settings added on for various apps and services.

## Future additions

### Things that still need to be done manually

It's my hope that I can get the rest of these things wrapped up into Ansible playbooks soon, but for now, these steps need to be completed manually (assuming you already have Xcode and Ansible installed, and have run this playbook).

  
  1. Configure Bash-It aliases, plugins and completions (manually link)
  2. Install all the Mac App Store Apps (see below).
  3. Enable Magnification in the Dock control panel
  4. Setup vundle
    1. `$ git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim`
    2. Open vim and run `PluginInstall`
  3. Remap Caps Lock to Control Key
  4. Configure extra Mail and/or Calendar accounts (e.g. Google, Exchange, etc.).

### Apps only available via the App Store

I also use the following apps at least once or twice per week, but unfortunately, as the Mac App Store is not able to be controlled via CLI, or any other way I can find (so far), I have to manually install all of these apps from within the App Store application.

  - 1Password
  - Pages
  - Keynote
  - Numbers

## Testing the Playbook

Many people have asked me if I often wipe my entire workstation and start from scratch just to test changes to the playbook. Nope! Instead, I posted instructions for how I build a [Mac OS X VirtualBox VM](https://github.com/geerlingguy/mac-osx-virtualbox-vm), on which I can continually run and re-run this playbook to test changes and make sure things work correctly.

## Author

* [Bob Breznak](http://github.com/bobbrez)
* [Jeff Geerling](http://jeffgeerling.com/), 2014 (originally inspired by [MWGriffin/ansible-playbooks](https://github.com/MWGriffin/ansible-playbooks)).
