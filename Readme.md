<!-- default file list -->
*Files to look at*:

* [CustomFormatClearContentsCommand.cs](./CS/SpreadsheetCustomCommand/CustomFormatClearContentsCommand.cs) (VB: [CustomFormatClearContentsCommand.vb](./VB/SpreadsheetCustomCommand/CustomFormatClearContentsCommand.vb))
* [CustomService.cs](./CS/SpreadsheetCustomCommand/CustomService.cs) (VB: [CustomService.vb](./VB/SpreadsheetCustomCommand/CustomService.vb))
* [Form1.cs](./CS/SpreadsheetCustomCommand/Form1.cs) (VB: [Form1.vb](./VB/SpreadsheetCustomCommand/Form1.vb))
<!-- default file list end -->
# How to replace standard SpreadsheetControl command with your own custom command


<p>This example illustrates the technique used to modify the functionality of existing SpreadsheetControl commands.<br />The SpreadsheetControl exposes the ISpreadsheetCommandFactoryService interface that enables you to substitute the default command with your own custom command. <br /><br />First, create a custom command class, inherited from the command that you wish to replace. Override the required methods of the command. Then, create a class inherited from the SpreadsheetCommandFactoryServiceWrapper, intended to substitute a default command service. In this class, you need to override the CreateCommand method to create an instance of a custom command class, an identifier of the currently processed command is passed as a parameter of this method. <br /><br />Finally, use the SpreadsheetCommandFactoryServiceWrapper class descendant to substitute the default command service.<br /><br />In this case, instead of the default command, the command you implemented will be used by the SpreadsheetControl.</p>

<br/>


