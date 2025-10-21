# Remove-OldJava



Step 1: Uninstall old Java RTE:
```bat
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F32180111F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180111F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F32180141F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F32180144F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F32180161F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180161F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180181F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F32180191F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180191F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F32180201F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180201F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F32180231F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180231F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F32180251F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180251F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180261F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F32180291F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180301F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180333F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180341F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180351F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180361F0}
MsiExec.exe /qn /norestart /X{26A24AE4-039D-4CA4-87B4-2F64180371F0}
MsiExec.exe /qn /norestart /X{77924AE4-039E-4CA4-87B4-2F64180381F0}
MsiExec.exe /qn /norestart /X{71324AE4-039E-4CA4-87B4-2F64180391F0}
MsiExec.exe /qn /norestart /X{71024AE4-039E-4CA4-87B4-2F64180401F0}
MsiExec.exe /qn /norestart /X{77924AE4-039E-4CA4-87B4-2F64180411F0}
MsiExec.exe /qn /norestart /X{71024AE4-039E-4CA4-87B4-2F64180431F0}
MsiExec.exe /qn /norestart /X{77724AE4-039E-4CA4-87B4-2F64180441F0}
```


Step 2: Uninstall old Java JDK:
```bat
MsiExec.exe /qn /norestart /X{3FA68A00-9C88-5E69-870A-B40CB89DC2EF}
MsiExec.exe /qn /norestart /X{64A3A4F4-B792-11D6-A78A-00B0D0170800}
MsiExec.exe /qn /norestart /X{64A3A4F4-B792-11D6-A78A-00B0D0180181}
MsiExec.exe /qn /norestart /X{32A3A4F4-B792-11D6-A78A-00B0D0180192}
MsiExec.exe /qn /norestart /X{64A3A4F4-B792-11D6-A78A-00B0D0180192}
MsiExec.exe /qn /norestart /X{64A3A4F4-B792-11D6-A78A-00B0D0180211}
```



Step 3: Remove Autorun
```bat
reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Run" /v "SunJavaUpdateSched" /f
```


Step 4: Clean up Start Menu shortcuts
```powershell
rm -Recurse -Force "C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Java"
rm -Recurse -Force "C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Java Development Kit"
```