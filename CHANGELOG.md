# Changelog

All notable changes to this project will be documented in this file.

## [0.0.4] - 2024-01-XX

### Security Improvements
- **REMOVED** `serialize` and `unserialize` filters due to security vulnerability (pickle arbitrary code execution)
- **ENHANCED** SQL injection protection with more comprehensive pattern detection
- **IMPROVED** `addslashes` filter to properly escape single quotes, double quotes, and backslashes

### Bug Fixes
- **FIXED** Critical class variable sharing bug - each InputRules instance now has independent variables
- **FIXED** `empty()` function logic to properly handle all data types (lists, dicts, booleans, etc.)
- **FIXED** `getValue()` error handling - now returns `None` instead of raising KeyError
- **FIXED** `urlencode` filter double encoding issue
- **IMPROVED** validation schema error handling for nested structures
- **FIXED** `map_options()` structure overwrite issue

### Enhancements
- Better error handling throughout the codebase
- Comprehensive test suite with 100+ test cases
- Improved documentation with security notes
- Enhanced type checking and validation

### Breaking Changes
- `serialize` and `unserialize` filters are no longer available
- `empty()` function behavior changed for consistency across data types

## [0.0.3] - Previous Version

### Features
- Basic validation rules and filters
- Nested data structure support
- SQL sanitization
- Multiple filter types

## [0.0.2] - Initial Releases

### Features
- Core InputRules class
- Basic validation and filtering
- JSON tools utilities