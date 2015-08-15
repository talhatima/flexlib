# Introduction #

The following steps will guide you in checking out the source code for this project and using it in a new FlexBuilder library project.

# Details #

In order to work with Subversion in FlexBuilder, you must have a Subversion plugin installed.  I use [Subclipse](http://subclipse.tigris.org/).

## Project Members ##

If you are a project member with write access to the repository, you must follow Google Code's instructions on checking out the project with your username.  See [Command-Line Access](http://code.google.com/p/flexlib/source).

Once you've run the "svn checkout", create a new Flex Library Project
  * Use "flexlib" as the project name
  * Create the project in the folder that you checked out the svn contents to, such as C:\Development\flexlib
  * When you click Finish, FlexBuilder will create a library project with the initial code present from the "svn checkout" step.

After completing the step, jump down to "Configure the project...".

## Read-Only Access ##

Follow the steps below to create a project with read-only access.

### Add an SVN Repository location for this project ###

  * In the Window menu, select Show View -> Other
  * Expand SVN and select SVN Repository, then click OK
  * Right click in the SVN Repository view and select New -> Repository location...
  * Enter the SVN Repository for this project: http://flexlib.googlecode.com/svn/trunk/
  * Click Finish

### Check out the code from the project into the Flex Library Project ###

  * Right click on the repository location you added in the previous step, and select Checkout...
  * Select "Check out as a project configured using the New Project Wizard" and click Finish
  * Expand the Flex folder, select Flex Library Project, and click Next
  * Name the project after this library (in this case, flexlin), and select the directory where the source code will be placed (or, you can just use the default directory there, under the current workspace).  Click Finish.

## Configure the project to include the proper classes in the .swc output file ##

After the code is checked out from the previous step, you need to modify the project so that it knows what classes to include in the output .swc file.

  * Right click on the project that you just created in FlexBuilder and select Properties
  * Select Flex Library Build Path
  * In the "Main Source Folder" field, type in "src"
  * Under the Classes tab, select the "src" folder to include everything.  Alternatively, you can pick and choose what classes you want.
  * Click OK

## Configure the project to build against Flex3 or Flex4 ##
After the code is checked out from the previous step, you need to modify the project so that it knows whether it should build against Flex3 or Flex4.
  * Right click on the project that you just created in FlexBuilder and select Properties
  * Select Flex Library Compiler
  * Update Addition Flex Compiler arguments box with one of:
    * Flex3 (default): -define+=FLEX\_TARGET\_VERSION::flex4,false -define+=FLEX\_TARGET\_VERSION::flex3,true
    * Flex4: -define+=FLEX\_TARGET\_VERSION::flex4,true -define+=FLEX\_TARGET\_VERSION::flex3,false
  * Click OK.

When the dialog closes, the project will be built and you'll have the projects .swc file placed in the default "bin" output directory.

## Updating the project code ##

To get the latest code from SVN, right click on the project, and select Team -> Update

## Working with the project ##

See HowToBuild for information about building the examples, running the unit tests, or creating asdoc documentation.