Not My Type

When our file approached his crush, he got heartbroken. "I told you during the Induction CTF 2019, that you are not my type. But now you look feverish! Do you have the virus?". Can you have a look at our file? It used to excel.

File: Our_file_-_Copy.docx

Writeup:
Running the file command on the given file tell that it is a zip file and not a docx file.
Changing the extension to .zip and unzipping gives three folders _rels/, xl/, docProps/

The flag is inside the file sharedStrings.xml inside the folder xl/

TECHWKND{3asy_fLaG}