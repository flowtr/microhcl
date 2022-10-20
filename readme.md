# microhcl

C++20 header-only parser for the [Hashicorp Configuration Language](https://www.github.com/hashicorp/hcl).

## Requirements

- C++20-compliant compiler
- CMake >= 3.21

## Usage

```c++
std::ifstream ifs("foo.hcl");
hcl::ParseResult parseResult = hcl::parse(ifs);

if (!parseResult.valid()) {
    std::cout << parseResult.errorReason << std::endl;
    return;
}

const hcl::Value& value = parseResult.value;
```

## To Do

- Block comments
- Negative float numbers
- Fix escape sequences such as `\a`
- Preserve comments
