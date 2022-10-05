# Blackhat-CTF-MEM-Forensics---Write-up

The Challenge was a memory dump file. ( RAW file )

<img width="618" alt="Screen Shot 1444-03-09 at 8 52 23 AM" src="https://user-images.githubusercontent.com/114960489/193990638-37bb40ba-c1b6-47bf-9993-6ce71c04eb23.png">



So, the first thing will kick off to looks for any printable, texetual strings in the RAW file by using [ strings command ] 

<img width="381" alt="Screen Shot 1444-03-09 at 9 04 03 AM" src="https://user-images.githubusercontent.com/114960489/193992080-060da278-e925-4064-b91f-c9265f0b2bfc.png">


what we did above basically we print all strings that contain "flag" sometimes flag can be found but in this case we found the following:

1- File Path
2- The flag is compressed by .rar as it shows below figur


<img width="456" alt="image" src="https://user-images.githubusercontent.com/114960489/193992564-67488657-8bf9-4299-b4b5-b734771a381d.png">






<img width="517" alt="image" src="https://user-images.githubusercontent.com/114960489/193988727-e38be489-d99a-4009-903d-a639ef23c266.png">
