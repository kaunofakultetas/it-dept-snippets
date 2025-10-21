# Fix-WOL


Step 1: Disable fast startup in windows (CMD):
```batch
REG ADD "HKLM\SYSTEM\CurrentControlSet\Control\Session Manager\Power" /v HiberbootEnabled /t REG_DWORD /d 0 /f
```


Step 2: Allow wake from S5 (CMD):
```batch
REG ADD HKLM\SYSTEM\CurrentControlSet\Services\NDIS\Parameters /v AllowWakeFromS5 /t REG_DWORD /d 1 /f
```


Step 3: Configure network card "Advanced" settings (Powershell):
```powershell
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Energy-Efficient Ethernet" -DisplayValue "Disabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Energy Efficient Ethernet" -DisplayValue "Disabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Green Ethernet" -DisplayValue "Disabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Power Saving Mode" -DisplayValue "Disabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Idle Power Saving" -DisplayValue "Disabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "System Idle Power Saver" -DisplayValue "Disabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Ultra Low Power Mode" -DisplayValue "Disabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Gigabit Lite" -DisplayValue "Disabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Wake on Magic Packet" -DisplayValue "Enabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Wake on pattern match" -DisplayValue "Enabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Shutdown Wake-On-Lan" -DisplayValue "Enabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Modern Standby WoL Magic Packet" -DisplayValue "Enabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Wake on magic packet when system is in the S0ix power state" -DisplayValue "Enabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Wake on link change" -DisplayValue "Enabled"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "Battery Mode Link Speed" -DisplayValue "100 Mbps First"
Set-NetAdapterAdvancedProperty -Name "Ethernet*" -DisplayName "WOL & Shutdown Link Speed" -DisplayValue "100 Mbps First"

```