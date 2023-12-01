# Post Install

> ## 🪄 Patch Broadcom
- Download OCLP after installation macOS on drive | [Click to download OCLP](https://github.com/dortania/OpenCore-Legacy-Patcher/releases)
- Open OCLP
- Click Post-Install Root Patch
- Click Start Root Patching
- Done! The computer will restart automatically

> ## 🍎 Enable Apple Services (iMessage/iCloud/FaceTime)

- Download GenSMBIOS | [Click to download GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
- Open `GenSMBIOS.command`
- Type `1` to install MacSerial, then press ENTER.
- Type `3` to Generate SMBIOS, then press ENTER.
- Type `iMacPro1,1` or `MacPro7,1`, then press ENTER.
- Open `/EFI/OC/Config.plist` with any editor and navigate to `PlatformInfo -> Generic`
- Add the script's last result to `MLB, SystemSerialNumber and SystemUUID`

```diff
<key>PlatformInfo</key>
<dict>
  <key>Generic</key>
  <array>
    </dict>
      <key>AdviseFeatures</key>
      <false/>
      <key>MaxBIOSVersion</key>
      <false/>
      <key>MLB</key>
+     <string>00000000000000000</string>
      <key>ProcessorType</key>
      <integer>0</integer>
      <key>ROM</key>
      <data>00000000</data>
      <key>SpoofVendor</key>
      <true/>
      <key>SystemMemoryStatus</key>
      <string>Auto</string>
      <key>SystemProductName</key>
      <string>iMacPro1,1</string>
      <key>SystemSerialNumber</key>
+     <string>000000000000</string>
      <key>SystemUUID</key>
+     <string>00000000-0000-0000-0000-000000000000</string>
      </dict>
   </array>
</dict>
```

- Save and reboot.

> ## 📁 Extra
How mount EFI?
- Use `MountEFI` | [Click to download MountEFI](https://github.com/Andrej-Antipov/MountEFI/releases/tag/1.8)

I can enable HiDPI?
- Yes, use one-key-hidpi | [Click to download one-key-hidpi](https://github.com/xzhih/one-key-hidpi)
