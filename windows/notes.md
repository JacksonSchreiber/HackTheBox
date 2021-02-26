##WINDOWS

**Versions**
    OS Name                     Version Number

    Windows NT 4                4.0
    Windows 2000                5.0
    Windows XP                  5.1
    Windows Server 2003         5.2
    Windows Vista, Server 2008  6.0
    Windows 7, Server 2008 R2   6.1
    Windows 8, Server 2012      6.2
    Windows 8.1, Server 2012 R2 6.3
    Windows 10, 2016, 2019      10.0

**Basic OS Information**
    Get-WmiObject
        Get-WmiObject -Class win32_OperatingSystem | select Version,BuildNumber     #show build number
        Other Useful Classes
            Win32_Process   #gets process listing
            Win32_Service   #gets service listing
            Win32_Bios      #bios info

**Object Permissions**
    icacls <directory>      view/manage permissions
        ACCESS PERMISSIONS
            
            F : full access
            D :  delete access
            N :  no access
            M :  modify access
            RX :  read and execute access
            R :  read-only access
            W :  write-only access
        
        INHERITANCE SETTINGS
            
            (CI): container inherit
            (OI): object inherit
            (IO): inherit only
            (NP): do not propagate inherit
            (I): permission inherited from parent container
        
        icacls c:\users /grant joe:f    //grants joe full access to users folder, but not any of its files or subdirectories
        icacls c:\users /remove joe     //remove permissions


**Services**
    sc.exe
    Get-Service
        Get-Service | ? {$_.Status -eq "Running"}
**Powershell**

    **Basic Powershell Commands**
        Get-ChildItem -Recurse
        Set-Location        //change directories
        Get-Alias           //list aliases
        Update-Help         //download help files
        Get-Help <commandlet>

    **Execution Policy**
        Get-ExecutionPolicy -List
        Set-ExecutionPolicy Bypass

    **WMI**
        Get-WmiObject
            Get-WmiObject -class Win32_OperatingSystem | select...  //OS info
        Invoke-WmiMethod    //call methods of WMI objects
