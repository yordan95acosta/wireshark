# URL to your GitHub release asset
$installerUrl = "https://github.com/yordan95acosta/wireshark/releases/download/Wireshark-4.4.6-x64.exe/Wireshark-4.4.6-x64.exe"
$installerPath = "$env:TEMP\Wireshark-4.4.6-x64.exe"

# Download the installer
Invoke-WebRequest -Uri $installerUrl -OutFile $installerPath

# Install silently
Start-Process -FilePath $installerPath -ArgumentList "/S" -Wait

# Optional: Clean up
Remove-Item -Path $installerPath -Force
