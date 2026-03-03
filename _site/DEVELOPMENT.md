# Development Setup Guide

To preview this site locally, you need to install Jekyll. Since the system Ruby version on macOS is old, we recommend using Homebrew to install a newer Ruby version.

## 1. Install Homebrew

Open your terminal and paste this command:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Follow the prompts (you may need to enter your password). After installation, follow the "Next steps" instructions in the terminal output to add brew to your PATH.

## 2. Install Ruby

Use Homebrew to install the latest Ruby:

```bash
brew install ruby
```

After installation, add the new Ruby to your PATH so your terminal uses it instead of the system version. Add this to your `~/.zshrc` file:

```bash
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

*Note: If you are on an Intel Mac, the path might be `/usr/local/opt/ruby/bin` instead.*

## 3. Install Jekyll

Now install Jekyll and Bundler:

```bash
gem install jekyll bundler
```

## 4. Run the Site

Navigate to the project directory and run:

```bash
bundle install
bundle exec jekyll serve
```

The site will be available at `http://localhost:4000/recipes/`.
