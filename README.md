# ismkey_DD_FILESPEC<br />
**Created Date:** 1/10/2017<br />
**Last Updated:** 1/10/2017<br />
**Description:** This is a modified version of the ismkey CodeExchange entry. It includes a subroutine that uses DD_FILESPEC to generate a file specification from a Repository structure, and a test program to demonstrate how to use the subroutine.<br />
**Platforms:** Windows<br />
**Products:** Synergy DBL; Synergy DBMS; Repository<br />
**Minimum Version:** 10.3.3a<br />
**Author:** Tate Chamberlain
<hr>
<p><strong>Additional Information:</strong>
This project contains a subroutine that will generate the parameters
required to create an ISAM file based on a structure and file definition
in the Synergy/DE Repository. It also includes a test program that will
run the subroutine from the command line, with the name of the structure
as a command line argument.

This project is based on the earlier CodeExchange entry "ismkey.zip".
Some of the modifications include:
- Using DD_FILESPEC instead of DD_FILE to get the file specifications.
This demonstrates one way to use DD_FILESPEC, since there aren't
many examples.
- Support for both structures where the kref value is explicitely
defined for each key and structures where the value is implicit.
Provides an error message if a combination is attempted or if a
kref value other than 0 is drepeated.
- Removed code that relied on UI Toolkit.
- Program made more user friendly, accepting the structure name
as a command line argument instead of hard-coding it.
- Various other code improvements.
- Workbench project converted to Visual Studio Traditional Synergy
project.
Instructions
------------

To use the ismkey subroutine, inclue the ismkey.dbl source file in your
program.

To run the test program, open ismkey.sln in Visual Studio, and use Visual
Studio to build the program. Then run the program. It should create an
ISAM file in the 'dat' folder.

The program accepts the name of a Repository structure as a command line
argument, and creates a file based on the specs for the first file that
structure is assigned to.

The test program comes with a sample Repository file that contains a
single structure ("TESTSTRUCT"), which is assigned to the signle file
("DATADIR:FILETEST.ISM"). The Visual Studio project is set up to use that
Repository structure (all of the appropriate environment variables are set,
and the command line argument "teststruct" is provided on the Debug property
page), so all you have to do is run the program.

To run the test program with your own Repository, either modify the command
line argument in the project's properties or run the program from the
command line and give it the appropriate structure name. In either case,
make sure to set the environment variabls (e.g. RPSMFIL and RPSTFIL) to
point to the Repository you want to use.

When running from the command line, I would recommend running the program
with dbs instead of dbr to avoid the Synergy runtime window appearing for
a moment and disappearing again. Aside from that, it should run fine in
either dbs or dbr.

The Workbench project is also included in case you don't have Visual Studio
or you would simply prefer to build and run in Workbench instead of Visual
Studio.


This code example is intended to be used with Traditional Synergy on
Windows, but the code should be able to work on Unix, OpenVMS, and Synergy
.NET on Windows as well. Some modification may be necessary.
</p>
