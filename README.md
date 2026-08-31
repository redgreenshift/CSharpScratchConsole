# CSharpScratchConsole

A C# scratchpad for exploring and testing algorithms, utility functions, and file-based data operations.

[![C#](https://img.shields.io/badge/language-C%23-68217A.svg?logo=csharp&logoColor=white)](https://learn.microsoft.com/en-us/dotnet/csharp/)
[![.NET Framework](https://img.shields.io/badge/Framework-8.0-512BD4.svg?logo=dotnet&logoColor=white)](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework)
[![License: GPL-2.0-only](https://img.shields.io/badge/License-GPL--2.0--only-2D6CDF.svg)](LICENSE)

[![Windows](https://img.shields.io/badge/Windows-0078D6.svg?logo=windows&logoColor=white)](https://www.microsoft.com/windows)

## Features / Current Implementations

### 1. Password Generator (`CreatePassword`)
Generates a cryptographically secure 15-character password in a segmented format.
- **Format**: `XXXXX-XXXXX-XXXXX` (15 characters plus dashes).
- **Security**: Uses `System.Security.Cryptography.RandomNumberGenerator` for high-entropy randomness.
- **Diversity**: Ensures at least one character from each of these categories:
    - Digits (`0-9`)
    - Uppercase letters (`A-Z`)
    - Lowercase letters (`a-z`)
    - Special characters (`!?()$%`)
- **Algorithm**: Uses a Fisher-Yates (Durstenfeld) shuffle to ensure uniform distribution of characters across the string.

### 2. JSON File Merging (`MergeJsonFiles`)
A utility to merge two JSON files containing string-to-string dictionaries.
- **Logic**: Combines keys from both input files into a single dictionary.
- **Conflict Resolution**: If a key exists in both files with different values, the conflict is resolved via user input (currently hardcoded to option `1` for automated testing).
- **Output**: The merged result is written as a JSON-serialized string to the provided `TextWriter`.

### 3. Date List Generation (`GenerateDateList`)
Generates a sequence of formatted date strings for a specified duration.

## Running the Code

The project is a .NET console application. You can run it using the following command:

```bash
dotnet run

▎ [!NOTE]
▎ Testing Mode: The current implementation of MergeJsonFiles expects input files to exist at C:\temp\left.txt and C:\temp\right.txt. If these files are not present, the application will throw a FileNotFoundException as part of its "fail-fast" testing design.

Technologies Used

- .NET (C#)
- Newtonsoft.Json: For JSON serialization and deserialization.
- System.Security.Cryptography: For cryptographically secure random number generation.
- System.IO: For file and stream handling.

How to use

Since this is a scratchpad, the main logic is contained within Program.cs. You can modify the Main method or the utility methods to test different scenarios or parameters.