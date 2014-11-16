CacheSemaphore
==============

This project contains an example of how to create and work with Seaphore in DBMS Intersystems Caché. It uses Increment and Decrement methods.

------------------------------=========================================------------------------------
University was given 10 slots to access international database of scientific articles. Each student has its own username and password. Each time someone logs in the database the number of available slots is decreased (of course) and when someone logs out this number comes up. 
------------------------------=========================================------------------------------


The idea of this sample is to show how to use semaphore to share access to the DB between students.

To import this project into your DB please open Caché Studio and click Tools -> Import local... In browser window choose xml file and click Open. Check all files and compile them. After it is done, open three seperate Terminal windows and in each of the input following commands (check the namespace beforehand - it should be the same for both Terminal and Studio) if you want to see how it works:

1. do ##class(SemaphoreSample.Main).Run()

2. do ##class(SemaphoreSample.LogIn).Run()

3. do ##class(SemaphoreSample.LogOut).Run()

First one starts the main thread which creates a semaphore and controls the flow. Second one starts the thread in which "students" log in their accounts. The third one starts the thread in which "students" log out of their accounts. When all 25 "students" are done working the semaphore is killed and in the first window you can see the log.

For more info please refer to the documentation on www.intersystems.com.
