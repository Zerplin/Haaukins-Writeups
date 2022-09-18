## In The Flesh

We receive a pcap file that is said to contain mysterious file transfers.
After loading the pcap file into Wireshark, we export HTTP objects and look at a bunch of cursed images from the capture.

<img src = "https://user-images.githubusercontent.com/43621940/190922419-dd7e118b-cb43-4bc1-9760-924369b3231f.png" width = 50% >

After a while, we realize that none of the HTTP objects are relevant and notice a bunch of FTP traffic instead.
Following this traffic reveals that a zip file has been transfered.

<img src = "https://user-images.githubusercontent.com/43621940/190922620-79d8a1ec-7539-4311-9f20-a82ab38c5ff2.png" width = 50% >

We then look for the zip file by searching for FTP-DATA traffic and following it.
We find the following transfer and identify it as a zip file by the "PK" in the header.

<img src = "https://user-images.githubusercontent.com/43621940/190922972-e60c5bb6-dfe7-4e52-8160-3c0c2da7d546.png" width = 50% >

We format the file to raw before saving it as a zip.
Once unzipped we see a bunch of images and a password protected zip-file

<img src = "https://user-images.githubusercontent.com/43621940/190924438-75161576-49b9-4e7b-a2fd-7c35875d797f.png" width = 50%>

After a while we notice the phrase "heybookworm" in one of the pictures 

<img src = "https://user-images.githubusercontent.com/43621940/190924532-ae36d330-1468-4589-af31-f771f99545a1.png" width = 50%>

We use it as a password to unzip the flag

<img src = "https://user-images.githubusercontent.com/43621940/190924599-7d2356db-9dd0-4804-bf51-ad819ca88789.png" width = 50%>

