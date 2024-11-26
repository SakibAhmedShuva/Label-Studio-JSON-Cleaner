# Label Studio JSON Cleaner

A robust Python utility to clean and fix encoding issues in Label Studio JSON annotation files while preserving annotation structure and positions. The tool now includes advanced special character analysis capabilities.

## Problem Statement

When working with Label Studio annotations, special characters and encoding issues can cause several problems:
- Model training failures due to malformed characters
- Shifted annotation positions during data conversion
- Processing errors in downstream tasks
- Reduced annotation efficiency and data quality
- Difficult-to-detect Unicode and special character issues

This tool addresses these challenges by providing both cleaning capabilities and comprehensive special character analysis while maintaining the integrity of annotation positions and structure.

Sample JSON file provided in "samples" folder.

## Features

- 🔍 Fixes common encoding issues (UTF-8 special characters)
- 📊 Analyzes and reports special character usage and frequency
- 🎯 Preserves annotation positions and structure
- 🛡️ Maintains JSON data integrity
- 📝 Supports nested JSON structures
- 🔄 Handles common problematic character sequences
- 📈 Generates detailed special character analysis reports

## Installation

```bash
# Clone the repository
git clone https://github.com/SakibAhmedShuva/Label-Studio-JSON-Cleaner.git

# Navigate to the project directory
cd Label-Studio-JSON-Cleaner
```

## Usage

### Cleaning JSON Files

```python
from ls_json_cleaner import clean_json_with_annotations

# Clean your Label Studio JSON file
input_file = "path/to/your/labelstudio_export.json"
output_file = "cleaned_annotations.json"
clean_json_with_annotations(input_file, output_file)
```

### Analyzing Special Characters

```python
from ls_json_cleaner import find_special_chars_in_json, print_analysis_report

# Analyze special characters in your JSON file
json_file = "path/to/your/labelstudio_export.json"
results = find_special_chars_in_json(json_file)
print_analysis_report(results)
```

The analysis will generate:
- A detailed console report showing character frequencies
- A comprehensive JSON report file with character details including:
  - Unicode names
  - Character categories
  - Hex values
  - Occurrence counts

## Character Analysis and Mappings

### Special Character Analysis
The analyzer identifies and reports on:
- Non-ASCII characters
- Unicode properties
- Character frequencies
- Character categories
- Hex values

### Cleaning Mappings
The cleaner handles the following common problematic character sequences:

```python
encoding_fixes = {
    'ÃƒÂ': 'A',
    'Ã': 'A',
    'ƒÂ': '',
    'â€™': "'",  # Smart quote
    'â€œ': '"',  # Left double quote
    'â€': '"',   # Right double quote
    'Ã©': 'e',
    'Ã¨': 'e',
    'Â': ' ',
    # Additional special character mappings
    '©': '(c)',     # COPYRIGHT SIGN
    '‰': '%',       # PER MILLE SIGN
    '¬': '-',       # NOT SIGN
    '¢': 'c',       # CENT SIGN
    # ... and more
}
```

## Benefits

1. **Improved Model Training**: Clean data leads to better model performance
2. **Maintained Accuracy**: Preserves annotation positions for accurate model training
3. **Error Prevention**: Reduces processing errors in downstream tasks
4. **Enhanced Efficiency**: Saves time by automatically fixing common encoding issues
5. **Better Data Insights**: Provides detailed analysis of special character usage
6. **Quality Assurance**: Helps identify potential encoding issues before they cause problems

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

If you encounter any issues or have questions, please [open an issue](https://github.com/SakibAhmedShuva/Label-Studio-JSON-Cleaner/issues) on GitHub.

## Author

Sakib Ahmed Shuva - [GitHub Profile](https://github.com/SakibAhmedShuva)
