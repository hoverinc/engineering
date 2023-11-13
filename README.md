# HOVER Engineering

https://github.com/hoverinc/engineering

# Development setup

Copy/paste this into `Terminal.app` on your Mac

```sh
curl https://raw.githubusercontent.com/hoverinc/engineering/main/script/bootstrap --output ~/Downloads/bootstrap
sh ~/Downloads/bootstrap
```

You'll be asked for your:

- **Bash / Z shell preference** : If you don't know, just press `return` to use the default.
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
- Installs everything from this repo's [`Brewfile`](https://github.com/hoverinc/engineering/blob/main/Brewfile)
- Installs Ruby
- Installs NVM, the latest Node, and the latest NPM
- Installs Postgres


## AWS Credentials
Follow instructions on this page [Installing gimme-aws-credentials](https://hoverinc.atlassian.net/wiki/spaces/EN/pages/2790850693/Installing+gimme-aws-credentials) to set up your aws credentials

## Bundler Setup

We use [GitHub Package Registry](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-rubygems-registry) for private repo RubyGems which requires a personal access token.

1. Go to [Settings › Developer Settings › Personal access tokens](https://github.com/settings/tokens)
2. Click on **Generate new token**
3. Set the **Note** field to `HOVER packages`
4. Set **Expiration** to `90 days`
5. Check the **repo** and **read:packages** scopes
6. Click on **Generate token**
7. Copy the token!
8. Save it to you _1Password_ vault
8. On the resulting screen open the **Enable SSO** drop-down and click the **Authorize** button
9. Add the following line to your `~/.bash_profile` / `~/.zshrc`:
  ```
  # "HOVER packages" github token
  export BUNDLE_RUBYGEMS__PKG__GITHUB__COM=<PASTE YOUR TOKEN HERE>
  ```
10. You should now be able run `bundle install` in a new `Terminal.app` tab/window

* NOTE: If you encounter an error that says the following while running `bundle install`:

  ```
  Bad username or password for https://<TOKEN>@rubygems.pkg.github.com/hoverinc/.
  Please double-check your credentials and correct them.
  ```

* Run the following command:
  ```
  bundle config https://rubygems.pkg.github.com/hoverinc <GITHUB-USERNAME>:<TOKEN>
  ```

11. **Important:** Add a recurring calendar event to remind you every 3 months to replace your token so you're not left scratching your head when your development environment breaks

# Contents of the Repo

- [Recommended Reading](https://github.com/hoverinc/engineering/blob/main/recommended-reading)