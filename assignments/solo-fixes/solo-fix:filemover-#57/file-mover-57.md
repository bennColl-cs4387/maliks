# Bug Fix Report: Case Sensitivity in File Types

## Issue Overview
The issue was identified in the file handling process where the program failed to move all files with extensions such as `.jpeg` if they were named with varying cases (e.g., `.JPEG`, `.Jpeg`). This case sensitivity led to the unintended omission of files with uppercase or mixed-case extensions. This issue was reported in [Issue #57](https://github.com/AustinCGomez/Python-File-Mover/issues/57) by @AustinCGomez.

## Bug Description
In the initial implementation, file extension checks were case-sensitive, meaning that the program only recognized extensions in the exact casing provided by the user. Consequently, files with extensions in uppercase or mixed case were ignored, as they did not match the expected lowercase format.

## Fix Implementation

### Normalization of File Extensions
The main bug fix involved normalizing both the user-provided file extensions and the file extensions in the directory to lowercase, allowing for case-insensitive comparisons. This change ensures that all variations of the same extension (e.g., `.jpeg`, `.JPEG`, `.Jpeg`) are recognized as equivalent, allowing the program to correctly process and move all files with the specified extension, regardless of case.

#### Code Analysis
1. **Lowercase Conversion of User Extensions**: 
   - The code now includes a step where `user_extensions` is normalized to lowercase, ensuring that the extensions provided by the user are stored and checked in a consistent format.
   - This change can be observed in the addition:
     ```python
     normalized_extensions = [ext.lower() for ext in self.user_extensions]
     ```

2. **Case-Insensitive Comparison in File Moving Process**:
   - During the file-moving process, each file’s extension is converted to lowercase before comparing it to the normalized list of user extensions. This allows the program to match files regardless of how the extension is capitalized.
   - The modified comparison uses:
     ```python
     if any(file.lower().endswith(ext) for ext in normalized_extensions):
     ```
   - This updated logic ensures that files with extensions like `.JPEG`, `.Jpeg`, and `.jpeg` are all processed identically.

## Impact and Testing
The program now robustly handles variations in file extension casing. Testing confirmed with the pre exisiting test cases.

## Additional Information
- **Pull Request**: [Update Comparison Logic to Case-Insensitive](https://github.com/AustinCGomez/Python-File-Mover/pull/60)
- **Original Issue**: [Case Sensitive File Types - Issue #57](https://github.com/AustinCGomez/Python-File-Mover/issues/57)
