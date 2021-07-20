### Lab: Unprotected admin functionality

#### Scenario:
This lab has an unprotected admin panel.

Solve the lab by deleting the user `carlos.`

#### Walkthrough 
1. We initially land on the login page for `We Like to Blog.` Since we already know the library and vulnerability class, we will enumerate the application by looking for an administrator panel. 
![image1](images/access_1.png)

2. When enumerating the application, there is a `robots.txt` file with an entry of `Disallow: /administrator-panel.` The `robots.txt` file is an excellent place to review for additional attack surfaces. 
![image2](images/access_2.png)

3. When navigating to the `administrator-panel` endpoint, two headers can be deleted. The objective of this challenge is to delete the user. Once completed, the challenge is marked as solved.
![image3](images/access_3.png)