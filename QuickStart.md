# Note #

This is just a quick outline.  We'll make this page more descriptive with screenshots when we get a chance!

# Using FlexLib #

If you don't have Flex 2.0.1 yet, you must [download that first](http://www.adobe.com/products/flex/).  FlexLib **requires** Flex 2.0.1.

Download the latest version of the flexlib.swc from the [download page](http://code.google.com/p/flexlib/downloads/list).

Create a new Flex project in FlexBuilder.

In your Flex project, create a _lib_ directory.

Extract the flexlib.swc file from the .zip, and place it in the _lib_ directory.

Right click on the project name in the project Navigator, and select Properties.

Select "Flex Build Path" on the left.

Select the "Library Path" tab.

Click the "Add SWC Folder" button.

Type in "lib", press "OK"

Press "OK" to commit your changes.

FlexLib is now available for your project to use.  To use the FlexLib components, you need to use the proper XML Namespace:  xmlns:flexlib="http://code.google.com/p/flexlib/"

Once the _flexlib_ name space is added in your MXML file, you can use any of the flexlib controls, like: <flexlib:TreeGrid ... />
