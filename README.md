# Date Class (C++)

A simple, well-tested C++ Date class that provides basic date manipulation, validation, and formatting utilities. This project is intended as an educational implementation to demonstrate design, operator overloading, and date arithmetic in modern C++.

## Features

- Construct date objects from year, month, and day
- Validation of dates (including leap years)
- Add / subtract days
- Comparison operators (==, !=, <, <=, >, >=)
- String formatting (ISO 8601: YYYY-MM-DD)
- Conversion helpers and utility functions (day of week, days in month)

## Getting Started

These instructions will help you build and run the project locally.

### Requirements

- A C++ compiler that supports C++17 or later (g++, clang++, MSVC)
- CMake (optional, recommended for cross-platform builds)

### Build with g++

If the repository contains a single header/source pair (e.g., `Date.h`, `Date.cpp`) and an example `main.cpp`:

```bash
g++ -std=c++17 -O2 -Wall -Wextra -o date_example src/Date.cpp src/main.cpp
./date_example
```

### Build with CMake

If a CMakeLists.txt is provided, the typical workflow is:

```bash
mkdir build && cd build
cmake ..
cmake --build . --config Release
./date_example
```

## Usage

Example usage for a typical Date class API:

```cpp
#include "Date.h"
#include <iostream>

int main() {
    Date d(2024, 2, 28);
    std::cout << d.toString() << "\n"; // 2024-02-28

    d.addDays(1);
    std::cout << d.toString() << "\n"; // 2024-02-29 (leap year)

    Date a(2023, 12, 31);
    Date b = a + 1; // or b.addDays(1)
    if (b > a) std::cout << b.toString() << std::endl;

    return 0;
}
```

Adjust the example to match the actual API in `Date.h` / `Date.cpp`.

## API (Suggested)

- Date(int year, int month, int day)
- bool isValid() const
- bool isLeapYear() const
- void addDays(int n)
- Date operator+(int days) const
- Date operator-(int days) const
- int operator-(const Date &other) const // difference in days
- bool operator==(const Date &other) const
- std::string toString() const

If your implementation uses different names, update the README examples accordingly.

## Tests

Include unit tests using your preferred framework (Catch2, GoogleTest, doctest). Example with Catch2:

```bash
# from repo root
mkdir build && cd build
cmake ..
cmake --build . --target test
```

## Contributing

Contributions are welcome. Please follow these guidelines:

- Open an issue to discuss major changes before implementing them.
- Fork the repository and create a feature branch for your changes.
- Write unit tests for new features and bug fixes.
- Ensure code is formatted and documented.

## License

No license is specified for this repository. If you would like to make this project open source, consider adding a license (for example, the MIT License) in a `LICENSE` file.

## Contact

Created by Dawood-Al-kharazy. If you have questions or suggestions, please open an issue or contact the maintainer via the GitHub profile.
