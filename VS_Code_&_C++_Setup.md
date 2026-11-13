# C++ & VS Code – Complete Setup Guide

A step-by-step guide to setting up your C++ development environment for DSA.

## 1. Download and Install Visual Studio Code

1. Visit the official website: https://code.visualstudio.com/
2. Click **Download for Windows**.
3. Download the Windows User Installer.
4. Run the installer and follow the installation instructions.
5. During installation, enable:
   - Add to PATH
   - Add "Open with Code" action (optional)
   - Create a desktop icon (optional)

Open VS Code after installation.

## 2. Install the C/C++ Extension

1. Open VS Code.
2. Navigate to the Extensions tab (`Ctrl + Shift + X`).
3. Search for **C/C++**.
4. Install the extension published by Microsoft.

This provides:
- Syntax highlighting.
- IntelliSense and code suggestions.
- Error detection.
- Debugging support.

**Note:** The extension does not include a C++ compiler. You need to install one separately.

## 3. Install the C++ Compiler (MinGW-w64 via MSYS2)

We'll use MSYS2 to install the MinGW-w64 GCC toolchain.

**Step 1: Download MSYS2**

Visit: https://www.msys2.org/

- Download the official installer.
- Run the installer.
- Use the default installation directory: `C:\msys64`
- Complete the installation and launch MSYS2.

**Step 2: Install the compiler**

Open the **MSYS2 UCRT64** terminal from the Start menu.

Execute:

```bash
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```

- Press Enter to accept the default package selection.
- Type `Y` when prompted to proceed.
- Wait for the installation to complete.

This installs GCC, G++, GDB and other required development tools.

## 4. Configure the PATH Environment Variable

This step allows Windows and VS Code to locate the C++ compiler from any terminal.

1. Open Windows Search.
2. Search for **Edit the system environment variables**.
3. Click **Environment Variables**.
4. Under *User variables*, select `Path`.
5. Click **Edit → New**.
6. Add the following path:

```text
C:\msys64\ucrt64\bin
```

7. Click OK on all open windows to save the changes.
8. Close and reopen your terminals and VS Code.

**Important:** If you installed MSYS2 in a different location, use the corresponding `ucrt64\bin` path.

## 5. Verify Your Installation

Open a NEW terminal in VS Code (`Ctrl + ~`).

Execute these commands individually:

```bash
g++ --version
gcc --version
gdb --version
```

If the commands display version information, your compiler and debugger are accessible.

If you get an error such as `'g++' is not recognized`, recheck your PATH configuration and restart the terminal.

## 6. Run Your First C++ Program

1. Open VS Code.
2. Select **File → New File**.
3. Save the file as `main.cpp`.
4. Enter the following code:

```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!" << endl;
    return 0;
}
```

5. Open the integrated terminal (`Ctrl + ~`).

**Compile the program:**

```bash
g++ main.cpp -o main
```

**Execute the program (Windows PowerShell):**

```powershell
.\main.exe
```

Expected output:

```text
Hello, World!
```

## 7. Understanding Input and Output

Try another program:

```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b;
    cin >> a >> b;

    cout << a + b << endl;
    return 0;
}
```

Input:
```text
10 20
```

Output:
```text
30
```

## 8. Basic VS Code Debugging

Familiarise yourself with these debugging features:

- **Breakpoint:** Pause execution at a selected line.
- **Continue (F5):** Resume execution.
- **Step Over (F10):** Execute the current line.
- **Step Into (F11):** Enter a function.
- **Variables:** Inspect variable values during execution.
- **Watch:** Monitor specific expressions or variables.

To start debugging, set a breakpoint, press F5 and select the GDB debugger configuration if prompted.

---

## Final Setup Checklist

Before starting your DSA practice, ensure:

- [ ] VS Code is installed.
- [ ] Microsoft C/C++ extension is installed.
- [ ] MSYS2 and MinGW-w64 toolchain are installed.
- [ ] MinGW-w64 `bin` directory is added to PATH.
- [ ] `g++ --version` works in the terminal.
- [ ] You can successfully compile and execute a C++ program.

**Official References:**

- [Visual Studio Code Downloads](https://code.visualstudio.com/download)
- [VS Code C++ Documentation](https://code.visualstudio.com/docs/languages/cpp)
- [MSYS2 Official Website](https://www.msys2.org/)
- [VS Code MinGW Setup Tutorial](https://code.visualstudio.com/docs/cpp/config-mingw)

**Happy Coding!**