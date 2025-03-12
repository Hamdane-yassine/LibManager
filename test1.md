# Understanding DLLs in .NET: Class Libraries vs. Executable DLLs

## 1. Class Library DLLs
- **Purpose**: Contains reusable code (e.g., classes, methods) without an entry point.
- **Entry Point**: **No `Main` method**.
- **Execution**: Cannot be executed directly. Must be referenced by an application (e.g., `.exe` or another `.dll`).
- **Use Case**: Shared functionality (e.g., utility libraries, algorithms).
- **Example**: A third-party algorithm library shipped as a `.dll`.

---

## 2. Executable DLLs
- **Purpose**: Contains application logic, including an entry point.
- **Entry Point**: **Has a `Main` method**.
- **Execution**: Can be executed directly using:
  - The `dotnet` CLI (e.g., `dotnet app.dll`).
  - Wine (e.g., `wine app.dll`).
- **Use Case**: Represents the entire application code in modern .NET.
- **Example**: A console app or Windows app compiled as a `.dll`.

---

## 3. Key Differences

| **Aspect**              | **Class Library DLL**                          | **Executable DLL**                              |
|--------------------------|-----------------------------------------------|------------------------------------------------|
| **Entry Point**          | No `Main` method.                             | Contains a `Main` method.                      |
| **Purpose**              | Reusable code for other applications.         | Represents the entire application code.         |
| **Execution**            | Cannot be executed directly.                  | Can be executed directly (e.g., `dotnet` or Wine). |
| **Example**              | A utility library for math functions.         | A console app compiled as a `.dll`.            |

---

## 4. When Did Executable DLLs Become Standard?
- **.NET Core 1.0 (2016)**: Introduced the concept of platform-agnostic `.dll` files with entry points.
- **.NET 5+ (2020)**: Unified .NET Core and .NET Framework, making executable `.dll` files the default for console and Windows apps.

### Key Changes:
- **.NET Core 1.0+**: Applications produce both `.exe` (platform-specific launcher) and `.dll` (platform-agnostic application code).
- **.NET 5+**: The `.dll` file contains the entry point and can be executed directly using `dotnet` or Wine.

---

## 5. How to Identify if a DLL is Executable
- **Check for Entry Point**:
  - Use the `dotnet` CLI:
    ```bash
    dotnet <path-to-dll> --info
    ```
  - If the DLL has a `Main` method, it is executable.
- **Third-Party DLLs**:
  - If the DLL is provided as a **Class Library**, it will **not** have an entry point and cannot be executed directly.
  - If the DLL is provided as an **application**, it may have an entry point and can be executed.

---

## 6. Practical Implications for Your Project
- **Third-Party DLLs**: If the third party ships a `.dll` as a **Class Library**, it will **not** have an entry point and cannot be executed directly. It is safe to assume it is not an executable DLL.
- **Executable DLLs**: If the `.dll` is part of an application build (e.g., from .NET Core or .NET 5+), it may have an entry point and can be executed.

---

## 7. Conclusion
- **Class Library DLLs**: Reusable code without an entry point. Cannot be executed directly.
- **Executable DLLs**: Application code with an entry point. Can be executed using `dotnet` or Wine.
- **.NET Core 1.0+**: Introduced executable `.dll` files as part of cross-platform support.

For your project, if the third party provides a `.dll` as a **Class Library**, it is **not executable** and is safe for protecting intellectual property.
