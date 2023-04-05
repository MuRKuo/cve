**ibos OA v4.5.5 SQL Injection vulnerability**

Project download address：https://gitee.com/ibos/IBOS

There is a vulnerability route：file/personal/del&op=recycle  

Vulnerability parameters exist:filds

 1.Function point: file cabinet delete folder
 
 ![WPS图片(1)](https://user-images.githubusercontent.com/31273358/230069472-82cb73ac-0259-4305-b881-8433aabdff5c.png)

![WPS图片(2)](https://user-images.githubusercontent.com/31273358/230069500-2590c15d-37bf-43d3-ac4a-e10f4bb629b3.png)

![WPS图片(3)](https://user-images.githubusercontent.com/31273358/230069635-feb1c69e-5c6e-4e2c-9e60-e03897158e08.png)


2. Source code analysis

Receive the fids parameter and process the incoming fids through the fetchAllByFids() method under the model

![WPS图片(4)](https://user-images.githubusercontent.com/31273358/230069975-c1fbee47-a248-4ae4-bd2a-dfe4a11bffe7.png)

The SQL statement is encapsulated in the fetchAllByFids() method, and queryAll() executes the SQL statement to cause the SQL injection

![WPS图片(5)](https://user-images.githubusercontent.com/31273358/230070096-078ed945-2e18-4ae6-a2e6-a423727faa8c.png)

![WPS图片(6)](https://user-images.githubusercontent.com/31273358/230070182-757ce71a-8819-478e-b9f7-55682f4c82ae.png)

This will call the YII framework with an error.

![WPS图片(7)](https://user-images.githubusercontent.com/31273358/230070314-952b92e7-c77e-45a3-b2c7-73d7a35b716b.png)
