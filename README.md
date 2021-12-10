# Cheat Sheets

`CheatSheet.html` is a mini-infrastructure for hosting cheat sheets.

It's basically a minimalistic HTML page which pulls its content from a public Google Sheets spreadsheet (or from a static JSON file).

Cheat sheets currently available:

 * [Git Cheat Sheet](https://dvd848.github.io/Cheat-Sheets/CheatSheet.html?subject=Git)

## Customization

In order to use this infrastructure for your own cheat sheets:

 1. Create a new Google Drive Spreadsheet
 2. Add the following columns as a header: `Category, Subcategory, Weight, Is Starred?, Command, Description, More Info, Output`
 3. Change the spreadsheet permissions so that it has public Read-Only permissions
 4. Modify `SPREADSHEET_ID` in `CheatSheet.html` to point to your spreadsheet ID
 5. Modify the table of contents under `setupCheatSheet` to include the spreadsheet name (and any information that should appear in the footer)

At this point, there are two options to access the spreadsheet content:
 
 1. Using a Google Spreadsheet API Key:
    1. Create an API Key using the instructions [here](https://developers.google.com/sheets/api/guides/authorizing)
    2. Append the API Key to the request, e.g. `CheatSheet.html?google_api_key=<API_KEY>`
 2. Using a static JSON file:
    1. Access the spreadsheet via `https://sheets.googleapis.com/v4/spreadsheets/<SPREADSHEET_ID>/values/<SPREADSHEET_NAME>?key=<API_KEY>`
    2. Save the resulting JSON file to the same directory as `CheatSheet.html`

See [this StackOverflow Question](https://stackoverflow.com/questions/30082277/accessing-a-new-style-public-google-sheet-as-json) for more information about accessing Google Spreadsheets as JSON files.
