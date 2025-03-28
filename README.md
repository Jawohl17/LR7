# Laboratory Work № 7
## Topic: Creating Script Scenarios and Determining System Hardware Configuration

### Objective
To gain practical skills in working with the Bash command shell and to become familiar with basic actions when working with script scenarios.

### Glossary of Terms
- **Shell Script:** A file containing executable commands stored in a text format.
- **Shebang:** A special line at the beginning of a script that indicates which interpreter to use for execution.
- **chmod:** A command used to change file access permissions.
- **Variables:** Variables that store temporary information in the script.
- **Conditionals:** Conditions that allow different actions to be performed based on tests.
- **Loops:** Loops that allow the same action to be performed multiple times.

### Answers to Questions 4.1 and 4.5
# System Administration and Shell Scripting Guide

## 1. Script Scenario in the Command Shell

A **script scenario**, or **shell script**, is a file that contains a sequence of commands executed by a command-line interpreter (**shell**).  
It allows users to:
- Automate repetitive tasks
- Manage system operations
- Execute complex sequences of commands without manual input  

Shell scripts can include **variables, conditionals, loops, and functions**, making them powerful tools for **system administration** and **programming**.

---

## 2. Creating and Running Scripts

### Creating a Script:
1. Open a text editor (e.g., `nano`, `vim`, or `gedit`).
2. Create a new file with a `.sh` extension (e.g., `script.sh`).
3. Write the desired commands in the file.

### Editing a Script:
- Open the script file in a text editor, modify it, and save the changes.

### Running a Script:
1. Make the script executable:
   ```sh
   chmod +x script.sh
   ```
2. Execute the script:
   ```sh
   ./script.sh
   ```

---

## 3. Main Components of a Motherboard

| Component        | Description |
|-----------------|-------------|
| **CPU Socket**  | Slot for installing the processor (CPU). |
| **RAM Slots**   | Slots for installing memory modules (RAM). |
| **Chipset**     | Manages data flow between CPU, memory, and peripherals. |
| **Expansion Slots** | Slots for additional cards (e.g., graphics, sound cards). |
| **Power Connectors** | Supply power to the motherboard. |
| **Storage Connectors** | SATA or M.2 connectors for storage devices (HDDs, SSDs). |

---

## 4. MBR vs. GPT Partitioning

| Partitioning Scheme | Description |
|--------------------|-------------|
| **MBR (Master Boot Record)** | Used in older systems, supports drives up to **2 TB**, and allows **4 primary partitions**. Common in **BIOS-based** systems. |
| **GPT (GUID Partition Table)** | Supports **larger drives** (>2 TB) and up to **128 partitions**. Used in **UEFI-based** systems with better data integrity and recovery. |

---

## 5. Mounting Operation in Linux

**Mounting** is the process of making a **file system** on a storage device accessible to the operating system.  

### Why is it Needed?
- Allows users to **access files** and directories on external/internal drives.
- Enables the OS to **read/write data** on storage devices.
- Without mounting, the OS **cannot recognize or interact** with the data.

### Main Steps of the Work
1. Start the Linux operating system (Ubuntu).
2. Log in and open the terminal.
3. Familiarize yourself with command examples from the NDG Linux Essentials lab work.
4. Create a table to describe the commands.

### Command Table

| Command Name | Purpose and Functionality |
|-------------|---------------------------|
| `echo`      | Outputs text to the screen. |
| `ls`        | Lists files in a directory. |
| `cd`        | Changes the current directory. |
| `chmod`     | Changes file access permissions. |
| `mkdir`     | Creates a new directory. |
| `rm`        | Deletes files or directories. |

# Creating Script Scenarios
Script 1: Greeting Output

![image](https://github.com/user-attachments/assets/eac6c034-81b2-41c0-874b-f2ffa5915452)
![image](https://github.com/user-attachments/assets/67d9824c-8117-470c-908a-d3748e74e2f5)


 **'$(whoami)'**  outputs the name of the current user.

 
 **'$(date)'** outputs the current date and time.

 
 **'uname -a'** provides general information about the system.

# Script 2: Outputting Hardware Configuration Information
![image](https://github.com/user-attachments/assets/0b8a49fc-feca-4058-9fe7-64528db122db)
![image](https://github.com/user-attachments/assets/41b3b584-675f-40ce-abe8-999be5d1f434)
![image](https://github.com/user-attachments/assets/c3f54007-f03d-4ef4-a1d6-16b9cf2ced31)


**'lscpu** Displays detailed information about the CPU architecture.


**'free -h**' Shows the amount of used and free memory in a human-readable format.


**'df -h**' Reports disk space usage and availability on file systems in a human-readable format.


# Script 3: Example Script Scenario
![image](https://github.com/user-attachments/assets/460b8de8-b0e7-4e8b-9ca4-285d4b426917)


**'for i in {1..5}**' This line initiates a loop that iterates over the numbers 1 to 5.


**'do**' Indicates the start of the commands to be executed in each iteration of the loop.


**'echo "num $i"**' This command outputs the text "Loop number" followed by the current value of i for each iteration.


**'done:**' Marks the end of the loop.



# System Information and Management Commands

## 1. Difference Between `arch` and `lscpu`
- **`arch`**: Outputs the architecture of the processor, such as `x86_64` for 64-bit systems. It provides a simple indication of the CPU architecture being used.
- **`lscpu`**: Provides detailed information about the CPU architecture, including the number of CPU cores, threads, model name, CPU family, and other relevant details about the processor.

## 2. Checking System RAM Usage
To display the amount of used and free memory in the system in a human-readable format, use:
```sh
free -h
```

## 3. Variables, Branching, and Looping in Scripts
### Variables:
Variables can be declared using:
```sh
variable_name=value
```
To access the value of a variable, use:
```sh
echo $variable_name
```

### Branching:
Conditional statements can be created using `if`, `else`, and `elif`:
```sh
if [ $var -eq 10 ]; then
    echo "Variable is 10"
elif [ $var -gt 10 ]; then
    echo "Variable is greater than 10"\else
    echo "Variable is less than 10"
fi
```

### Loops:
- **For loop**:
```sh
for i in {1..5}; do
    echo "Iteration $i"
done
```
- **While loop**:
```sh
while [ $var -lt 10 ]; do
    echo "Var is $var"
    var=$((var+1))
done
```
- **Until loop**:
```sh
until [ $var -ge 10 ]; do
    echo "Var is $var"
    var=$((var+1))
done
```

## 4. Checking Peripheral Devices
- **List USB devices**:
```sh
lsusb
```
- **List PCI devices**:
```sh
lspci
```

## 5. `gparted` Capabilities
`gparted` (GNOME Partition Editor) allows users to:
- Create, delete, resize, and move disk partitions.
- Format partitions with different file systems.
- Check and repair file systems.
- Manage partition flags and labels.
- View partition information and usage statistics.

### Installation
To install `gparted`, use:
```sh
sudo apt install gparted  # Debian/Ubuntu
sudo dnf install gparted  # Fedora
sudo pacman -S gparted    # Arch Linux
```

### Running `gparted`
To run `gparted` with root privileges:
```sh
sudo gparted
```

### conclusions

Completing Laboratory has significantly enhanced my skills in Bash scripting and system administration, providing me with practical experience in automating tasks, managing system resources, understanding hardware components, and utilizing commands for effective data management and troubleshooting.
