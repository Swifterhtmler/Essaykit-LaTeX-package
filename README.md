<!---This project uses LPPL 1.3c or later licence -->

# essaykit - LaTeX Package


A comprehensive LaTeX package for creating styled boxes, titles, quotes, and bibliographic references, designed for academic and scientific documents.


## Features

- **🎨 Styled Boxes** (`\rbox`) - Customizable colored boxes with titles
- **📝 Main Titles** (`\maintitle`) - Large, styled section titles  
- **💬 Quotes** (`\quoter`) - Formatted quotations with author attribution
- **📏 Rules** (`\rrule`) - Clean horizontal separators
- **📚 Sources** (`\sources`) - Bibliography with hyperlink support

## Quick Start

### Installation

```latex
\usepackage{essaykit}
```

### Basic Usage

```latex
% Styled box
\rbox[title=Important, color=softblue]{
    This is a highlighted box with a title.
}

% Main title
\maintitle[titlecolor=bluecolor]{Chapter 1: Introduction}

% Quote
\quoter{Science is organized knowledge.}{Herbert Spencer}

% Horizontal rule
\rrule

% Sources with hyperlinks
\sources{
    \href{https://example.com}{Online Article},
    Book Title by Author,
    Journal Reference
}
```

## Key Features

### Customizable Options

All commands support extensive customization through key-value options:

- **Colors**: `color`, `textcolor`, `titlecolor`, `authorcolor`
- **Sizing**: `width`, `titlesize`, `quotesize`  
- **Spacing**: `titlespacing`, `quotespacing`
- **Content**: `title` - Sets the box title text (any string)

### Predefined Colors

```latex
greycolor,marooncolor,bluecolor, lightgray, 
softgray, boxcolor, darkgray, softblue
```

### Box Examples

```latex
% Basic box
\rbox{Simple content}

% Titled box with custom styling
\rbox[title=Warning, color=red, textcolor=white]{
    Important safety information
}

% Custom width box
\rbox[width=0.7\textwidth, color=lightgray]{
    Narrower box for specific layouts
}
```

### Title Examples

```latex
% Large blue title
\maintitle[titlecolor=bluecolor, titlesize=\LARGE]{
    Research Methodology
}

% Custom spacing
\maintitle[titlespacing=1cm]{Section Overview}
```

### Quote Examples

```latex
% Styled quote
\quoter[authorcolor=darkgray, quotesize=\Large]{
    The important thing is not to stop questioning.
}{Albert Einstein}
```

### Image Commands

#### Logo
Insert images without captions:
```latex
% Basic usage
\logo{image.png}{5cm}

% Use with positioning
\placeleft{2cm}{\logo{company-logo.png}{3cm}}{8cm}
```

#### Figure
Insert captioned figures that can be referenced:
```latex
% Basic figure
\fig{chart.png}{Monthly sales data}{0.7\textwidth}

% Smaller figure
\fig{diagram.png}{System architecture}{0.5\textwidth}
```

### Positioning Commands

Position content at absolute locations on the page without affecting text flow:

#### Place Left
```latex
% Place content from left margin
\placeleft{distance from left}{content}{content width}

% Example
\placeleft{3cm}{\logo{sidebar.png}{4cm}}{10cm}
```

#### Place Right
```latex
% Place content from right margin
\placeright{distance from right}{content}{content width}

% Example
\placeright{2cm}{\rbox[color=softblue]{Note}}{8cm}
```

**Note**: Content placed with these commands floats above the text and doesn't affect document flow, similar to absolute positioning in CSS.


## File Structure

```
essaykit/
├── essaykit.dtx          # Documented source code
├── essaykit.ins          # Installation script
├── essaykit.pdf          # Package documentation
├── README.md           # This file

```

## Building from Source

```bash
# Generate package file
latex essaykit.ins

# Build documentation  
pdflatex essaykit.dtx
makeindex -s gind.ist essaykit.idx
pdflatex essaykit.dtx
pdflatex essaykit.dtx
make all
```
<!-- 
## Examples

See the `examples/` directory for complete working examples:

- `basic-example.tex` - Simple usage demonstration
- `advanced-example.tex` - Advanced styling options
- `complete-document.tex` - Full academic document example -->

## Dependencies

The package automatically loads:
- `tcolorbox` - Colored boxes
- `hyperref` - PDF hyperlinks
- `xkeyval` - Key-value options
- `xcolor` - Color support
- `graphicx` - Image support
- `textpos` - Absolute positioning
- And several others for full functionality

## Compatibility

- **LaTeX Version**: Requires LaTeX2e (2005/12/01 or later)
- **Engines**: pdfLaTeX, XeLaTeX, LuaLaTeX
- **Package Conflicts**: Handles `hyperref` conflicts automatically

## Common Use Cases

### Academic Papers
```latex
\maintitle{Abstract}
\rbox[color=lightgray]{
    This paper presents a novel approach to...
}
```

### Laboratory Reports
```latex
\rbox[title=Objective, color=softblue]{
    To investigate the relationship between...
}
```

### Presentations
```latex
\quoter{Imagination is more important than knowledge.}{Einstein}
```

## Troubleshooting

### Package Conflicts
Load conflicting packages before essaykit:
```latex
\usepackage{animate}
\usepackage{multimedia}
\usepackage{essaykit}  % Load last
```

### Color Issues
Use predefined colors or define custom ones:
```latex
\definecolor{mycolor}{RGB}{100,150,200}
\rbox[color=mycolor]{Content}
```

## License

This package is released under the LaTeX Project Public License v1.3c or later.
See [LPPL 1.3c or later](https://www.latex-project.org/lppl.txt) for details.

## Support

- **Documentation**: `essaykit.pdf`
- **Issues**: Report on GitHub
- **Contact**: RKTuotanto@icloud.com

## Contributing

Contributions are welcome! Please:
1. Follow existing code style
2. Add tests/examples for new features
3. Update documentation
4. Submit via standard channels
5. File issue on github first

## Version History

- **v1.0** (2025/08/15) - Initial release
  - Core functionality: boxes, titles, quotes, rules, sources
  - Comprehensive key-value option system
  - Hyperref integration
- **v2.0** (2026/01/02) - Second release
  - New logo box for university/school logos
  - New fig element for figures
  - New `\placeleft` and `placeright` commands for absolute positioning

---

*For complete documentation, see `essaykit.pdf`*