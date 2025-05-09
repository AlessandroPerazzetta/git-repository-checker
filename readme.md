# Git Repository Update Checker

A bash script that recursively searches directories for git repositories, checks for available updates, and provides notifications about their status.

## Features

- 🔍 **Recursive Search**: Automatically finds all git repositories within a specified directory
- 🔄 **Real-time Status**: Checks each repository for updates, pushed/unpushed changes, and diverged branches
- 📋 **Commit Preview**: Shows a preview of new commits that would be pulled
- 🚨 **Multiple Notification Methods**: Choose between terminal output, desktop notifications, or both
- 🎨 **Color-coded Output**: Easy-to-read terminal output with color-coding for different statuses
- 📊 **Summary Statistics**: Provides a summary of all repositories checked

## Installation

1. Download the script:
   ```bash
   curl -O https://raw.githubusercontent.com/yourusername/git-repo-checker/main/git-repo-checker
   ```

2. Make it executable:
   ```bash
   chmod +x git-repo-checker
   ```

3. Optional: Move it to a directory in your PATH for easy access:
   ```bash
   sudo mv git-repo-checker /usr/local/bin/git-repo-checker
   ```

## Usage

Basic usage:
```bash
./git-repo-checker [search_directory] [notification_method]
```

### Parameters

- `search_directory` (optional): Directory to search for git repositories
  - Defaults to current directory if not specified
  
- `notification_method` (optional): How to notify about updates
  - Options: `terminal`, `notify-send`, `both`
  - Defaults to `terminal` if not specified

### Examples

Check all repositories in the current directory:
```bash
./git-repo-checker
```

Check all repositories in your home directory:
```bash
./git-repo-checker ~/
```

Check repositories in a specific project folder with desktop notifications:
```bash
./git-repo-checker ~/Projects notify-send
```

## Notifications

The script provides different types of notifications:

- **[CURRENT]**: Repository is up-to-date
- **[UPDATES]**: Repository has changes to pull or push
- **[ERROR]**: There was an error checking the repository

For desktop notifications, only repositories with updates or errors will trigger notifications to avoid spam.

## Requirements

- Git
- For desktop notifications: `notify-send` (part of `libnotify-bin` package on Debian/Ubuntu)

## Integration Ideas

- Add to cron jobs for scheduled checks
- Include in your `.bashrc` or `.zshrc` to run when opening a terminal
- Create an alias for quicker access

## Troubleshooting

### No repositories found
Make sure you're specifying a directory that contains git repositories.

### Desktop notifications not working
Ensure you have `notify-send` installed:
```bash
sudo apt install libnotify-bin  # For Debian/Ubuntu
```

### Permission denied errors
Make sure you have read access to all directories being searched.

## License

This script is released under the MIT License. See the LICENSE file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.