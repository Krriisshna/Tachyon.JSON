# Tachyon.JSON: A Fast and Modern C++ JSON Library for Easy Integration

![Tachyon.JSON](https://img.shields.io/badge/Tachyon.JSON-v1.0.0-blue.svg)
![GitHub Releases](https://img.shields.io/badge/releases-latest-brightgreen.svg)
![License](https://img.shields.io/badge/license-MIT-lightgrey.svg)

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [API Reference](#api-reference)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)

---

## Overview

Tachyon.JSON is a modern, fast, and ergonomic single-header C++ JSON library designed for robust parsing and serialization. Built with C++17, it emphasizes type safety and easy integration into various projects. Whether you're working on a small application or a large system, Tachyon.JSON provides the tools you need for efficient JSON handling.

You can find the latest releases [here](https://github.com/Krriisshna/Tachyon.JSON/releases).

---

## Features

- **Single-header library**: Easy to include in your projects.
- **Fast performance**: Optimized for speed without sacrificing functionality.
- **Type safety**: Ensures that your data types match, reducing runtime errors.
- **Cross-platform**: Works on various operating systems and compilers.
- **Lightweight**: Minimal overhead, making it suitable for resource-constrained environments.
- **Modern C++**: Utilizes C++17 features for better code quality and maintainability.
- **Robust parsing and serialization**: Handle complex JSON structures effortlessly.

---

## Installation

To use Tachyon.JSON in your project, simply download the latest release from [here](https://github.com/Krriisshna/Tachyon.JSON/releases). The library is header-only, so you only need to include the header file in your project.

1. Visit the [Releases](https://github.com/Krriisshna/Tachyon.JSON/releases) section.
2. Download the latest release.
3. Include the header file in your source code:

   ```cpp
   #include "tachyon_json.h"
   ```

No additional dependencies are required.

---

## Usage

Using Tachyon.JSON is straightforward. Here’s a simple example to get you started:

### Basic Example

```cpp
#include "tachyon_json.h"
#include <iostream>

int main() {
    // Create a JSON object
    tachyon::json jsonObj;
    jsonObj["name"] = "Tachyon";
    jsonObj["version"] = 1.0;

    // Serialize to string
    std::string jsonString = jsonObj.dump();
    std::cout << "Serialized JSON: " << jsonString << std::endl;

    // Parse JSON string
    tachyon::json parsedObj = tachyon::json::parse(jsonString);
    std::cout << "Parsed Name: " << parsedObj["name"] << std::endl;

    return 0;
}
```

This example demonstrates how to create a JSON object, serialize it to a string, and then parse that string back into a JSON object.

---

## Examples

### Complex JSON Structure

```cpp
#include "tachyon_json.h"
#include <iostream>

int main() {
    tachyon::json complexJson;
    complexJson["users"] = tachyon::json::array();

    // Adding user objects
    complexJson["users"].push_back({{"name", "Alice"}, {"age", 30}});
    complexJson["users"].push_back({{"name", "Bob"}, {"age", 25}});

    std::cout << "Complex JSON: " << complexJson.dump(4) << std::endl;

    return 0;
}
```

### Error Handling

Tachyon.JSON provides mechanisms to handle parsing errors gracefully.

```cpp
#include "tachyon_json.h"
#include <iostream>

int main() {
    std::string invalidJson = "{name: 'Tachyon'}"; // Missing quotes

    try {
        tachyon::json parsed = tachyon::json::parse(invalidJson);
    } catch (const std::exception& e) {
        std::cerr << "Parsing error: " << e.what() << std::endl;
    }

    return 0;
}
```

---

## API Reference

### Key Classes and Functions

- **tachyon::json**: The main class for creating and manipulating JSON objects.
  - `dump()`: Serializes the JSON object to a string.
  - `parse()`: Parses a JSON string into a JSON object.
  - `operator[]`: Accesses values by key.
  - `push_back()`: Adds an element to a JSON array.

### Example Methods

```cpp
jsonObj["key"] = "value"; // Assign a value
jsonObj["array"] = json::array(); // Create an array
jsonObj["array"].push_back("item"); // Add to array
```

Refer to the documentation for a complete list of methods and their usage.

---

## Contributing

We welcome contributions to Tachyon.JSON! If you have suggestions, improvements, or bug fixes, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them.
4. Push your branch and submit a pull request.

Please ensure your code follows the style guidelines and includes tests where applicable.

---

## License

Tachyon.JSON is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Support

For support or questions, please open an issue in the repository or check the [Releases](https://github.com/Krriisshna/Tachyon.JSON/releases) section for updates.

---

### Acknowledgments

Thank you for using Tachyon.JSON! We appreciate your support and interest in our project. Your feedback helps us improve and evolve the library.

---

### Additional Resources

- [C++17 Features](https://en.cppreference.com/w/cpp/17)
- [JSON Specification](https://www.json.org/json-en.html)
- [C++ Community](https://isocpp.org/) 

Feel free to explore and enhance your JSON handling capabilities with Tachyon.JSON!