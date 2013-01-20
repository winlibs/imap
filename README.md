# cclient
All prebuilt libraries are available in the php-libs [repositories][1] 

The patched sources (only the makefiles) are available in the [source repository][2] 

The filename format is: 

cclient-x.y.z-vcversion-architecture.zip 

where x.y.z defines the version, vcversion which Visual C++ has been used and architecture defines whether the build is for win32 or win64. 

Only static library (cclient_a.lib) are available for now. 

## Requirements

*   imap-2007a Sources, fetch our [version][2] or the original [sources][3] 

*   Common tools used to compile PHP

## Preparing the sources

Simply uncompress the sources archives. 

## Configuration

Modify the file in imap-2007b\sc\osdep\ntmakefile.w2k, on line 39: 

    CCLIENTLIB = cclient_a.lib

srcipopdmakefile.w2k on line 29: 

    CCLIENTLIB = $C\cclient_a.lib

srcmailutilmakefile.w2k on line 29 

    CCLIENTLIB = $C\cclient_a.lib

srcmtestmakefile.w2k on line 29 

    CCLIENTLIB = $C\cclient_a.lib

No other special configuration required. Be sure to have the platform SDK in your path. 

## Compilation

### Release

The following command: 

    cd imap-2007b
    nmake /f makefile.w2k

will build the cclient.lib required to build php's imap extension.

 [1]: http://windows.php.net/downloads/php-sdk/ "http://windows.php.net/downloads/php-sdk/"
 [2]: https://github.com/winlibs "https://github.com/winlibs"
 [3]: ftp://ftp.cac.washington.edu/imap/ "ftp://ftp.cac.washington.edu/imap/"  



     

 
