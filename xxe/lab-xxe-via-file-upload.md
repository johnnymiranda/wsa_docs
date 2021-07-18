### Lab: Exploiting XXE via image file upload

#### Scenario 
This lab lets users attach avatars to comments and uses the Apache Batik library to process avatar image files. To solve the lab, upload an image that displays the contents of the /etc/hostname file after processing. Then use the "Submit solution" button to submit the value of the server hostname.

#### Walkthrough
1. We initially land on the login page for `We Like to Blog`. Since we already know the library and vulnerability class, we will enumerate the application until we find an imagee update. 
[image1]
2. At the endpoint `{random_id}.web-security-academy.net/post?postId=2` there is an avatar image upload. From the scenario of this challenge we know the image processing library and the goal, which is to display the contents of `/etc/hostname` to verify code execution. 
[image2]
3. Using the GitHub repository `PayloadsAllTheThings` we can navigate to `https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/XXE%20Injection/Files/Classic%20XXE.xml` and review this XXE payload. 
4. Use the above payload to generate `image_payload.svg`. 