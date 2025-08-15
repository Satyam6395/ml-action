# Git Graph Tool

A Python tool to visualize git commit history as a beautiful graph using matplotlib.

## Features

- Visualize git commit history as a graph
- Color-coded branches
- Show commit information (hash, author, date, message)
- Save graphs as images
- Repository statistics
- Command-line interface with various options

## Installation

1. Install the required dependencies:
```bash
pip install -r requirements.txt
```

Or install manually:
```bash
pip install gitpython matplotlib numpy
```

## Usage

### Basic Usage

Run the tool in a git repository:
```bash
python git_graph.py
```

### Command Line Options

```bash
python git_graph.py [OPTIONS]
```

Options:
- `--repo, -r`: Path to git repository (default: current directory)
- `--max-commits, -m`: Maximum number of commits to display (default: 50)
- `--branch, -b`: Specific branch to visualize
- `--output, -o`: Output file to save the graph (e.g., git_graph.png)
- `--no-author`: Hide author information
- `--no-date`: Hide date information
- `--stats, -s`: Show repository statistics

### Examples

1. **Basic graph visualization:**
```bash
python git_graph.py
```

2. **Show only last 20 commits:**
```bash
python git_graph.py --max-commits 20
```

3. **Visualize a specific branch:**
```bash
python git_graph.py --branch main
```

4. **Save graph to file:**
```bash
python git_graph.py --output git_history.png
```

5. **Show repository statistics:**
```bash
python git_graph.py --stats
```

6. **Minimal view (no author/date):**
```bash
python git_graph.py --no-author --no-date
```

7. **Analyze a different repository:**
```bash
python git_graph.py --repo /path/to/other/repo
```

## Programmatic Usage

You can also use the GitGraph class in your own Python code:

```python
from git_graph import GitGraph

# Create a git graph instance
git_graph = GitGraph("path/to/repo")

# Get commit history
commits = git_graph.get_commit_history(max_commits=30)

# Show statistics
git_graph.print_commit_stats()

# Create and display graph
git_graph.create_graph(
    output_file="my_graph.png",
    show_author=True,
    show_date=True
)
```

## Output

The tool generates a visual graph showing:
- Commit circles (color-coded by branch)
- Commit information (hash, author, date)
- Commit messages
- Branch connections
- Legend showing branch colors

## Requirements

- Python 3.6+
- Git repository
- Required Python packages (see requirements.txt)

## Troubleshooting

1. **"gitpython is required" error**: Install gitpython with `pip install gitpython`
2. **"Not a valid git repository" error**: Make sure you're in a git repository or specify the correct path
3. **No commits found**: The repository might be empty or the specified branch doesn't exist

## License

This tool is provided as-is for educational and development purposes.


