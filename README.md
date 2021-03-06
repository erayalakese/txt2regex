## txt2regex — The console regular expression wizard

- Author: [Aurelio Jargas](http://aurelio.net/about.html)
- License: GPL
- First release: 2001-02-23
- Website: http://aurelio.net/projects/txt2regex/

Txt2regex is a Regular Expression Wizard that converts human sentences
to regexes. In a simple interactive console interface, the user answer
questions and the program build the regexes for more than 20 programs,
like Vim, Emacs, Perl, PHP, Python, Procmail and OpenOffice.org. It is
a Shell Script 100% written with Bash builtin commands. No compilation
or extra commands are needed, just download and run.


## Install and run

Txt2regex will work in ANY system bash works, because it's a bash-only
program. This includes Cygwin and Cygwin XFree also.

After expanding the tarball, simply run the program directly.
But if you want it installed on your system, or in other language besides
english, use the `make` command.

- **Just english:** untar and run
- **With i18n:** untar, make install and run

untar:

    tar xvzf txt2regex-VERSION.tgz
    cd txt2regex-VERSION

run:

    ./txt2regex.sh

make install (as root, system install):

    make install
    /usr/bin/txt2regex

make install (as user, local install):

    make install BINDIR=. LOCALEDIR=po
    ./txt2regex

**Note 1:** Play with BINDIR, LOCALEDIR and DESTDIR variables to
change the default install paths.

**Note 2:** Txt2regex only works in Bash version >= 2.04.


## Tested programs versions 

All regexes and rules the program knows about were extensively tested
by hand or by the test-suite program. When the program can't be
reached or executed on my machine, the rules were taken:

- From the program documentation
- Or missing it, from the "Mastering Regular Expressions" O'Reilly book
- Or missing it, from Internet documents (Oh no!)

Programs I've tested here:

- **ed**: GNU ed version 0.2
- **mawk**: mawk 1.3.3 Nov 1996
- **gawk**: GNU Awk 3.0.6
- **grep**: grep (GNU grep) 2.4.2
- **egrep**: egrep (GNU grep) 2.4.2
- **find**: GNU find version 4.1
- **javascript**: netscape-4.77
- **mysql**: Ver 11.13 Distrib 3.23.36
- **ooo**: OpenOffice.org 1.1.0
- **perl**: v5.6.0 built for i386-linux
- **php**: 4.0.6
- **postgres**: psql (PostgreSQL) 7.1.2
- **procmail**: procmail v3.15.1 2001/01/08
- **python**: Python 2.1
- **sed**: GNU sed version 3.02.80
- **tcl**: 8.3
- **vi**: Nvi 1.79 (10/23/96)
- **vim**: VIM - Vi IMproved 5.8 (2001 May 31)


## Translations maintainers

"I feel like I could... Like I could... TAKE OVER THE WORLD"

    ca             catalan           Carles (ChAoS)
    de_DE          german            Jan Parthey
    en             english           Aurelio Jargas
    es_ES          spanish           Diego Moya
    fr_FR          french            wwp
    id_ID     bahasa indonesian      Muhamad Faizal
    it_IT          italian           Daniele Pizzolli
    ja            japanese           Hajime Dei
    pl_PL          polish            Chris Piechowicz
    pt_BR    brazilian portuguese    Aurelio Jargas
    ro_RO         romanian           Robert Claudiu Gheorghe

A nice way to contribute with the project, is to translate its
messages to your own language. Just get the `po/txt2regex.pot`
file and translate it, on the `msgstr` lines. In doubt, ask.


## FAQ 

### Q: Why?

A: To try to make simple regexes less painful for the beginners.

A: To have a reliable source for regexes differences between programs.

A: To have coding fun &:)

### Q: Why bash2?

A: Basically, for me to learn the new bash2 concepts as arrays, i18n
and advanced variable expansion. They rule!

### Q: My screen has more than 25 lines, I'm serious!
### Q: Why it only uses 80 columns if my screen has more?
### Q: I've changed the xterm window size, why it didn't notice that?

A: The program do use the bash environment variables `$LINES` and
`$COLUMNS` to get the actual screen size. Those **MUST** be exported
variables, or you'll be stuck at the default 80x25 size. Try:

    /bin/bash -c 'echo $COLUMNS $LINES'

If you don't get the screen size, do:

    echo export COLUMNS LINES >> ~/.bash_profile

### Q: Why my bash version is not recognized correctly?
### Q: Here bash --version is >=2.04. Why the program gets other?

A: To find your bash version, the program uses the `$BASH_VERSION`
environment variable that is available in all bash versions.

If some alien has possessed your machine and your environment
don't have this variable, try to set it by hand. Check with

    echo $BASH_VERSION

If this variable is ok, but `bash --version` returns other
version, check if your bash is really /bin/bash:

    which bash

If it's not `/bin/bash`, you **MUST** change the first line
of the script to your bash's right path. Suppose you have the
bash binary in your `$HOME` because the system's bash is old,
just change the first line of the program to:

    #!/home/YOU/bin/bash

Or if you cannot change the program file, call it with bash:

    bash ./txt2regex

Sux, but worx.

### Q: What is that <TAB> that appears when I choose TAB on the special combination menu?
	
A: Inside lists [], the <TAB> string is a visual representation of
a literal TAB character, for programs which doesn't support [\t].

--

The End.
