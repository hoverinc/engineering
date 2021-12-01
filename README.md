# Brightline Engineering Workstation Setup

This setup has been tested on M1 macbook pros. 

There may be bugs that arise from changes to homebrew or other packages or from using more recent operating systems or chip architectures. 

If you encounter problems, feel free to reach out to your onboarding buddy. If you both still have problems, contact [James Hart](https://brightlinehealth.slack.com/team/U011R7G5RRD) on Slack.

> **Note:** JAMF will slowly install applications on first boot that are required for working at Brightline. Things like Slack, Chrome, Office Suite, 1password, etc... They'll be installed as you work through these instructions.

# Development setup

Copy/paste this into `Terminal.app` on your Mac

```sh
curl https://raw.githubusercontent.com/hellobrightline/workstation/main/script/bootstrap | sh
```

> Note: You may need to run this command twice, due to an unknown bug right after closing the GitHub browser. If the script halts, re-run the command above to finish bootstrapping.

You'll be asked for your:

- **GitHub account email address** : This is used to create SSH keys for working with GitHub.
- **macOS password** : This is so that the script can use `sudo` to install some things.

## What it does

- Checks for or creates SSH keys for git/GitHub
- Helps you add an SSH key to your GitHub account
- Uses `strap` to [setup up your Mac](https://github.com/MikeMcQuaid/strap#features) for development:
  > - Disables Java in Safari (for better security)
  > - Enables the macOS screensaver password immediately (for better security)
  > - Enables the macOS application firewall (for better security)
  > - Adds a Found this computer? message to the login screen (for machine recovery)
  > - Enables full-disk encryption and saves the FileVault Recovery Key to the Desktop (for better security)
  > - Installs the Xcode Command Line Tools (for compilers and Unix tools)
  > - Agree to the Xcode license (for using compilers without prompts)
  > - Installs Homebrew (for installing command-line software)
  > - Installs Homebrew Bundle (for bundler-like Brewfile support)
  > - Installs Homebrew Services (for managing Homebrew-installed services)
  > - Installs Homebrew Cask (for installing graphical software)
  > - Installs the latest macOS software updates (for better security)
  > - Installs dotfiles from a user's https://github.com/username/dotfiles repository and runs script/setup to configure them; also runs script/strap-after-setup after setting up everything else
  > - Installs software from a user's Brewfile in their https://github.com/username/homebrew-brewfile repository or .Brewfile in their home directory.
- Installs everything from this repo's [`Brewfile`](https://github.com/hellobrightline/workstation/blob/main/Brewfile)
- Installs asdf, ruby, node, and yarn

## Next Steps

Hop over to https://github.com/hellobrightline/reef and follow the Setup instructions to configure our primary application, which is known as Reef.
