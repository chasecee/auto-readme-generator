# Automatic README Generator

⚠️ **WARNING: This README is automatically generated and may be overwritten.** ⚠️

This tool automatically generates a README.md file for your project using the Claude API. It can run as a pre-commit hook or be executed manually, ensuring your README is always up-to-date with your project structure.

## Features

- Automatically generates a README.md based on your project's file structure
- Uses Claude API for intelligent content generation
- Can run as a pre-commit hook for seamless integration into your workflow
- Allows manual execution with custom output file option
- Securely manages API keys using environment variables

## Prerequisites

- Python 3.x
- Git
- An Anthropic API key

## Installation

1. Clone this repository or copy the necessary files to your project.

2. Install the required Python package:

   ```
   pip install anthropic
   ```

3. Create a `.env` file in your project root with your Anthropic API key:

   ```
   ANTHROPIC_API_KEY=your_api_key_here
   ```

4. Add `.env` to your `.gitignore` file to prevent it from being version controlled:

   ```
   echo ".env" >> .gitignore
   ```

5. (Optional) Set up the pre-commit hook by running the following commands in your terminal:

   ```bash
   cat > .git/hooks/pre-commit << EOL
   #!/bin/sh

   # Run the Python script to generate README.md
   python generate_readme.py

   # Add the updated README.md to the commit
   git add README.md
   EOL

   chmod +x .git/hooks/pre-commit
   ```

## Usage

### As a Pre-commit Hook

If you've set up the pre-commit hook, the tool will automatically run every time you make a commit. It will:

1. Analyze your project's file structure
2. Generate a new README.md or update the existing one
3. Add the README.md to your commit

You don't need to do anything extra - just commit as you normally would, and your README will be kept up-to-date automatically.

### Manual Execution

You can also run the script manually:
