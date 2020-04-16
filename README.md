[![Build Status](https://travis-ci.org/Funz/plugin-Cmd.exe.png)](https://travis-ci.org/Funz/plugin-Cmd.exe)

# Funz plugin: Cmd.exe

This plugin is dedicated to launch Cmd.exe calculations from Funz.
It supports the following syntax and features:

  * Input
    * file type supported: *.bat, any other format for resources
    * parameter syntax: 
      * variable syntax: `$(...)`
      * formula syntax: `&{...}`
      * comment char: `REM`
    * example input file:
        ```
        @echo off

        ... $(x1~[1,2]) ... 
        
        ... &{$x2 + 1.23 | #.###} ...

        echo z=$z
        ```
      * will identify input:
        * x1, expected to vary inside [1,2]
        * x2
      * replace `&{%x2 + 1.23 | #.###}` expression by its evaluation

  * Output
    * file type supported: *.out (contains output stream)
    * read any named value printed with '=', like `echo z=...`
    * example output file:
        ```
        z=4.5
        ```
        * will return output:
          * z=4.5 



![Analytics](https://ga-beacon.appspot.com/UA-109580-20/plugin-Cmd.exe)
