# GitHub Copilot Instructions for PowerToys

This file provides guidance for GitHub Copilot when generating code for the PowerToys repository.

## Project Overview

PowerToys is a set of utilities for power users to tune and streamline their Windows experience for greater productivity. It consists of multiple modules written in a mix of C++, C#, and other technologies.

## Architecture

- **Modules**: Each PowerToys utility is implemented as a module
- **Runner**: Central executable that loads and manages modules
- **Settings**: Common settings UI and libraries for module configuration

## Coding Standards

### General

- Follow the established patterns in the codebase
- Be mindful of performance impact, as PowerToys runs in the background
- Ensure proper error handling and cleanup
- Add appropriate logging for debugging and telemetry
- Write unit tests for new functionality

### C# Code Style

- Use C# 10+ features where appropriate
- Follow the .editorconfig settings for C# code style
- Use Pascal case for classes, methods, and properties
- Use camel case for local variables and parameters
- Prefix private fields with underscore (`_fieldName`)
- Include XML documentation for public APIs
- File header template: 
  ```csharp
  // Copyright (c) Microsoft Corporation
  // The Microsoft Corporation licenses this file to you under the MIT license.
  // See the LICENSE file in the project root for more information.
  ```

### C++ Code Style

- Use modern C++ features (C++17)
- Use RAII principles for resource management
- Use smart pointers instead of raw pointers when managing ownership
- Avoid exceptions in favor of error codes/returns where possible
- Prefer namespaces to prevent naming conflicts
- Use `snake_case` for variables and functions
- Use `PascalCase` for class names
- Use `m_` prefix for member variables
- Use `g_` prefix for global variables

### User Interface

- Follow Windows 11/10 design language
- Design for accessibility (keyboard navigation, screen readers)
- Support dark/light theme
- Support localization/internationalization
- Support high DPI displays

## Module Development

When developing a new module or enhancing an existing one:

1. Follow the existing module structure
2. Implement the required module interface
3. Handle settings persistence appropriately
4. Add localization support
5. Add telemetry for usage tracking
6. Implement appropriate unit tests

## Testing

- Write unit tests for core functionality
- Follow existing test patterns in the codebase
- Ensure modules can be enabled/disabled without issues
- Test on different Windows versions (10/11)
- Test with different display configurations

## Pull Request Process

1. Ensure code compiles without warnings
2. Run unit tests
3. Verify code style compliance
4. Document changes properly
5. Ensure changes follow the "Do no harm" principle (avoid breaking existing functionality)

## Resources

- Check the `doc/devdocs` folder for module-specific documentation
- Refer to `CONTRIBUTING.md` for contribution guidelines
- Use the issue tracker for feature discussions before implementing significant changes