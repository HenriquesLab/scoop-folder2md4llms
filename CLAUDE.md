# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Scoop bucket repository** for Windows installation of [folder2md4llms](https://github.com/henriqueslab/folder2md4llms) - a Python CLI tool that converts repository contents into LLM-friendly Markdown files.

## Repository Structure

This repository contains:
- `bucket/folder2md4llms.json` - Scoop package manifest
- `.github/workflows/` - CI/CD automation (test-manifest.yml, update-manifest.yml)
- `README.md` - Installation and usage documentation

## Common Commands

### Testing
```bash
# Run CI tests locally (requires Windows + PowerShell)
# The CI tests cover:
# - Manifest JSON validation
# - Scoop installation/uninstallation
# - Package functionality testing
# - Version checking against PyPI
```

### Manifest Management
```bash
# Update version in manifest (automated via Excavator)
# Edit bucket/folder2md4llms.json to modify package configuration
```

### CI/CD
- **Update Manifest**: Runs every 4 hours to check PyPI for new versions and auto-update manifest
- **Test Manifest**: Tests on Windows 2022/latest with Python 3.11/3.12/3.13

## Key Architecture

### Scoop Integration
- Package installs via `python -m pip install folder2md4llms`
- Creates shim: `folder2md` command mapped to `python -m folder2md4llms.cli`
- Supports Windows 10/11 with Python 3.11+ requirement

### Automated Updates
- **Excavator workflow**: Monitors PyPI, creates PRs for version updates
- **Checkver**: Uses PyPI JSON API to detect new versions
- **Auto-update**: Handles version bumping automatically

### Testing Strategy
- Matrix testing across Windows versions and Python versions
- Full installation/functionality/uninstallation cycle
- Performance timing and caching optimizations
- Real-world usage simulation with test files

## Dependencies

### Runtime Requirements
- Windows 10/11 or Windows Server 2016+
- Python 3.11+ (managed by Scoop as dependency)
- PowerShell 5.1+ (built-in on Windows)

### Build/CI Dependencies
- Scoop package manager
- GitHub Actions (Windows runners)
- PowerShell for automation scripts

## Version Management

- **Source of Truth**: PyPI version of `folder2md4llms`
- **Update Process**: Update Manifest workflow monitors PyPI → Creates PR → Tests → Merges
- **Manifest**: `bucket/folder2md4llms.json` contains current version
- **Checkver URL**: `https://pypi.org/pypi/folder2md4llms/json`

## CI/CD Pipeline

### Workflows
1. **Test Manifest** (`test-manifest.yml`): Validates manifest, tests installation/functionality
2. **Update Manifest** (`update-manifest.yml`): Automated version updates every 4 hours

### Test Coverage
- JSON manifest validation
- Package installation via Scoop
- CLI functionality testing (`folder2md --help`, `folder2md --version`)
- File processing verification
- Clean uninstallation
- Version synchronization with PyPI

## Package Configuration

The Scoop manifest (`bucket/folder2md4llms.json`) defines:
- Python pip installation command
- Binary shim mapping
- Dependencies (Python)
- Post-install messages
- Checkver/autoupdate configuration

## Distribution Strategy

This bucket serves as the **Windows distribution channel** for folder2md4llms:
- **Main repo**: Source code and PyPI publishing
- **This repo**: Windows-specific packaging and distribution
- **Automation**: Keeps Windows package in sync with PyPI releases