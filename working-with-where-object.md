## Working with `Where-Object`

One of the most valuable concepts I learned was filtering objects with `Where-Object`.

### Challenge

I was given a task to identify a Windows service whose **DisplayName** had been modified by a suspicious user.

My first attempt was:

```powershell
Get-Service | Where-Object -DisplayName "merry life and a short one"
```

This command did **not** work because `Where-Object` doesn't have a `-DisplayName` parameter.

The correct solution was:

```powershell
Get-Service | Where-Object {$_.DisplayName -like "*merry life and a short one*"}
```

---

## Understanding the Command

Breaking down the solution:

### `Get-Service`

Returns all Windows services as **objects**.

### `|` (Pipeline)

Passes each service object to the next command.

### `Where-Object`

Filters objects based on a condition.

### `$_`

Represents the **current object** being processed in the pipeline.

### `.DisplayName`

Accesses the **DisplayName** property of the current service object.

### `-like`

Performs wildcard matching.

Example:

```powershell
"*Defender*"
```

Matches any text containing **Defender**.

The asterisk (`*`) represents zero or more characters before or after the specified text.

---

## Common Comparison Operators

| Operator   | Description                       |
| ---------- | --------------------------------- |
| `-eq`      | Equals                            |
| `-ne`      | Not equal                         |
| `-like`    | Matches a wildcard pattern        |
| `-notlike` | Does not match a wildcard pattern |
| `-gt`      | Greater than                      |
| `-lt`      | Less than                         |
| `-ge`      | Greater than or equal to          |
| `-le`      | Less than or equal to             |

### Examples

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

```powershell
Get-Service | Where-Object {$_.Name -like "*Win*"}
```

```powershell
Get-Process | Where-Object {$_.CPU -gt 100}
```

---

## Discovering Object Properties

One command I'll continue using is:

```powershell
Get-Service | Get-Member
```

This displays all the properties and methods available on the objects returned by `Get-Service`.

You can also inspect all properties of a single object:

```powershell
Get-Service | Select-Object -First 1 *
```

---

## Properties Commonly Used for Filtering

### Services

```powershell
Get-Service
```

Useful properties:

* `Name`
* `DisplayName`
* `Status`
* `ServiceType`

### Processes

```powershell
Get-Process
```

Useful properties:

* `Name`
* `Id`
* `CPU`
* `Handles`
* `WorkingSet`

### Local Users

```powershell
Get-LocalUser
```

Useful properties:

* `Name`
* `Enabled`
* `Description`
* `SID`

### Files and Directories

```powershell
Get-ChildItem
```

Useful properties:

* `Name`
* `Length`
* `Extension`
* `CreationTime`

---

## Automatic Variables

PowerShell includes several built-in automatic variables.

| Variable        | Purpose                                                   |
| --------------- | --------------------------------------------------------- |
| `$_`            | Represents the current object in the pipeline             |
| `$PSItem`       | Alias for `$_`                                            |
| `$?`            | Indicates whether the last command completed successfully |
| `$$`            | Represents the last token in the last command entered     |
| `$LASTEXITCODE` | Stores the exit code of the last native program that ran  |
| `$null`         | Represents an empty or null value                         |

---

## What I Learned

This exercise taught me that PowerShell isn't just a command-line tool—it's an object-oriented automation framework.

Instead of memorizing commands, I now understand how to:

* Work with objects instead of plain text.
* Filter results using `Where-Object`.
* Access object properties with dot notation.
* Use comparison operators to build conditions.
* Discover available properties with `Get-Member`.
* Apply the same concepts to services, processes, users, files, and many other PowerShell objects.

Understanding **why** a command works is far more valuable than simply memorizing the syntax.
