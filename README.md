<i>Project Title : </i>
     <strong>Reconstruction of JPEG and PNG Images from pcap file.</strong><br>
     <br>
Overview : <br>
       <ol> To retrieve downloaded images by monitoring and capturing network traffic with the use of Wireshark and Hex Editor(HxD) </ol><br>
      Features : </i><br>
       <br>
       <li> JPEG file reconstruction from pcap file
       <li> PNG file reconstruction from pcap file</li><br>

Tools used :</i> Wireshark, HxD Hex Editor<br>
<br>
Flow :</i> <br>
<br>
<li> Initially, we capture the network traffic using network analyzers like Wireshark. 
       <li> Save the generated data as packet capture(pcap) file. Here the file has extension .pcapng
<li>After successful packet capturing, load the pcap file in Wireshark.
<li> Now, Wireshark loads the captured data.
        <li>Set the filter to HTTP traffic to know more about the data that has been browsed.
<li> As data is requested, the server fetches the data through get method(200=OK).
<li>Now, check the get method for the downloaded image name along with extension.
<li>For JPEG files, it goes like oi.jpg(Assuming oi is the image name).
<li>The similar goes for PNG files as oi.png(Assuming oi is the image name).
<li>Then, select the image to be retrieved.
<p>In this instance,<strong> lets take JPEG</strong> as example.</p>
<li> Go to oi.jpg file.
<li> Then right click on it and navigate to follow.
<li> In follow navigate to TCP stream as it stores the data of the image. Now a new screen pops up displaying the packet data.
<li> Check the data format and set data filter to raw data.
<li> This filter displays the data in hex code, now search for the JFIF i.e JPEG File Image Format.
 <li> The JPEG header is <strong>FFD8</strong> and footer is <strong> FFD9</strong> .
<li> So search the data and copy the entire data from FFD8 to FFD9.
<li> Now, Open any Hex Editors.
<li> In this project we will be using HxD.
<li> So, open HxD Editor and create a new file.
<li> Now paste the previous data into it, the hex data is aligned with the HXD editor.
<li> Now, save the file as image.jpeg.
<li> Thus, the jpeg image is sucessfully retrieved. <br>
<br>
<strong>Retrieval of PNG Image:</strong>
<br><br>
<li>Go to oi.png file.
<li> Then right click on it and navigate to follow.
<li> In follow navigate to TCP stream as it stores the data of the image. Now a new screen pops up displaying the packet data.
<li> Check the data format and set data filter to raw data.
<li> Here, we are using png header and footer signature for detecting the file's start and the end.
<li> The header starts with <strong>89 50 4E</strong> and footer ends with <strong>45 4E 44.</strong>
<li> By using this <strong>signature</strong>, the data between the header and footer is extracted.
<li> Now, the extracted data is pasted in HxD editor and the file is saved.
<li> Make sure to save the file using .png file extension. Thus, png file has been successfully retrieved.
<br>
<i>Thus, by following the above process, PNG and JPEG images can be retrieved </i>
