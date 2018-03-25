
该demo是参照[[使用 GNU autotools 改造一个软件项目]](http://www.cppblog.com/liu1061/articles/54740.html)而来。

注意，每次修改了 configure.ac 或 Makefile.am 等 autotools 输入文件后都需要再次运行aclocal, automake,  autoconf 这些命令，为了方便起见，可以将他们放到一个 shell脚本里面，例如:
```shell
#! /bin/sh
set -x
aclocal
autoheader
automake --foreign --add-missing
autoconf
```

- step1: 得到configure.scan 并将它改名为configure.ac
```shell
tu_xu@desktop- MINGW64 ~/algorithm
$ autoscan
```

- step2: 编辑configure.ac


- step3: 手工创建Makefile.am

	 创建根目录以及目录下的Makefile.am

- step4: 执行aclocal

		```text
		tu_xu@desktop- MINGW64 ~/algorithm
		$ ls
		autoscan.log  configure.ac  Makefile.am  readme.md  src

		tu_xu@desktop- MINGW64 ~/algorithm
		$ aclocal

		tu_xu@desktop- MINGW64 ~/algorithm
		$ ls
		aclocal.m4  autom4te.cache  autoscan.log  configure.ac  Makefile.am  readme.md  src

		tu_xu@desktop- MINGW64 ~/algorithm
		$
		```

- step5:  执行autoheader

		```text
		tu_xu@desktop- MINGW64 ~/algorithm
		$ autoheader

		tu_xu@desktop- MINGW64 ~/algorithm
		$ ls
		aclocal.m4  autom4te.cache  autoscan.log  config.h.in  configure.ac  Makefile.am  readme.md  src

		```

- step6: 执行automake

		```text
		$ automake --foreign --add-missing
		configure.ac:11: installing './compile'
		configure.ac:24: installing './install-sh'
		configure.ac:24: installing './missing'
		src/bubbleSort/Makefile.am: installing './depcomp'

		tu_xu@desktop- MINGW64 ~/algorithm
		$ ls
		aclocal.m4  autom4te.cache  autoscan.log  compile  config.h.in  configure.ac  depcomp  install-sh  Makefile.am  Makefile.in  missing  readme.md  src

		tu_xu@desktop- MINGW64 ~/algorithm
		$

		```
- step7: 执行autoconf
		```text
		tu_xu@desktop-▒▒▒▒ MINGW64 ~/algorithm
		$ autoconf

		tu_xu@desktop-▒▒▒▒ MINGW64 ~/algorithm
		$ ls
		aclocal.m4  autom4te.cache  autoscan.log  compile  config.h.in  configure  configure.ac  depcomp  install-sh  Makefile.am  Makefile.in  missing  readme.md  src
		```
- step8: 执行 .\configure		