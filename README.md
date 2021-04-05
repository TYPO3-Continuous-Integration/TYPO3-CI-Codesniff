# TYPO3 PHP Codesniffer Github Action

This action sniffs your PHP code of your TYPO3 extension.

## Inputs

### `Files`

Files you want to lint. Default `Classes Configuration Tests`.

## Example usage

```
uses: typo3-continuous-integration/typo3-ci-php-codesniffer@v1
with: 
  files: 'Classes Configuration Tests'
```
