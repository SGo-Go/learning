# Antiviruses

## Recommendations

### Linux

FOSS:
- scanners:
  [ClamAV](https://en.wikipedia.org/wiki/ClamAV)
  [^top-free-Linux] [^top-business-Linux]
- sandboxing:
  [Firetools](https://github.com/netblue30/firetools)

## ClamAV

- API:
  [nClam](https://github.com/tekmaven/nClam)
- GUI: 
  [ClamTk](https://en.wikipedia.org/wiki/ClamTk)
  [ClamWin](https://en.wikipedia.org/wiki/ClamWin_Free_Antivirus)
- [configuring](https://docs.clamav.net/manual/Usage/Configuration.html)
- installing
  <details><summary>Windows</summary>

  - on Windows [^medium:ClamAV-Win-install] [^youtube:ClamAV-Win-install]: 
    1. download [:inbox_tray:](https://www.clamav.net/downloads) and install `*.msi`
    2. configure the ClamAV

       ```sh
       cp .\clamd.conf.sample C:\ClamAV\clamd.conf
       cp .\freshclam.conf.sample C:\ClamAV\freshclam.conf
       ```
       fine tune [`C:\ClamAV\clamd.conf`](https://docs.clamav.net/manual/Usage/Configuration.html#clamdconf)
       - comment out `#Example`
       - uncomment `LogFile "C:\Program Files\ClamAV\clamd.log"`
       fine tune [`C:\ClamAV\freshclam.conf`](https://docs.clamav.net/manual/Usage/Configuration.html#freshclamconf)
       - comment out `#Example`
       - uncomment `UpdateLogFile "C:\Program Files\ClamAV\freshclam.log`
       - uncomment `DatabaseDirectory "C:\Program Files\ClamAV\database"`

    3. register ClamAV as a windows service

       ```sh
       clamd.exe --install
       ```
    
    4. update the [ClamAV Cirus Database (CVD)](https://docs.clamav.net/manual/Usage/SignatureManagement.html)
       (optional: [CVD private mirror](https://docs.clamav.net/appendix/CvdPrivateMirror.html))

       ```sh
       freshclam.exe
       ```

    5. run the ClamAV service (exec `services.msc` and start the ClamAV service)

  </details>
  <details><summary>Ubuntu</summary>

  - on [Ubuntu](http://www.ubuntuguide.org/wiki/Ubuntu_Feisty.html#Anti-virus) [^habr:ClamAV-nix-install]

  </details>

[^medium:ClamAV-Win-install]: ClamAV install on Windows [medium](https://medium.com/aeturnuminc/clamav-install-on-windows-5971358b2bc7)

[^youtube:ClamAV-Win-install]: How to setup ClamAV on Windows, initial setup for scanning [:play:](https://youtu.be/9gQXBUJbSHE?t=227)

[^habr:ClamAV-nix-install]: Антивирус для Linux – ClamAV https://habr.com/en/articles/654541/

[^top-free-Linux]: SafetyDetectives (2023) 5 Best (REALLY FREE) Antivirus Protection for Linux [web](https://www.safetydetectives.com/blog/best-really-free-antivirus-for-linux/)

[^top-business-Linux]: SafetyDetectives (2024) 3 Best Antiviruses for Linux in 2024 (Home + Business Options) [web](https://www.safetydetectives.com/best-antivirus/linux/)
