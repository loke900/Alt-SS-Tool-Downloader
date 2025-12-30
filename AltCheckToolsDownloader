# Folder name on Desktop
$folderName = "Downloaded Tools"
$desktopPath = [Environment]::GetFolderPath("Desktop")
$downloadPath = Join-Path $desktopPath $folderName

# Create folder if it doesn't exist
if (!(Test-Path $downloadPath)) {
    New-Item -ItemType Directory -Path $downloadPath | Out-Null
}

# Files to download
$files = @{
    "Everything-Setup.exe" = "https://www.voidtools.com/Everything-1.4.1.1030.x86-Setup.exe"
    "SystemInformer-Canary.exe" = "https://github.com/winsiderss/si-builds/releases/download/3.2.25297.1516/systeminformer-build-canary-setup.exe"
    "FTK-Imager.exe" = "https://d1kpmuwb7gvu1i.cloudfront.net/AccessData_FTK_Imager_4.7.1.exe"
    "Espouken.exe" = "https://github.com/spokwn/Tool/releases/download/v1.1.3/espouken.exe"
}

# Download files
foreach ($file in $files.GetEnumerator()) {
    $destination = Join-Path $downloadPath $file.Key
    Invoke-WebRequest -Uri $file.Value -OutFile $destination
}

Write-Host "All files downloaded successfully to $downloadPath"
