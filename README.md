# Scoop Bucket for folder2md4llms

[![CI](https://github.com/HenriquesLab/scoop-folder2md4llms/actions/workflows/ci.yml/badge.svg)](https://github.com/HenriquesLab/scoop-folder2md4llms/actions/workflows/ci.yml)
[![Excavator](https://github.com/HenriquesLab/scoop-folder2md4llms/actions/workflows/excavator.yml/badge.svg)](https://github.com/HenriquesLab/scoop-folder2md4llms/actions/workflows/excavator.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A [Scoop](https://scoop.sh/) bucket for easy Windows installation of [folder2md4llms](https://github.com/henriqueslab/folder2md4llms) - a powerful tool that converts repository contents into LLM-friendly Markdown files.

## 🚀 Quick Start

### Prerequisites

- **Windows 10/11** (or Windows Server 2016+)
- **Python 3.11+** installed and accessible via `python` command
- **PowerShell 5.1+** (usually pre-installed)

### Installation

1. **Install Scoop** (if not already installed):
   ```powershell
   Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
   Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
   ```

2. **Add this bucket**:
   ```powershell
   scoop bucket add folder2md4llms https://github.com/HenriquesLab/scoop-folder2md4llms
   ```

3. **Install folder2md4llms**:
   ```powershell
   scoop install folder2md4llms
   ```

### Usage

After installation, you can use `folder2md4llms` directly from any command prompt:

```powershell
# Process current directory
folder2md . --output output.md

# Process specific directory with token limit
folder2md C:\MyProject --limit 80000t

# Copy output to clipboard
folder2md C:\MyProject --clipboard

# Generate ignore file template
folder2md --init-ignore

# Show help
folder2md --help
```

## 📦 What's Included

This Scoop bucket provides:

- **folder2md4llms** - The main package with all dependencies
- **Automatic updates** - Excavator workflow keeps the package current
- **Comprehensive testing** - CI workflows ensure reliability
- **Issue automation** - Intelligent issue handling and support

## 🔧 Advanced Usage

### Configuration

Create a `folder2md.yaml` file in your project root:

```yaml
limit: 80000t
condense: true
ignore_patterns:
  - "*.log"
  - "temp/*"
output_format: "markdown"
```

### Python Module Access

You can also access the tool as a Python module:

```powershell
# Direct module access
python -m folder2md4llms.cli --help

# Or use the installed executable
folder2md --help
```

### Updating

```powershell
# Update to latest version
scoop update folder2md4llms

# Update all packages
scoop update

# Check for updates
scoop status
```

## 🤖 Automation Features

### Automatic Updates (Excavator)

This bucket includes an automated update system that:

- ✅ Runs every 4 hours
- ✅ Checks PyPI for new versions
- ✅ Updates manifests automatically
- ✅ Creates pull requests for review
- ✅ Tests updated packages

### Continuous Integration

Every change is automatically tested on:

- ✅ Windows 2019, 2022, and latest
- ✅ Python 3.11 and 3.12
- ✅ Installation and uninstallation
- ✅ Basic functionality testing
- ✅ Manifest validation

### Issue Management

The bucket includes intelligent issue handling:

- ✅ Automatic labeling and triage
- ✅ Installation troubleshooting
- ✅ Version checking and guidance
- ✅ Common problem resolution

## 📋 Requirements

### System Requirements

- **Operating System**: Windows 10/11, Windows Server 2016+
- **Python**: 3.11 or higher
- **Memory**: 512MB RAM minimum
- **Storage**: 100MB free space

### Python Dependencies

The following packages are automatically installed:

- `click>=8.0.0` - Command-line interface
- `httpx>=0.24.0` - HTTP client
- `markdown>=3.4.0` - Markdown processing
- `nbconvert>=7.0.0` - Jupyter notebook conversion
- `openpyxl>=3.1.0` - Excel file support
- `pillow>=9.0.0` - Image processing
- `psutil>=5.9.0` - System monitoring
- `pygments>=2.10.0` - Syntax highlighting
- `pypdf>=4.0.0` - PDF processing
- `pyperclip>=1.9.0` - Clipboard operations
- `python-docx>=0.8.11` - Word document support
- `python-magic-bin` - File type detection (Windows)
- `python-pptx>=0.6.21` - PowerPoint support
- `pyyaml>=6.0` - YAML configuration
- `rich>=13.0.0` - Terminal formatting
- `striprtf>=0.0.26` - RTF processing
- `tqdm>=4.64.0` - Progress bars

## 🔄 Alternative Installation Methods

### Direct pip Installation

If you prefer to install without Scoop:

```powershell
python -m pip install folder2md4llms
```

### Development Installation

For development or testing:

```powershell
# Clone the repository
git clone https://github.com/henriqueslab/folder2md4llms.git
cd folder2md4llms

# Install in development mode
python -m pip install -e .
```

## 🛠️ Troubleshooting

### Common Issues

**Command not found:**
```powershell
# Refresh Scoop shims
scoop reset folder2md4llms

# Check if Python is accessible
python --version
```

**Permission errors:**
```powershell
# Run as administrator or check execution policy
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

**Installation fails:**
```powershell
# Check Python and pip versions
python --version
python -m pip --version

# Install directly if needed
python -m pip install folder2md4llms
```

**Package not found:**
```powershell
# Refresh bucket
scoop bucket rm folder2md4llms
scoop bucket add folder2md4llms https://github.com/HenriquesLab/scoop-folder2md4llms
```

### Getting Help

- 📚 [Main Documentation](https://github.com/henriqueslab/folder2md4llms)
- 🐛 [Report Issues](https://github.com/HenriquesLab/scoop-folder2md4llms/issues)
- 💬 [Discussion Forum](https://github.com/henriqueslab/folder2md4llms/discussions)

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

### Reporting Issues

1. Check existing [issues](https://github.com/HenriquesLab/scoop-folder2md4llms/issues)
2. Create a new issue with:
   - Windows version
   - Python version
   - Scoop version
   - Full error message
   - Steps to reproduce

### Submitting Changes

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

### Adding New Packages

To add new packages to this bucket:

1. Create a manifest in the `bucket/` directory
2. Follow the [Scoop manifest format](https://github.com/ScoopInstaller/Scoop/wiki/App-Manifests)
3. Test the manifest locally
4. Submit a pull request

## 📊 Statistics

- **Total Packages**: 1
- **Supported Platforms**: Windows 10/11, Server 2016+
- **Python Versions**: 3.11, 3.12
- **Update Frequency**: Every 4 hours
- **Test Coverage**: 100% (installation, functionality, uninstallation)

## 🔄 Maintenance

This bucket is actively maintained with:

- **Automated updates** via Excavator
- **Continuous testing** on multiple Windows versions
- **Issue tracking** and resolution
- **Security monitoring**
- **Performance optimization**

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Scoop](https://scoop.sh/) - The Windows package manager
- [folder2md4llms](https://github.com/henriqueslab/folder2md4llms) - The main tool
- [ScoopInstaller](https://github.com/ScoopInstaller) - Official Scoop tools and actions
- All contributors and users of this bucket

---

**Made with ❤️ for the Windows development community**

For questions or support, please [open an issue](https://github.com/HenriquesLab/scoop-folder2md4llms/issues) or visit the [main project repository](https://github.com/henriqueslab/folder2md4llms).