# Bug Fix Report: Case Sensitivity in File Types

## Issue Overview
The issue was identified in the file handling process where the program failed to move all `.jpeg` files if they were named with different cases, such as `.JPEG`. This was reported in issue #57 by user @AustinCGomez.

## Bug Description
The program did not account for case sensitivity when checking file extensions, leading to the omission of files with uppercase extensions.

## Fix Implementation

**Normalization of File Extensions**: 
   - The file extension checks were updated to be case-insensitive. This ensures that all variations of the `.jpeg` extension (e.g., `.JPEG`, `.Jpeg`, etc.) are recognized and processed correctly.

=### Additional Information
- **Pull Request**: [Update Comparison Logic to Case-Insensitive](https://github.com/AustinCGomez/Python-File-Mover/pull/60)
- **Original Issue**: [Case Sensitive File Types - Issue #57](https://github.com/AustinCGomez/Python-File-Mover/issues/57)
