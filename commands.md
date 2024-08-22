# Commands used in __Learning Linux Command Line__ from LinkedIn Learning

## 01_01 - Creating a Linux virtual machine

`sudo apt install gcc make perl`

## 02_03 - Write commands in a shell at the prompt

`ls`

`ls -l`

`ls`

`list` (invalid command)

`jhsdgjhksad` (invalid command)

## 02_04 - Finding help for commands

`man ls`

`ls --help`

`apropos list`

## 02_05 - Helpful keyboard shortcuts in the terminal

`ls -l De` followed by the Tab key

`ls -l Do` followed by the Tab key twice

`ls -l Doc` followed by the Tab key

`a` followed by the Tab key

`clear` (used throughout the course)

## 03_01 - The Linux file system

`ls -l`

`file Documents`

`stat Documents`

![image](https://github.com/user-attachments/assets/d740ec04-6abe-4173-940f-9332cadb97d3)

## 03_03 - Navigating the file system

![image](https://github.com/user-attachments/assets/3c68d3f6-6107-4c6d-bbaf-50fd79fe37bf)

![image](https://github.com/user-attachments/assets/1908e66e-fb9e-4c76-9890-23c33931d78d)


`cd Documents/`

`pwd`

`cd Exercise Files` (invalid command)

`cd Exercise\ Files`

![image](https://github.com/user-attachments/assets/b5de8012-ca70-4635-9b82-bbf9e8ad9655)

`pwd`

`ls`

`ls -R departments/`

`cd departments/hr/policies`

`cd ..`

`cd ..`

`cd hr/policies`

`cd ../../finance/documents`

`cd -`

`cd`

![image](https://github.com/user-attachments/assets/a8ef88cd-4af0-4c21-8068-7974e23be27d)


## 03_04 - Exploring the output of the ls command

`ls`

`ls --color=always`

`cd Documents/Exercise\ Files`

`ls -l`

`ls -lh`

## 03_05 - Create and remove directories

`mkdir newfolder`

`ls -l`

`mkdir departments/customerservice`

`mkdir departments/customerservice/documents departments/customerservice/cases departments/customerservice/awards`

`mkdir -p departments/legal/contracts`

`rmdir departments/legal/contracts/`

`rmdir departments/legal/`

`rmdir departments/customerservice`

## 03_06 - Copy, move, and delete files and directories

`cp poems.txt poems2.txt`

`cp simple_data.txt departments/hr/employee\ info/`

`mv poems2.txt departments/marketing`

`mv departments/marketing/poems2.txt departments/marketing/literature.txt` - moves and renames at the same time. 

`ls departments/marketing/`

`mv departments/marketing/literature.txt .`

`mv *.txt departments/marketing/` - copies all text files from current directory to marketing folder

`mv departments/marketing/* .`

![image](https://github.com/user-attachments/assets/05c68804-61fb-4c18-a718-12200984ce3b)

`ls`
`rm literature.txt` - Delete single file only 
`rm poems?.txt` - deletes all files after poems and have another character after that
`rm departments/customerservice/` - Error that customerservice is a directory
`rm -r departments/customerservice/` - Will recursivly delete files 

## 03_07 - Find files from the command line

`find . -name "poe*"`

`find . -name "do*"`

`find . -name "d*"`

`find . -name "*d*"`

`find ~/Documents -name "*d*"`

![image](https://github.com/user-attachments/assets/84a34190-e1ed-4312-b6c7-41b43b67693f)

## 03_08 - Understand user roles and sudo

`ls /root`

`sudo ls /root`

`sudo -k` - Removed sudo access (logout)

`sudo -s`

`exit`

## 03_10 - Modify file permissions

`ls`

`./test.sh`

`ls -l test.sh`

`stat test.sh`

`chmod 644 test.sh` followed by Ctrl+C

`chmod -x test.sh`

`./test.sh`

`bash test.sh`

`cat test.sh`

`chmod u-r test.sh`

`chmod 244 test.sh` followed by Ctrl+C

`cat test.sh`

`chmod 755 test.sh`

`./test.sh`

`cat test.sh`

`touch newfile`

`stat newfile`

`ls -l`

`nano test.sh`

`sudo chown root test.sh`

`nano test.sh`

`ls -l test.sh`

`sudo chown [username] test.sh` (replace `[username]` with your user name)

## 03_11 - Create hard and symbolic links

`ln -s poems.txt writing.txt`

`ls -l`

`cat writing.txt`

`ln poems.txt words.txt`

`ls -l`

## 04_02 - Use pipes to connect commands together

`echo "Hello"`

`echo "Hello" | wc`

`echo "Hello world from the command line" | wc`

## 04_03 - View text files with cat, head, tail, and less

`cat poems.txt`

`head poems.txt`

`head -n5 poems.txt`

`tail -n3 poems.txt`

`cat poems.txt | cat -n | tail -n5`

`cat poems.txt | tail -n5 | cat -n`

`less poems.txt`

`cat poems.txt | less`

## 04_04 - Search for text in files and streams with grep

`grep "the" poems.txt`

`grep -n "the" poems.txt`

`grep -n "The" poems.txt`

`grep -in "The" poems.txt`

`grep -vi "the" poems.txt``grep -E "\w{6.}" poems.txt`

## 04_05 - Manipulate text with awk, sed, and sort

`cat simple_data.txt`

`awk '{print $2}' simple_data.txt`

`awk '{print $2 "\t" $1}' simple_data.txt`

`awk '{print $2 "\t" $1}' simple_data.txt | sort -n`

`cat simple_data.txt`

`sort simple_data.txt`

`sort -k2 simple_data.txt`

`cat dupes.txt`

`sort -u dupes.txt`

## 04_06 - Edit text with Vim

`vi`

`vi poems.txt`

## 04_07 - Edit text with nano

`nano`

`nano poems.txt`

## 04_08 - Working with tar and zip archives

`cd ..`

`tar -cvf myfiles.tar Exercise\ Files/`

`ls -l`

`tar -caf myfiles.tar.gz Exercise\ Files/`

`tar -caf myfiles.tar.bz2 Exercise\ Files/`

`ls -lh`

`mkdir unpack1`

`mv myfiles.tar.bz2 unpack1/`

`cd unpack1/`

`tar -xf myfiles.tar.bz2`

`ls -l`

`cd Exercise\ Files`

`ls`

`cd ~/Documents/`

`mkdir unpack2`

`tar -xf myfiles.tar.gz -C unpack2`

`ls unpack2`

`zip -r exfiles.zip Exercise\ Files/`

`ls -lh`

`mkdir unpack3`

`mv exfiles.zip unpack3`

`cd unpack3`

`unzip exfiles.zip`

`ls -l`

`cd ..`

`mkdir unpack4`

`unzip unpack3/exfiles.zip -d unpack4`

`ls -l unpack4`

## 04_11 - Output redirection

`cd Exercise\ Files`

`ls`

`ls 1> filelist.txt`

`cat filelist.txt`

`ls > filelist2.txt`

`cat filelist2.txt`

`ls notreal`

`ls notreal > filelist3.txt`

`ls notreal 2> filelist4.txt`

`cat filelist4.txt`

`>filelist4.txt`

`cat filelist4.txt`

`ls > filelist5.txt`

`echo "some appended text" >> filelist5.txt`

`cat filelist5.txt`

## 04_12 - Exploring environment variables and PATH

`env`

`echo $PATH`

`which ls`

`which less`

`ls -a`

`nano ~/.bash_profile`

## 05_01 - Find information about your Linux distribution

`ls -l /etc/*release`

`cat /etc/lsb-release`

`cat /etc/os-release`

`cat /etc/*release`

`uname -a`

`uname -r`

## 05_02 - Find system hardware and disk information

`free -h`

`cat /proc/cpuinfo`

`lscpu`

`df -h`

`sudo du -hd1 /`

`sudo lshw | less`

`ip a`

## 05_03 - Install and update software with a package manager

`apt search tree`

`apt show tree`

`tree`

`sudo apt update`

`sudo apt install tree`

`tree`

`man tree`

`sudo apt update`

`sudo apt upgrade`
