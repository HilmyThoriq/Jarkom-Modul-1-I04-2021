# Problem 1
**What web server is used on "ichimarumaru.tech"!**

# Problem 2
**Find the packets from the web that use the basic authentication method!**

In This Problem, We need to find packets from the web that use basic authentication method. We simply use filter `http contains "basic"`
Next we can confirm the packets got basic authentication by seeing the details below
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

# Problem 5
**Login to portal.ichimarumaru.tech then follow the instructions! The username and password can be obtained from the insert query in the users table from the .pcap file!**

In this problem we're using the packets from `Problem 4` with the same filter as well. then we go through `tcp stream` then we can find the username and password that used to login to portal.ichimarumaru.tech

*here is how the tcp stream looks like and where the username and password placed
![4](https://user-images.githubusercontent.com/81411468/134629804-2c3a789a-712e-44b2-bb05-8e3c4862baf9.PNG)

*here is the answero of portal.ichimarumaru.tech
![5](https://user-images.githubusercontent.com/81411468/134629887-0b9da0d8-4217-4770-959c-d312d24d1cc0.PNG)

**Difficulties**
- Used wrong filter but then ended up find the username and password

# Problem 6
**Find username and password when logging into FTP Server!**

In this problem we want to find the user and pass in FTP server. We're using `ftp.request.command == USER || ftp.request.command == PASS` to find the packet that has the user and pass. The user and password shown on the packet (right side)

*here is the packet that show the user and pass
![666](https://user-images.githubusercontent.com/81411468/134630508-09bdf694-b786-46c9-9d40-51c09568c635.PNG)

**Difficulties
- if we're using `ftp.request.command == user || ftp.request.command == pass` it will not show the packet that contains user and pass

# Problem 7
**There are 500 zip files saved to FTP Server with names 0.zip, 1.zip, 2.zip, ..., 499.zip. Save and Open the pdf file. (Hint = the name of the pdf is "Real.pdf")**

In this problem we want to find the `Real.pdf` that hiding in one of 500 zip files in our FTP server. First we need to find the packet that contains Real.pdf with `ftp-data contains Real.pdf` filter. Then we can go to tcp stream of the packets and show the data as `raw` and save it as `.pdf` files.

*here is the packet shown using filter
![filter ftp](https://user-images.githubusercontent.com/81411468/134631319-515a3368-b00b-40fe-bc57-2f32d747377e.PNG)

*here is the tcp stream of the packets
![Raw PDF](https://user-images.githubusercontent.com/81411468/134631372-04519617-acb3-48ad-b383-a57059dcd7d9.PNG)

*here is the picture inside Real.pdf 
![Real](https://user-images.githubusercontent.com/81411468/134631392-47ca76de-7eab-40ea-a001-0871ec08bb7a.PNG)

**Difficulties
- if we using `ftp-data contains real.pdf` filter, it not shown anything

# Problem 8
**Look for the packets that show the retrieval of files from the FTP!**

# Problem 9
**From the packets going to FTP, there are indications of storing some files. One of them is a file containing confidential data with the name "secret.zip". Save and open the file!**

# Problem 10
**Also there is "history.txt" which probably contains the history of the bash server! Use the contents of "history.txt" to find the password to open the secret file in "secret.zip"!**

# Problem 11
**Filter so that wireshark only picks up packets coming from port 80!**

# Problem 12
**Filter so that wireshark only picks up packets containing port 21!**

# Problem 13
**Filter so that wireshark only shows packets going to port 443!**

# Problem 14
**Filter so that wireshark only picks up packets going to kemenag.go.id!**

First we need to know the kemenag.go.id ip using `command prompt` then we use the filter `ip.addr == 103.7.13.247` which is using kemenag.go.id ip

*here is the checking ip in command prompt
![ip kemenag](https://user-images.githubusercontent.com/81411468/134631793-a227645e-d769-4d5c-889c-7e731da50440.PNG)

*here is the packet using filter
![filter kemenag](https://user-images.githubusercontent.com/81411468/134631825-9a47e1ba-e871-4626-8d96-061e9e766086.PNG)

# Problem 15
**Filter so that wireshark only picks up packets coming from your local ip address!**
