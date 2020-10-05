Not My Type II

In an alternate universe, our file is the her type! Can you cure it fafa?

File: Our_File.jpg

Writeup:
The jpg file does not open. Looking at the hexdump of the file, it is clear that the file header has been messed up with. 
On rewriting the header with the normal JPG header [https://en.wikipedia.org/wiki/List_of_file_signatures], the picture opens normally and we get the flag.
You can use any coommand line tools like hexedit to edit the hexdump of the file.

TECHWKND{!50_3asy_fLaG}