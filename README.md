<i>Project Title : </i>
     <strong>Reconstruction of JPEG and PNG Images from pcap file.</strong><br>
     <br>
Overview : <br>
       <ol> To retrieve downloaded images by monitoring and capturing network traffic with the use of Wireshark and Hex Editor(HxD) </ol><br>
       <i>Features : </i><br>
       <li> JPEG file reconstruction from pcap file
       <li> PNG file reconstruction from pcap file

#Tools used : Wireshark, HxD Hex Editor
In this project, by using Digital Forensics, JPG and PNG images are reconstructed.

Flow : 
Step 1: Capturing the network traffic using network analyzers like Wireshark. 
        At this point, we get packet capture(pcap) file. Here the file has extension .pcapng
Step 2: After successful packet capturing, load the pcap file in Wireshark.
Step 3: Now, Wireshark loads the captured data.
        Set the filter to HTTP traffic to know more about the data that has been browsed.
Step 4: As data is requested, the server fetches the data through get method(200=OK).
Now, check the get method for the downloaded image name along with extension.
For JPEG files, it goes like oi.jpg(Assuming oi is the image name).
The similar goes for PNG files as oi.png(Assuming oi is the image name).
Now, select the image to be retrieved.
In this instance, lets take JPEG as example.
Go to oi.jpg file.
Then right click on it and navigate to follow.
In follow navigate to TCP stream as it stores the data of the image. Now a new screen pops up displaying the packet data.
Check the data format and set data filter to raw data.
This filter displays the data in hex code, now search for the JFIF i.e JPEG File Image Format.
 The JPEG header is FFD8 and footer is FFD9 .
So search the data and copy the entire data from FFD8 to FFD9.
Now, Open any Hex Editors.
In this project we will be using HxD.
So, open HxD Editor and create a new file.
Now paste the previous data into it, the hex data is aligned with the HXD editor.
Now, save the file as image.jpeg.
Thus, the jpeg image is sucessfully retrieved.

Retrieval of PNG Image:
Follow the above steps untill raw datA view.
Here, we using png header and footer formats for detecting the file start and the end.
The header starts with 89 50 4E and footer ends with 45 4E 44.
By using this signature, the data between the header and footer is extracted.
Now, the extracted data is pasted in HxD editor and the file is saved.
Make sure to save the file using .png file extension. Thus, png file has been successfully retrieved.
