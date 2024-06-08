### Adding a "Download to CSV" button in a Browse Screen

1. Create a [Procedure](https://wiki.nubuilder.net/nubuilderforte/index.php/Procedures): Tab Builders -> Procedure -> Add

2. Code: BrowseDownloadToCSV

3. Give it a description. (E.g. Downloads data in a Browse Screen as a csv)

4. Paste the PHP code from the file [BrowseDownloadToCSV.php](BrowseDownloadToCSV.php) to the PHP field.

<p align="left">
  <img src="screenshots/BrowseDownloadToCSV.png">
</p>

5. Save

6. Add this JavaScript Code to your form’s *Custom Code*/ Browse field:

❓ [How to add Custom Code](/codelib/common/form_add_custom_code_javascript.gif)

```
function browseDownloadToCSV() {
    const fileDelimiter = ';';
    const fileName = 'browse_download.csv';

    nuRunPHPWithParams('BrowseDownloadToCSV', 'BrowseDownloadParams', {
        file_name: fileName, file_delimiter: fileDelimiter, sql: nuCurrentProperties().browse_sql
    });
}

nuAddActionButton('browseDownloadToCSV', 'Download to CSV', 'browseDownloadToCSV();');
```

7. Save

Now you see a new button "Download to CSV" in your Browse Screen!
