<h1>Update a file through a Python algorithm</h1>

<h2>Project Description</h2>
At my organization, access to restricted resources is managed through an allow list of approved IP addresses stored in the allow_list.txt file. A separate remove list identifies IP addresses that should no longer be authorized. I developed a Python algorithm to automate the process of updating the allow list by removing unauthorized IP addresses.
<br />

<h2>Opening the Allow List File</h2>

The first step in the algorithm was opening the allow_list.txt file for processing. I stored the file name as a string in the variable import_file and used a with statement to open the file in read mode.

<p align="left">
<img src="https://i.imgur.com/6YTAW90.png" height="80%" width="80%" alt="Opening the Allow List File"/>
<br />
<p align="left">
<img src="https://i.imgur.com/hBIg2za.png" height="80%" width="80%" alt="Using 'with' statement to open the file"/>
<br />

Using with open(import_file, "r") as file: allowed the program to safely access the file contents while ensuring the file was automatically closed once processing was complete. The "r" argument specified that the file was opened for reading, and the file variable stored the file object during execution.


<h2>Reading the File Contents</h2>

To access the IP addresses, I used the .read() method within the with statement to read the contents of the file and convert them into a string. The resulting string was stored in the variable ip_addresses.

Reading the file in this format allowed the data to be easily manipulated later in the program.

<p align="left">
<img src="https://i.imgur.com/v4osmIs.png" height="80%" width="80%" alt="Reading the File Contents"/>
<br />

<h2>Converting the String to a List</h2>

To remove individual IP addresses, the data needed to be converted from a string to a list. I used the .split() method to separate the IP addresses based on whitespace and store them as individual elements in a list.

The resulting list was reassigned to the variable ip_addresses, making it easier to modify the allow list.

<p align="left">
<img src="https://i.imgur.com/FcLI8ku.png" height="80%" width="80%" alt="Converting the String to a List"/>
<br />

<h2>Iterating Through the Remove List</h2>

A core component of the algorithm involved looping through each IP address in the remove_list. I implemented a for loop to evaluate each element individually.

The loop allowed the algorithm to apply the same logic to every IP address in the remove list.

<p align="left">
<img src="https://i.imgur.com/WQz7d7r.png" height="80%" width="80%" alt="Iterating Through the Remove List"/>
<br />

<h2>Removing Unauthorized IP Addresses</h2>

Within the loop, I used a conditional statement to check whether the current IP address existed in the ip_addresses list. This prevented errors that could occur if .remove() was applied to a non-existent element.

If the IP address was present, I used the .remove() method to delete it from the allow list.

<p align="left">
<img src="https://i.imgur.com/PkRXQZj.png" height="80%" width="80%" alt="Removing Unauthorized IP Addresses"/>
<br />
  
<h2>Updating the Allow List File</h2>

After removing the unauthorized IP addresses, I converted the updated list back into a string using the .join() method. I used "\n" as the separator so that each IP address would appear on a new line in the file.

<p align="left">
<img src="https://i.imgur.com/9G3nGvc.png" height="80%" width="80%" alt="Updating the Allow List File"/>
<br />
  
I then reopened allow_list.txt using a second with statement in write mode ("w") and used the .write() method to overwrite the file with the revised list. Opening the file in write mode ensured that the previous contents were replaced with the updated data.

<p align="left">
<img src="https://i.imgur.com/sKq6CkM.png" height="80%" width="80%" alt="Updating the Allow List File"/>
<br />

<h2>Summary</h2>

In this task, I developed a Python algorithm to automate the maintenance of an IP allow list by removing addresses identified in a remove list. The process involved reading the file contents, converting the data between string and list formats, iterating through unauthorized IP addresses, and writing the updated allow list back to the file. This approach ensured that access to restricted resources remained properly controlled.
