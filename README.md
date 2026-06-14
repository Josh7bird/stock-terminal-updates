# Stock Terminal Updates

This public repository hosts over-the-air firmware updates for the Bird Engineering Stock Terminal.

## Publish an update

1. Increase `FIRMWARE_VERSION` in `TerminalMay9.ino`.
2. Export the compiled ESP32 binary and rename the application image to `stock-terminal.bin`.
3. Calculate its MD5 checksum in PowerShell:

   ```powershell
   Get-FileHash .\stock-terminal.bin -Algorithm MD5
   ```

4. Create a GitHub release tagged with the same version, such as `v1.0.2`.
5. Attach `stock-terminal.bin` to the release.
6. Update `firmware_manifest.json` with the new version, MD5, and release notes.

The manifest URL used by the device is:

`https://raw.githubusercontent.com/Josh7bird/stock-terminal-updates/main/firmware_manifest.json`

Do not publish a newer manifest version until its matching release binary is attached and its MD5 is correct.
