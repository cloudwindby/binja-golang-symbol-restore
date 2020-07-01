# Golang Symbol Restore (v1.1) 
Author: **Daniel Weber,cloudwindby**

_Binary Ninja plugin for restoring function names from stripped Golang binaries._
## Description:
The plugin parses the section `.gopclntab` where Golang stores debug symbols and restores 
the function names. If there is no section named `.gopclntab` it will try to search for the section.

## Minimum Version

This plugin requires the following minimum version of Binary Ninja:

 *  2.0.2097


## Required Dependencies

The following dependencies are required for this plugin:

 * Python3


## License

This plugin is released under a MIT license.
## Metadata Version

2

## 修改信息

Daniel Weber的1.0版本对于没有gopclntab section的程序，会去搜索别的section，但是搜索的时候只会匹配section头部的hex，golang的符号信息是可以不在section的头部的。所以我对其进行了修改。可以搜索整个bin的hex来匹配符号信息，然后对其进行恢复。不过只测试了windows下的pe程序。别的平台未做测试。