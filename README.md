# asm_helpers

## get_real_device

    get_real_device [-d] [-S] <file>

      -d            - include last dm- device
      -S            - exclude sd devices
      <file>        - device-file (or symlink to device) to be evaluated

    get_real_device tries to identify the underlying device(s) of a given dm-
    device (or a symlink pointing to it). This can be used to determinate
    multipath configuration without root (or sudo)
    if <file> is not a proper multipath-device, <file> is returned

##asmstat

inspired by [Bart Sjerps](https://twitter.com/CacheFlush)' [asmstat](https://github.com/outrunnl/asmdisks), but it gets the ASM-diskname and devicename from asmcmd.

    asmstat [-?] [-e] [-f] [-o] <iostat parameters>

      -?            - this page
      -e            - exclude disks which does not belong to ASM
      -f            - show full ASM diskname (do not truncate)
      -o            - show ASM diskname only (no device)

    asmstat is a wrapper for iostat in ASM setup.
    It replaces all sdxx devices by a combination of ASM-diskname and the device.
    All parameters are directly passed to iostat.
    Proper ORACLE_HOME $ ORACLE_SID must be set for an ASM instance and
    the binary asmcmd must be in the PATH.

	