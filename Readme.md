<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128613902/14.1.7%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T163272)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
[![](https://img.shields.io/badge/💬_Leave_Feedback-feecdd?style=flat-square)](#does-this-example-address-your-development-requirementsobjectives)
<!-- default badges end -->

# Spreadsheet for WinForms - Replace Standard SpreadsheetControl Commands with Custom Commands

This example illustrates the technique used to modify the functionality of existing SpreadsheetControl commands.

## Implementation Details

The SpreadsheetControl exposes the [ISpreadsheetCommandFactoryService](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraSpreadsheet.Services.ISpreadsheetCommandFactoryService) interface that enables you to substitute the default command with your own custom command.

1. Create a custom command class, inherited from the command that you wish to replace. Override the required methods of the command.

2. Create a class inherited from the [SpreadsheetCommandFactoryServiceWrapper](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraSpreadsheet.Services.SpreadsheetCommandFactoryServiceWrapper), intended to substitute a default command service. In this class, override the [CreateCommand](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraSpreadsheet.Services.SpreadsheetCommandFactoryServiceWrapper.CreateCommand(DevExpress.XtraSpreadsheet.Commands.SpreadsheetCommandId)) method to create an instance of a custom command class, an identifier of the currently processed command is passed as a parameter of this method.

3. Use the `SpreadsheetCommandFactoryServiceWrapper` class descendant to substitute the default command service.

## Files to Review

* [CustomFormatClearContentsCommand.cs](./CS/SpreadsheetCustomCommand/CustomFormatClearContentsCommand.cs) (VB: [CustomFormatClearContentsCommand.vb](./VB/SpreadsheetCustomCommand/CustomFormatClearContentsCommand.vb))
* [CustomService.cs](./CS/SpreadsheetCustomCommand/CustomService.cs) (VB: [CustomService.vb](./VB/SpreadsheetCustomCommand/CustomService.vb))
* [Form1.cs](./CS/SpreadsheetCustomCommand/Form1.cs) (VB: [Form1.vb](./VB/SpreadsheetCustomCommand/Form1.vb))

## Documentation

* [How to: Replace Built-In Command with a Custom Command](https://docs.devexpress.com/WindowsForms/18004/controls-and-libraries/spreadsheet/examples/commands/how-to-replace-built-in-command-with-a-custom-command)
<!-- feedback -->
## Does this example address your development requirements/objectives?

[<img src="https://www.devexpress.com/support/examples/i/yes-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=winforms-spreadsheet-replace-standard-command-with-custom-command&~~~was_helpful=yes) [<img src="https://www.devexpress.com/support/examples/i/no-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=winforms-spreadsheet-replace-standard-command-with-custom-command&~~~was_helpful=no)

(you will be redirected to DevExpress.com to submit your response)
<!-- feedback end -->
