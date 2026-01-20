# ASCII Art Generator - CLI Usage Plan

## Core CLI Patterns

### 1. Direct Text Input (Primary)
```bash
ascii-art "Hello World"
ascii-art Hello World  # without quotes for single words
```

### 2. Interactive Mode
```bash
ascii-art
# Prompts: "Enter text to convert:"
```

### 3. Pipe from stdin
```bash
echo "DevOps" | ascii-art
cat banner.txt | ascii-art
```

## Feature Flags

### Gradient Styles
```bash
ascii-art "Code" -g rainbow
ascii-art "Code" -g sunset
ascii-art "Code" -g ocean
ascii-art "Code" -g matrix  # green like Matrix
ascii-art "Code" -g fire
ascii-art "Code" -g cotton-candy
```

### Custom Color Gradients
```bash
# Two colors - gradient between them
ascii-art "Text" --color "#FF6B6B,#4ECDC4"

# Single color - white to color (default)
ascii-art "Text" --color "#FF6B6B"

# Single color - color to dark
ascii-art "Text" --color "#FF6B6B" --dark
```

### Font Styles
```bash
ascii-art "Text" -f block      # solid blocks (default)
ascii-art "Text" -f standard   # figlet standard
ascii-art "Text" -f banner
ascii-art "Text" -f big
ascii-art "Text" -f slant
```

### Width Control
```bash
ascii-art "Text" -w 80   # max width 80 chars
ascii-art "Text" --width 120
```

### Output Options
```bash
ascii-art "Text" -o banner.txt        # save to file
ascii-art "Text" -o banner.txt --no-color  # plain ASCII without colors
ascii-art "Text" -c                   # copy to clipboard
```

### Preview Mode
```bash
ascii-art "Text" --preview-gradients  # shows all gradient options
ascii-art "Text" --preview-fonts      # shows all font options
```

## Advanced Usage

### Multi-line Support
```bash
ascii-art "Line 1" "Line 2"  # separate lines
ascii-art -m "Multi\nLine\nText"  # newline support
```

### Random Gradient
```bash
ascii-art "Surprise" --random
ascii-art "Surprise" -r
```

### Background Color
```bash
ascii-art "Text" --bg dark    # dark background optimization
ascii-art "Text" --bg light   # light background optimization
```

## Examples

```bash
# Project banner
ascii-art "MyProject" -g ocean -f block > banner.txt

# Git commit banner
git log --oneline | head -1 | ascii-art -g matrix

# Quick logo
ascii-art "LOGO" -g rainbow -c  # copies to clipboard

# Documentation header
ascii-art "API Docs" -g sunset --width 100 >> README.md
```

## NPX Support
```bash
npx ascii-art-generator "Quick Test"
```

## Global Install
```bash
npm install -g ascii-art-generator
ascii-art "Anywhere!"
```

## Implementation Priority

1. Basic direct input with default gradient
2. Gradient options (-g flag)
3. Custom color gradients (--color flag with hex codes)
4. Font options (-f flag)
5. Output to file (-o flag)
6. Interactive mode
7. Stdin pipe support
8. Copy to clipboard
9. Preview modes
10. Width control
11. Advanced features (multi-line, random, bg options)
