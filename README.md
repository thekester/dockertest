
# Docker Functionality Test

This README provides a simple guide to verify that Docker is functioning correctly on your machine, whether you're using Windows or Linux.

## Prerequisites
Ensure that Docker is installed on your system. If not, you can install it from the official Docker website:
- [Docker for Windows](https://docs.docker.com/desktop/install/windows-install/)
- [Docker for Linux](https://docs.docker.com/desktop/install/linux-install/)

### Steps for Both Windows and Linux

### 1. Verify Docker Installation

#### On Windows (PowerShell or CMD)
Open PowerShell or Command Prompt and run:
```bash
docker --version
```
This will display the installed version of Docker, which should confirm that Docker is installed correctly.

#### On Linux (Terminal)
Open a terminal and run:
```bash
docker --version
```
This command will confirm that Docker is installed on your Linux machine.

### 2. Test Docker with a Simple Image

#### PowerShell Script (Windows)

```powershell
# Check if Docker is installed
$dockerVersion = docker --version

if ($dockerVersion) {
    Write-Host "Docker is installed: $dockerVersion"
    
    # Run a test container
    Write-Host "Running the 'hello-world' image to test Docker..."
    docker run hello-world

    # Check if the container ran successfully
    if ($?) {
        Write-Host "Docker is functioning correctly."
    } else {
        Write-Host "The container failed to launch. Check your Docker installation."
    }
} else {
    Write-Host "Docker is not installed on this machine."
}
```

#### Batch Script (CMD for Windows)

```batch
@echo off
REM Check if Docker is installed
docker --version
IF %ERRORLEVEL% NEQ 0 (
    echo Docker is not installed.
    exit /b 1
)

echo Docker is installed. Running the hello-world image...
docker run hello-world
IF %ERRORLEVEL% EQU 0 (
    echo Docker is functioning correctly.
) ELSE (
    echo The container failed to launch. Check your Docker installation.
)
```

#### Shell Script (Linux)

```bash
#!/bin/bash

# Check if Docker is installed
docker --version

if [ $? -eq 0 ]; then
    echo "Docker is installed."
    
    # Run a test container
    echo "Running the 'hello-world' image to test Docker..."
    docker run hello-world
    
    if [ $? -eq 0 ]; then
        echo "Docker is functioning correctly."
    else
        echo "The container failed to launch. Check your Docker installation."
    fi
else
    echo "Docker is not installed on this machine."
fi
```

### 3. Additional Test: Docker Compose (Optional)

If you have Docker Compose installed, you can also verify it with the following command:

#### On Windows
```powershell
docker-compose --version
```

#### On Linux
```bash
docker-compose --version
```

This command will output the version of Docker Compose, confirming that it is installed and functioning.

### 4. Troubleshooting

If Docker doesn't appear to be working correctly:
- Ensure that the Docker service is running.
- Check your system's documentation for troubleshooting Docker installation issues.

### Conclusion
By following the steps in this guide, you should be able to confirm that Docker is functioning correctly on your Windows or Linux system.

