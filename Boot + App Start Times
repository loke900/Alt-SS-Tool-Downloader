Write-Host "==== SYSTEM BOOT & APPLICATION START TIMES ====" -ForegroundColor Cyan
Write-Host ""

# System boot time
$bootTime = (Get-CimInstance Win32_OperatingSystem).LastBootUpTime
Write-Host "PC Boot Time: $bootTime" -ForegroundColor Green
Write-Host ""

# Function to get process start time
function Get-ProcessStartTime {
    param (
        [string]$ProcessName,
        [string]$DisplayName
    )

    $process = Get-Process -Name $ProcessName -ErrorAction SilentlyContinue | Select-Object -First 1

    if ($process) {
        Write-Host "$DisplayName started at: $($process.StartTime)" -ForegroundColor Yellow
    } else {
        Write-Host "$DisplayName is not currently running." -ForegroundColor Red
    }
}

# Apps
Get-ProcessStartTime "javaw" "Minecraft"
Get-ProcessStartTime "java"  "Minecraft"
Get-ProcessStartTime "Discord" "Discord"
Get-ProcessStartTime "AnyDesk" "AnyDesk"

Write-Host ""
Write-Host "============================================="
Pause
