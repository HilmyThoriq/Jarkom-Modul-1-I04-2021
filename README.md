# IUP 04
Salsabila Irbah 05111942000007 <br />
Muh Hilmy Thoriq YR 05111942000012 <br />
Nadhif Bhagawanta Hadiprayitno 05111942000029 <br />

# Problem 1
**What web server is used on "ichimarumaru.tech"!**

To answer the question is by inserting `http.host == ichimarumaru.tech` into the filter of captured packets after opening the 1-5 file. After that it will display the two below and by right-clicking the first one and clicking follow → http, it will display it.

![image](https://user-images.githubusercontent.com/81474281/134762821-1bf74468-8ba4-4d5c-83ef-6915dd2546be.png)

The filter results

![image](https://user-images.githubusercontent.com/81474281/134762841-2313df0a-dcca-475f-aab0-fa44fdbe7e00.png)

the result after follow http

the answer in the end would be Nginx Web Server

**Difficulties:**
- No difficulties

# Problem 2
**Find the packets from the web that use the basic authentication method!**

In This Problem, We need to find packets from the web that use basic authentication method. We simply use filter `http contains "basic"`
Next we can confirm the packets got basic authentication by seeing the details below

*here is the packets shown with filter `http contains "basic"`*
![basic 2](https://user-images.githubusercontent.com/81411468/134629045-381a549a-bb79-4f08-9b2a-c34aebfad269.PNG)

**Difficulties:**
- Using `http contains "basic"` may show packets that dont have basic authentication

# Problem 3
**Follow the instructions at basic.ichimarumaru.tech! Username and password can be obtained from the .pcapng file!**

In this problem we're using same filter `http contains "basic"` then in the detail box below we can find the arrow button that shows the Username and Password that used to login to `basic.ichimarumaru.tech`

*here is the username and password details*
![User password 3](https://user-images.githubusercontent.com/81411468/134629447-ca9afb89-439e-4e0a-a463-c3e738fdb767.PNG)

*here is the answer of basic.ichimarumaru.tech*
![3](https://user-images.githubusercontent.com/81411468/134629458-37d84c25-8e2b-421e-a63a-99ad63411ac7.PNG)

**Difficulties**
- Strunggling find the username and password

# Problem 4
**Find the mysql packets that contain the select query command!**

In this problem we're using filter `mysql contains select` to find the packets that have select query command

*here is the packets contains select query*
![4 bener](https://user-images.githubusercontent.com/81411468/134649194-354d44c2-f6a6-490d-89da-6e85d29077b2.PNG)

**Difficulties**
- no difficulties

# Problem 5
**Login to portal.ichimarumaru.tech then follow the instructions! The username and password can be obtained from the insert query in the users table from the .pcap file!**

In this problem we're using the packets from `Problem 4` with the same filter as well. then we go through `tcp stream` then we can find the username and password that used to login to portal.ichimarumaru.tech

*here is how the tcp stream looks like and where the username and password placed*
![4](https://user-images.githubusercontent.com/81411468/134629804-2c3a789a-712e-44b2-bb05-8e3c4862baf9.PNG)

*here is the answero of portal.ichimarumaru.tech*
![5](https://user-images.githubusercontent.com/81411468/134629887-0b9da0d8-4217-4770-959c-d312d24d1cc0.PNG)

**Difficulties**
- Used wrong filter but then ended up find the username and password

# Problem 6
**Find username and password when logging into FTP Server!**

In this problem we want to find the user and pass in FTP server. We're using `ftp.request.command == USER || ftp.request.command == PASS` to find the packet that has the user and pass. The user and password shown on the packet (right side)

*here is the packet that show the user and pass*
![666](https://user-images.githubusercontent.com/81411468/134630508-09bdf694-b786-46c9-9d40-51c09568c635.PNG)

**Difficulties**
- if we're using `ftp.request.command == user || ftp.request.command == pass` it will not show the packet that contains user and pass

# Problem 7
**There are 500 zip files saved to FTP Server with names 0.zip, 1.zip, 2.zip, ..., 499.zip. Save and Open the pdf file. (Hint = the name of the pdf is "Real.pdf")**

In this problem we want to find the `Real.pdf` that hiding in one of 500 zip files in our FTP server. First we need to find the packet that contains Real.pdf with `ftp-data contains Real.pdf` filter. Then we can go to tcp stream of the packets and show the data as `raw` and save it as `.pdf` files.

*here is the packet shown using filter `ftp-data contains Real.pdf`*
![filter ftp](https://user-images.githubusercontent.com/81411468/134631319-515a3368-b00b-40fe-bc57-2f32d747377e.PNG)

*here is the tcp stream of the packets*
![Raw PDF](https://user-images.githubusercontent.com/81411468/134631372-04519617-acb3-48ad-b383-a57059dcd7d9.PNG)

*here is the picture inside Real.pdf*
![Real](https://user-images.githubusercontent.com/81411468/134631392-47ca76de-7eab-40ea-a001-0871ec08bb7a.PNG)

**Difficulties**
- if we using `ftp-data contains real.pdf` filter, it not shown anything

# Problem 8
**Look for the packets that show the retrieval of files from the FTP!**

In this problem we want to find the packets that show retrieval of files from FTP server. we're using filter `ftp.request.arg`

*here is the packets that shown with the filter `ftp.request.arg`*
![8 fix](https://user-images.githubusercontent.com/81411468/134649587-efaf8ee7-8bc6-4fa7-a231-98d3b29d4a45.PNG)

**Difficulties**
- at first, confuse what filter to find the correct packets 

# Problem 9
**From the packets going to FTP, there are indications of storing some files. One of them is a file containing confidential data with the name "secret.zip". Save and open the file!**

In this problem we need to find the packets that contains secret.zip . We're using filter `ftp-data.command contains "secret.zip"` . Then we go to tcp stream based on our packets that shown then show it as raw data and save it as `.zip` files.

*here is the packets shown with our filter `ftp-data.command contains "secret.zip"`*
![no 9 fix](https://user-images.githubusercontent.com/81411468/134649955-356c4070-6f3a-4637-8305-f68360de3103.PNG)

*here the `secret.zip` files contain wanted.pdf*
![Isi wanted](https://user-images.githubusercontent.com/81411468/134650134-38e362c9-f4d2-4771-abdf-558032ca19fd.PNG)

**Difficulties**
- using wrong filter and the `secret.zip` files are damaged.

# Problem 10
**Also there is "history.txt" which probably contains the history of the bash server! Use the contents of "history.txt" to find the password to open the secret file in "secret.zip"!**

In this problem we need to find packets that contains `history.txt`. first we using filter `ftp-data contains "history.txt"` . from that we found the clue `bukanapaapa.txt`
. Then we need to find the `bukanapaapa.txt` packets to find the password using `ftp-data.command contains "bukanapaapa.txt"`.

*here is the packets with the filter `ftp-data contains "history.txt"`*
![10 1](https://user-images.githubusercontent.com/81411468/134650479-26963281-2b9a-4cb3-bab7-233b2ed247db.PNG)

*here is the packets with `ftp-data.command contains "bukanapaapa.txt"`
![10 2](https://user-images.githubusercontent.com/81411468/134650992-72e65024-8b64-43f5-a7f3-1399d18faae6.PNG)

from here we know the password of the zip using `d1b1langbukanapaapajugagapercaya` for problem 9

**Difficulties**
- using wrong filter to find the password of the zip.

# Problem 11
**Filter so that wireshark only picks up packets coming from port 80!**
![11](https://user-images.githubusercontent.com/74058892/134762013-5acafd9b-1b55-439a-a28a-357ff008a96a.jpeg)

In this problem we have to picks up packet that only coming from port 80. So, we use filter tcp.srcport == 80 and that is the result. As you can see that the source port is 80.

**Difficulties**
- No difficulties

# Problem 12
**Filter so that wireshark only picks up packets containing port 21!**
![12](https://user-images.githubusercontent.com/74058892/134762020-ae2929ed-87fc-4472-a8b6-0c616dfb1715.jpeg)

In this problem, we need to find packets that containing port 21. SO, we use filter tcp.port == 21 || udp.port == 21 and you can see the result above. there is no packet that contains port 21

**Difficulties**
- We are not really sure because we already try together and there is still no result for problem 12

# Problem 13
**Filter so that wireshark only shows packets going to port 443!**
![13](https://user-images.githubusercontent.com/74058892/134762025-4632b8e5-03ce-4ff0-8a9d-ac3ade3bfc4e.jpeg)

In this problem we have to shows packets that going to port 443. So, we use filter tcp.dstport == 443 and then we get the result like the picture above. As you can see from the picture, the destination port is 443.

**Difficulties**
- No difficulties

# Problem 14
**Filter so that wireshark only picks up packets going to kemenag.go.id!**

First we need to know the kemenag.go.id ip using `command prompt` then we use the filter `ip.addr == 103.7.13.247` which is using kemenag.go.id ip

*here is the checking ip in command prompt* <br />
![ip kemenag](https://user-images.githubusercontent.com/81411468/134631793-a227645e-d769-4d5c-889c-7e731da50440.PNG)

*here is the packet using filter `ip.addr == 103.7.13.247`*
![filter kemenag](https://user-images.githubusercontent.com/81411468/134631825-9a47e1ba-e871-4626-8d96-061e9e766086.PNG)

**Difficulties**
- no Difficulties

# Problem 15
**Filter so that wireshark only picks up packets coming from your local ip address!**

For the answer, first of all you need to open Command Prompt and enter “ipconfig” and it will reveal the IPv4 Address →192.168.100.8 
After that inside the filter input the `command ip.addr == 192.168.100.8` after the capture packet command has run a bit.

![image](https://user-images.githubusercontent.com/81474281/134762955-23f1c297-f70d-459e-a40f-ae8e5c9e6c3c.png)

Result from opening ipconfig

![image](https://user-images.githubusercontent.com/81474281/134762977-9edc6618-d739-4ffa-ad73-16e49ccb240d.png)

result after inputting ip.addr == 192.168.100.8 in the filter

**Difficulties**
- no Difficulties
