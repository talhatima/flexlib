# Introduction #
Everyone is encouraged to contribute Flex components they have developed. The FlexLib project is meant to be an inclusive community project. That said, we want to make sure that the components included in the FlexLib library are high quality and follow good coding practices.

# License #
All code submitted to FlexLib must be released under the MIT license. All code must have the standard version of the FlexLib MIT license block added to each source file (see any of the current source files in the SVN repository). Any original classes from Adobe or Macromedia should retain the original licensing block contained in those files.

Here's the license block:
```
/*
Copyright (c) 2007 FlexLib Contributors.  See:
    http://code.google.com/p/flexlib/wiki/ProjectContributors

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
*/
```

# Before you submit code #
Please make sure you become familiar with the current FlexLib codebase. You should check out the latest version of FlexLib from the SVN repository. Follow the instructions on the FlexBuilderProject page to learn how to check out the project into Flex Builder. Read HowToBuild to learn how to compile the source files.

Make sure you are comfortable with checking out the source code and building the project. It's not too hard, and if you're not already familiar with using SVN and Ant within Eclipse then now is a great chance to learn.

# To submit your components #
If this is your first contribution to FlexLib then you do not have the ability to commit changes to the SVN repository. Contact one of the project administrators, this is either Darron Schall or Doug McCune by posting a message to the [FlexLib Discussion Group](http://groups.google.com/group/flexlib). Please either send along the code you want to add to flexlib, or links to the source code available on the web.

Once your contribution is submitted we'll review it to make sure it's up to the standards of the FlexLib project. This isn't meant to scare away developers, we welcome **all** contributions, but we want to make sure we keep the quality of the project high. Assuming you've submitted awesome code, we'll integrate it with FlexLib and provide you with SVN access, so in the future you can commit your own code to the project.

# Pure Actionscript vs. MXML #
Ideally all components included in FlexLib will be pure Actionscript 3.0 classes, not MXML classes. Anything you can do with an MXML class you can do with pure Actionscript. If you have some components you've developed in MXML we'll still incorporate them into FlexLib, with the intention of eventually reworking them as pure AS classes.

# ASDoc Documentation #
We use ASDoc to generate the documentation for FlexLib. Documentation style should be consistent with the format of the documentation throughout the Flex SDK framework classes. Obviously the level of source code documentation will vary from contributor to contributor, but we hope you'll take the time to provide comprehensive documentation in your code.

For more on ASDoc and how to format your comments, see [Using ASDoc](http://livedocs.adobe.com/flex/201/html/wwhelp/wwhimpl/common/html/wwhelp.htm?context=LiveDocs_Book_Parts&file=asdoc_127_1.html) on LiveDocs.

# Examples #
Each component (or set of related components) should have an associated example MXML application. This application should be a standalone Flex application that demonstrates the functionality of the component. The MXML file (and any associated resource files) should go in a subdirectory of the src/examples/ directory. See the current  [examples directory](http://flexlib.googlecode.com/svn/trunk/examples/).

These examples get compiled by the Ant build script. The Ant build target responsible for compiling the examples is called "examples" in the build.xml file. This build target loops over any MXML files that are named `*_`Sample.mxml under the src/examples/ directory and compiles each one into a SWF. Note that you should include the MIT licensing block in the example MXML file as well.

Your example should be simple, but it should also demonstrate the functionality of the component. Here's the example MXML file for the PromptingTextInput component:
```
<mx:Application xmlns:mx="http://www.adobe.com/2006/mxml" 
	xmlns:flexlib="http://code.google.com/p/flexlib/"
	layout="vertical">
	
	<mx:Panel title="PromptingTextInput Sample">
		<mx:Form>
			<mx:FormItem label="Name:">
				<mx:TextInput id="fullName" />
			</mx:FormItem>
			
			<mx:FormItem label="Address:" direction="vertical">
				<flexlib:PromptingTextInput id="address1" prompt="Address 1" />
				<flexlib:PromptingTextInput id="address2" prompt="Address 2" />			
				<mx:HBox>
					<flexlib:PromptingTextInput id="city" prompt="City"  width="129"/>
					<flexlib:PromptingTextInput id="state" prompt="State"  width="50"/>
					<flexlib:PromptingTextInput id="zip" prompt="Zip"  width="77"/>
				</mx:HBox>
			</mx:FormItem>		
		</mx:Form>

		<mx:ControlBar horizontalAlign="right">
			<mx:Button id="submit" label="Submit" />
		</mx:ControlBar>
	</mx:Panel>
</mx:Application>
```






