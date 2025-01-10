<h1>Exploring the Bytes: A Journey into File Signatures</h1>


<h2>Description</h2>
This project focuses on digital forensics, where you analyze file signatures, or "magic numbers," to help identify file formats and ensure data integrity. Using the table from Gary Kessler's website, you'll be comparing the file signatures of JPG and GIF files with the xxd tool to visualize the hexadecimal data and match them against the standard signatures of these file types. The purpose of this project is to develop a deeper understanding of how file types are identified, how this process can aid in verifying file authenticity, and how forensics tools can use this method to spot tampered or suspicious files.

A key part of the project is manipulating file signatures by echoing forged signatures into files, allowing you to create fake files that mimic real formats. This exercise allows you to explore how altering file signatures impacts file type identification, helping you understand how manipulation of signatures can mislead or confuse detection methods. It's a valuable skill set for investigators dealing with file misidentification or potential malware, as tampered or falsely identified files often raise flags during forensic investigations.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Bash</b> 
- <b>xxd</b>
- <b>[Gary Kessler's Website](https://www.garykessler.net/library/file_sigs.html)</b>

<h2>Environments Used </h2>

- <b>Kali Linux</b>

<h2>Walk-through:</h2>

<p align="left">
<h3> In this section we are going to be exploring the file signatures of the image "cat.jpg".</h3>
<br>
<br>
  <img src="https://i.imgur.com/AjYToXE.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<b> The following is a screenshot from Gary Kessler's Website, and it shows the header (FF D8) and trailer (FF D9) of a JPG file.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/GwUqRs3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<b> In Linux, we can confirm the file type of "cat.jpg" by using the (file) command.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/xAVIR0v.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<b> By running the command (xxd cat.jpg | head) we can see the first 10 lines of the files hexa dump, and if we compare the first 2 bytes, we can see the signatures match with the header in the magic numbers table.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/5cRCwVV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<b> By running the command (xxd cat.jpg | tail -n 5) we can see the last 5 lines of the files hexa dump, and if we compare the last 2 bytes, we can see the signatures match with the trailer in the magic numbers table.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/J6BMfam.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<h3> In this section we are going to be manipulating files by forging the signatures of a JPG file.</h3>

<b> Here we create a few variables. We create the variable jpegsignature which corralates to the file header and trailer in the magic number table, and a file variable, an array of 3 files (gdltvaycay.jpg gdltvaycay_2.jpg gdltvaycay_3.jpg). We then run a simple in line statement for loop that echos the jpegsignature into each file in the "file" variable. <b/> 
<br>
<br>
  <img src="https://i.imgur.com/0EFlY8L.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />




<h3> In this section we are going to be exploring the file signatures of the gif "simpsons.gif".</h3>
<br>
<br>
  <img src="https://i.imgur.com/DwjbC6Q.gif" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<b> In Linux, we can confirm the file type of "simpsons.gif" by using the (file) command.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/FH0w8fm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<b> The following is a screenshot from Gary Kessler's Website, and it shows the header (47 49 46 38 37 61) and trailer (00 3B) of a GIF file.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/CXMKh6z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<b> By running the command (xxd simpsons.gif | head) we can see the first 10 lines of the files hexa dump, and if we compare the first 2 bytes, we can see the signatures match with the header in the magic numbers table.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/51yVWbB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<b> By running the command (xxd simpsons.gif | tail -n 5) we can see the last 5 lines of the files hexa dump, and if we compare the last 2 bytes, we can see the signatures match with the trailer in the magic numbers table.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/f8iuMb0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>
