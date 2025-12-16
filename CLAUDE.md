# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a machine learning project for classifying American Sign Language digits (0-9) using the Sign Language Digits Dataset from Turkey Ankara Ayrancı Anadolu High School.

### Dataset Structure

- **Location**: `Sign-Language-Digits-Dataset/Dataset/`
- **Organization**: Images are organized in subdirectories by digit (0-9)
  - Pattern: `Sign-Language-Digits-Dataset/Dataset/N/IMG_*.JPG` where N is the digit (0-9)
- **Image specs**: 100x100 pixels, RGB color space
- **Dataset size**: 218 participants × 10 samples each = 2,180 images
- **Example images**: `Sign-Language-Digits-Dataset/Examples/example_N.JPG`

### Python Environment

- **Python version**: 3.12.3
- **Virtual environment**: `venv/` (already created)
- **Activation**: `source venv/bin/activate`

## Development Commands

```bash
# Activate virtual environment
source venv/bin/activate

# Install dependencies (when requirements.txt exists)
pip install -r requirements.txt

# Deactivate virtual environment
deactivate
```
