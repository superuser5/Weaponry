# Weaponry

A collection of offensive code used for red team engagements. 

### ObfuscateMeterpeterReverseTcp.py
```
    * Basic shell code loader. (Credit: https://ired.team)

    * Uses subprocess to call MSFVenom, creating a reverse TCP payload with supplied LHOST and LPORT parameters, saving C payload to a temporary file.

    * Loads temporary file, replacing standard variable names with random values of varying lengths, altering static signature of the executable.

    * Outputs modified Meterpeter payload in C for compilation with Visual Studio Community

    TODO: Add in "junk" logic, more anti-debug.

```

### ExclusionDrop.ps1
```
   * Writes Add-MpPreference -ExclusionExtension (".exe", ".dll") to a file in %TEMP%
   
   * Uses SDCLT.exe to escalate privileges and call above script.
   
   * Once EXE &  DLLs are excluded, Meterpreter payload is downloaded + executed.
   
   * Remove PS1 from %TEMP%
   
   * Restore SDCLT.exe functionality.
   ```

### Canary.ps1
```
   * Grab Username + Domain from environment variables.
   
   * Get Local IP from WMI query.
   
   * Get External IP from API (ipconfig.me)
   
   * Send string over socket to defined EndPoint + Port.
   
   * Server: nc -lvpk <Port>
   
 ```
