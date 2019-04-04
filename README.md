# Tableau-Extension-ExportData

No matter how much you try to convince them, there will always be some users who want to reduce your beautiful Tableau charts to a table of numbers in Excel. So if they're going to do it anyway, you may as well give them a simple, controlled way, generating one Excel workbook and not a bunch of CSVs.

With the Export All extension for Tableau Server you can place a simple button onto your dashboard, choose which sheets & columns are exported, and with one click your users can download a clean & tidy Excel workbook.

The data can also be exported to a parent window using JavaScript postMessage function.
When the target is specified e.g. "parent.parent", export mode switches from Excel to PostMessage.
Four different message types are currently posted:
1. ${prefix}BEGIN   : Export button pressed
2. ${prefix}START   : Export of sheet is starting
3. ${prefix}DONE    : Export of sheet completed
4. ${prefix}END     : Export finished

PostMessage data fields:
type    : string            : one of the four messages tyes (BEGIN, START, DONE, END)
sheet   : string            : Tableau sheet name of the data, available on START and DONE message type
rows    : array of records  : Rows containing named tuples records
PostMessage type can be configured with a prefix and a target URL to increase security (default is "*").
