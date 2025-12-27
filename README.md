# homebrew-tap

A Homebrew tap for custom formulae and casks.

## Installation

To tap this repository:

```bash
brew tap jeff-french/tap
```

## Usage

### Installing Formulae

Once the tap is added, you can install any formula from this tap:

```bash
brew install jeff-french/tap/<formula-name>
```

Or after tapping:

```bash
brew install <formula-name>
```

### Installing Casks

To install a cask from this tap:

```bash
brew install --cask jeff-french/tap/<cask-name>
```

## Structure

- `Formula/` - Contains Homebrew formulae (command-line tools, libraries, etc.)
- `Casks/` - Contains Homebrew casks (macOS applications)

## Adding Formulae

To add a new formula, create a Ruby file in the `Formula/` directory. Example:

```ruby
class MyTool < Formula
  desc "Description of my tool"
  homepage "https://github.com/jeff-french/my-tool"
  url "https://github.com/jeff-french/my-tool/archive/v1.0.0.tar.gz"
  sha256 "sha256-hash-here"
  license "MIT"

  def install
    bin.install "my-tool"
  end

  test do
    system "#{bin}/my-tool", "--version"
  end
end
```

## Adding Casks

To add a new cask, create a Ruby file in the `Casks/` directory. Example:

```ruby
cask "my-app" do
  version "1.0.0"
  sha256 "sha256-hash-here"

  url "https://github.com/jeff-french/my-app/releases/download/v#{version}/MyApp.dmg"
  name "My App"
  desc "Description of my app"
  homepage "https://github.com/jeff-french/my-app"

  app "MyApp.app"
end
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.