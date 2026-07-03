# date-class

A minimal, well-documented C++ Date utility focused on correctness, clarity, and ease of integration.

This repository provides a compact Date class implementation with parsing, formatting, arithmetic, and validation helpers. It is designed for educational use and as a lightweight utility for projects that need reliable date handling without heavy dependencies.

---

## Key features

- Construct Date objects from year, month, and day
- Accurate validation (including leap-year rules)
- Add and subtract days, months, and years
- Comparison operators and date difference calculations
- ISO-8601 string formatting (YYYY-MM-DD)
- Minimal, dependency-free implementation suitable for embedding

---

## Table of contents

- [Installation](#installation)
- [Usage](#usage)
- [API](#api)
- [Building & Tests](#building--tests)
- [Development](#development)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Installation

This project is a header/source C++ utility. Include the `src/` files in your project or build as a small static library.

Clone the repository:

```bash
git clone https://github.com/Dawood-Al-kharazy/date-class.git
cd date-class
```

If you prefer to install via a package manager, add instructions here when the package is published.

---

## Usage

Basic example (adjust include path to match your layout):

```cpp
#include "Date.h"
#include <iostream>

int main() {
    Date d(2026, 7, 3);
    std::cout << d.toString() << "\n";          // 2026-07-03

    Date d2 = d + 5;                             // add 5 days
    std::cout << d2.toString() << "\n";        // 2026-07-08

    if (!Date::isValid(2026, 2, 30)) {
        std::cout << "Invalid date supplied" << std::endl;
    }

    return 0;
}
```

---

## API

The following is a suggested public API. Update to match the repository implementation if names differ.

- Date(int year, int month, int day)
- static bool isValid(int year, int month, int day)
- bool isLeapYear() const
- void addDays(int n)
- Date operator+(int days) const
- Date operator-(int days) const
- int operator-(const Date &other) const  // difference in days
- bool operator==(const Date &other) const
- std::string toString() const            // ISO-8601 `YYYY-MM-DD`

Document any additional utility functions (dayOfWeek, daysInMonth, parseFromString, etc.) here.

---

## Building & tests

This project supports simple builds with g++ or CMake. Tests (if included) use the chosen test framework (Catch2, GoogleTest, or doctest).

Build example with g++:

```bash
g++ -std=c++17 -O2 -Wall -Wextra -o date_example src/Date.cpp src/main.cpp
./date_example
```

Build with CMake (recommended for cross-platform builds):

```bash
mkdir build && cd build
cmake ..
cmake --build . --config Release
ctest --output-on-failure
```

---

## Development

- Keep the implementation small and well-documented. Prefer clarity over micro-optimizations.
- Add unit tests for edge cases: end-of-month transitions, leap years, negative offsets, and historical dates as needed.
- Use continuous integration to run tests on each PR.

---

## Contributing

Contributions are welcome. To contribute:

1. Fork the repository.
2. Create a branch named `feat/your-feature` or `fix/issue-description`.
3. Add tests for new behavior and ensure existing tests pass.
4. Open a pull request with a clear description of changes.

Please follow the existing code style and add comments where behavior is non-obvious.

---

## License

This repository does not include a license file. To make the project open-source, add a `LICENSE` file (for example, the MIT License). Without a license, others have limited rights to reuse the code.

---

## Contact

Maintainer: Dawood-Al-kharazy

For questions, issues, or feature requests, please open an issue on this repository.
