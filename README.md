# keep_computer_awake

#Copy this code to powershell file and run!
#Make sure notepad is closed when you run the powershell file

#Change the line below to point to your notepad program on your computer. 

#If you have trouble message me on TikTok

Start-Process "C:\Program Files\WindowsApps\Microsoft.WindowsNotepad_11.2210.5.0_x64__8wekyb3d8bbwe\Notepad\Notepad"

$wshell = New-Object -ComObject wscript.shell;
$wshell.AppActivate('notepad')

Sleep 1

for ($i = 0; $i -lt 20011; $i++) {
    $wshell.AppActivate('notepad')
    $wshell.SendKeys("I will stay awake")
    Sleep 1
    for ($i = 0; $i -lt 17; $i++) {
        $notepad = Get-Process notepad -ErrorAction SilentlyContinue
        if ($notepad -eq $null) {
            break
        }
        Write-Host('running')
        $wshell.AppActivate('notepad')
        $wshell.SendKeys("{BACKSPACE}")
        Sleep 1
    }
    $notepad = Get-Process notepad -ErrorAction SilentlyContinue
    if ($notepad -eq $null) {
        Write-Host('quit')
        break
    }
    Write-Host('running')
}

