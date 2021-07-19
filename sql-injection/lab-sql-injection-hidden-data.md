### Lab: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

#### Scenario:
This lab contains an SQL injection vulnerability in the product category filter. When the user selects a category, the application carries out an SQL query like the following:

`SELECT * FROM products WHERE category = 'Gifts' AND released = 1`

To solve the lab, perform an SQL injection attack that causes the application to display details of all products in any category, both released and unreleased.

#### Walkthrough
1. We initially land on the main page for `We like to Shop`. Due to the scenario, we can assume the vulnerable parameter will be `category`
2. The simplest way to test if a target is SQL injectable, is simply passing in some `bad character` like single quotes, double quotes, etc. 
3. The web application returns an `Internal Server Error` when a `'` was passed into the `category` parameter. 
[image1]
4. After reviewing the following payloads (PayLoadAllTheThings)[https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/SQL%20Injection], I decided to manually attempt to exploit the `WHERE` clause. I do this in Burp Repeater since it's easy to send another request. 
5. 