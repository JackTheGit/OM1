# Windows Setup Guide for OMI

*Contributor: pokerdirectory@hotmail.com*  
*This guide was created through systematic testing and verification on a fresh Windows installation.*

## Prerequisites

### 1. Install Git
- Download from: https://git-scm.com/download/win
- Use default settings during installation
- Verify: Open PowerShell and run \git --version\

### 2. Install Python (Critical: Version 3.10, 3.11, or 3.12 only)
- **DO NOT use Python 3.13 or newer** - they are incompatible with project dependencies
- Download Python 3.12.10 from: https://www.python.org/downloads/release/python-31210/
- **During installation:**
  - Check \"Add Python to PATH\"
  - Choose \"Customize installation\" if available
- Verify: Open new PowerShell and run \python --version\

### 3. Install Microsoft Visual C++ Build Tools
- Required for compiling some Python packages
- Download from: https://visualstudio.microsoft.com/visual-cpp-build-tools/
- During installation, check \"C++ build tools\" workload
- Ensure these components are included:
  - MSVC v143 - VS 2022 C++ x64/x86 build tools
  - Windows 11 SDK (or Windows 10 SDK)
- **Restart your computer** after installation

## Installation Steps

1. **Clone the Repository**
   \\\powershell
   git clone https://github.com/OpenMind/OM1.git
   cd OM1
   \\\

2. **Install Dependencies**
   \\\powershell
   # Use the correct Python version (3.10-3.12)
   py -3.12 -m pip install .
   
   # Or if Python 3.12 is your default:
   pip install .
   \\\

3. **Verify Installation**
   \\\powershell
   python -c \"import om1; print('OM1 installed successfully!')\"
   \\\

## Common Issues & Solutions

### ❌ \"Python 3.14 is not supported\"
**Solution:** Install Python 3.12.10 instead of newer versions.

### ❌ \"Microsoft Visual C++ 14.0 or greater is required\"
**Solution:** Install Microsoft Visual C++ Build Tools as described in prerequisites.

### ❌ \"pip is not recognized\"
**Solution:** 
- Reinstall Python and check \"Add Python to PATH\"
- Restart PowerShell after Python installation
- Use \python -m pip install .\ instead of \pip install .\

### ❌ \"No such file or directory: 'requirements.txt'\"
**Solution:** This project uses modern \pyproject.toml\ packaging. Use \pip install .\ instead.

### ❌ \"Git is not recognized\"
**Solution:** Install Git and ensure it's added to PATH.

## Project Structure Notes

- **No requirements.txt**: This project uses modern Python packaging with \pyproject.toml\
- **Installation command**: \pip install .\ (not \pip install -r requirements.txt\)
- **Python version**: Must be 3.10, 3.11, or 3.12

## Verification

After successful installation, you should see:
- All 80+ dependencies installed without errors
- OM1 package built and installed
- No compilation errors for C++ packages

## Troubleshooting

If you encounter any issues:

1. **Restart PowerShell** after installing prerequisites
2. **Verify Python version**: \python --version\
3. **Check C++ Build Tools** are installed
4. **Use absolute Python path**: \py -3.12 -m pip install .\

---

*This guide was created through systematic testing on a fresh Windows VM, identifying and solving each installation hurdle encountered by new users.*
