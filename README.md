# Blackhat-CTF-MEM-Forensics---Write-up

TThis challenge was a memory dump file. ( RAW file )

<img width="618" alt="Screen Shot 1444-03-09 at 8 52 23 AM" src="https://user-images.githubusercontent.com/114960489/193990638-37bb40ba-c1b6-47bf-9993-6ce71c04eb23.png">



So, the first thing that will kick off is to look for any printable, texetual strings in the RAW file by using the [ strings command ] 

<img width="381" alt="Screen Shot 1444-03-09 at 9 04 03 AM" src="https://user-images.githubusercontent.com/114960489/193992080-060da278-e925-4064-b91f-c9265f0b2bfc.png">


What we did above Basically, we print all strings that contain "flag." Sometimes a flag can be found, but in this case we found the following:

1-File Path 
2-The flag is compressed by.rar as it shows below.


<img width="456" alt="image" src="https://user-images.githubusercontent.com/114960489/193992564-67488657-8bf9-4299-b4b5-b734771a381d.png">



Now, we will start with the Volatility 2 tool.

In order to use Volatility 2, we need to identify the OS and architecture of this memory image by using the below plugin.



<img width="841" alt="Screen Shot 1444-03-09 at 9 22 54 AM" src="https://user-images.githubusercontent.com/114960489/193994491-ee176d27-96b7-4dd2-af02-8afd0143cd20.png">



We got the profile. Usually, we take the first suggested profile.

Now, we will scan the files to locate the physical address "offest" of that file in order to dump it 



<img width="798" alt="Screen Shot 1444-03-09 at 9 29 46 AM" src="https://user-images.githubusercontent.com/114960489/193995415-81464247-d27c-4184-af1b-3724cf53381f.png">



The physical address "offset" of the "flag file" in the memory is [0x000000001bbf9c0].


In order to extract/dump the file and save it on the desktop, we will use the following:



<img width="796" alt="Screen Shot 1444-03-09 at 9 35 04 AM" src="https://user-images.githubusercontent.com/114960489/193996151-24652e9b-138c-4c1a-81fd-b000abb17fd1.png">



Now, we have the file dumped on the desktop with .dat, so we can extract it or change the extension to be .rar in order to unrar it 

I have extracted it and it is protected with a password as it is shown in the below figure.



<img width="792" alt="Screen Shot 1444-03-09 at 9 37 46 AM" src="https://user-images.githubusercontent.com/114960489/193996527-cdaffd4c-09e5-4269-b9e2-b148a6bff57e.png">



As it is mentioned in the challenge description, " I don't remember the password and saved it locally."

So, we will run the envirs plugin to display all environment variables.



<img width="855" alt="Screen Shot 1444-03-09 at 9 53 39 AM" src="https://user-images.githubusercontent.com/114960489/193998804-00fdc999-f9f4-4bf9-8809-3c7469c8c806.png">


When the result comes up, we can see that "systemP and some random strings" were used, and it is not a windows path, so I assumed that was the password!

Let's try it!


<img width="766" alt="Screen Shot 1444-03-09 at 10 02 59 AM" src="https://user-images.githubusercontent.com/114960489/194000271-eacaf839-3617-41f4-b5cd-6b9ea8b90865.png">


excellent! When we open the file, we get flag.txt > open it > congratulations "YOU HAVE THE FLAG!"


