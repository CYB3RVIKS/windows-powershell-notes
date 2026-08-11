## Overview

[Windows Powershell](https://tryhackme.com/room/windowspowershell)

Today I learnt the fundamentals of **Windows PowerShell**, a cross-platform task automation solution consisting of:

* A command-line shell
* A scripting language
* A configuration management framework

Unlike the traditional Windows Command Prompt (CMD), PowerShell uses an **object-oriented approach**, allowing commands to pass rich objects instead of plain text.

## Cmdlets

PowerShell commands are called **Cmdlets** and follow a **Verb-Noun** naming convention.

### Useful Cmdlets

| Cmdlet                              | Purpose                             |
| ----------------------------------- | ----------------------------------- |
| `Get-Command`                       | Lists all available Cmdlets         |
| `Get-Command -CommandType Function` | Displays only functions             |
| `Get-Help`                          | Shows help information for a Cmdlet |
| `Find-Module`                       | Searches for PowerShell modules     |
| `Get-ChildItem`                     | Lists files and directories         |
| `Set-Location`                      | Changes the current directory       |
| `New-Item`                          | Creates a new file or folder        |
| `Remove-Item`                       | Deletes files or folders            |
| `Copy-Item`                         | Copies files or directories         |
| `Get-Content`                       | Reads the contents of a file        |

## Piping

Piping (`|`) allows the output of one command to become the input of another command, making it possible to build powerful command pipelines.

## Practice Exercises

### 1. Display the largest file in the current directory

```powershell
Get-ChildItem | Sort-Object Length -Descending | Select-Object -First 1
```

### 2. Display files larger than 100 bytes

```powershell
Get-ChildItem | Where-Object Length -gt 100
```

## Key Takeaways

* PowerShell is far more powerful than CMD because it works with objects instead of plain text.
* Cmdlets use a consistent Verb-Noun format, making them easy to remember.
* Piping is one of PowerShell's most powerful features because it allows commands to work together seamlessly
* PowerShell works with **objects**, not just plain text.
* Cmdlets follow a **Verb-Noun** naming convention.
* The pipeline (`|`) passes objects from one command to another.
* Understanding objects and properties is essential for writing effective PowerShell commands.

---

