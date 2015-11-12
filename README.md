# find_and_replace_in_files.sh
This script does a recursive, case sensitive directory search and replace of files to make a case insensitive search replace, use the -i switch in the grep call uses a startdirectory parameter so that you can run it outside of specified directory - else this script will modify itself!


Alternative strings

Here I use sed to replace every occurrence of the word "cybernetnews" with "cybernet" in every file with the extension, c, in the directory, /home/user/directory/.

find /home/user/directory -name \*.c -exec sed -i "s/cybernetnews/cybernet/g" {} \;

Or a more generic variation where you search recursively from the directory of execution and operate on only regular, readable, writeable files:	

find ./ -type f -readable -writable -exec sed -i "s/cybernetnews/cybernet/g" {} \;

