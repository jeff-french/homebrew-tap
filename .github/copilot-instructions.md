# Copilot Instructions for homebrew-tap

This is a Homebrew tap repository for custom formulas maintained by Jeff French.

## Repository Structure

- Formulas should be placed in the `Formula/` directory (standard for Homebrew taps)
- Each formula is a Ruby class that inherits from `Formula`
- Follow Homebrew's naming conventions: formula files use lowercase with hyphens

## Development Guidelines

### Formula Development

- Use Homebrew's DSL for defining formulas
- Include proper `desc` and `homepage` in all formulas
- Specify `license` information when available
- Use `url` to point to source archives with required SHA256 checksums
- Define `depends_on` for any dependencies
- Implement `install` method with installation logic
- Add `test do` block for basic functionality tests

### Ruby Style

- Follow Homebrew's Ruby style guide
- Use 2 spaces for indentation
- Keep lines under 100 characters when possible
- Use double quotes for strings

### Testing

- Always include a `test do` block in formulas
- Test blocks should verify basic functionality
- Use `system` or `shell_output` to test executables
- Check that installed files exist where expected

### Version Updates

- Update both `url` and `sha256` when bumping versions
- Test the new version before committing
- Increment `revision` when rebuilding the same version with changes (e.g., build fixes, new patches)

### Documentation

- Keep README.md up to date with available formulas
- Document any non-standard installation procedures
- Include usage examples where helpful

## Best Practices

- Test formulas locally with `brew install --build-from-source ./formula-name.rb`
- Use `brew audit --strict formula-name` to check for issues
- Run `brew style formula-name` to verify style compliance
- Validate formulas with `brew test formula-name` after installation
