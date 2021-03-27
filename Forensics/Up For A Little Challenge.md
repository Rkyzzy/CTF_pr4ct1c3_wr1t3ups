# Up For A Little Challenge

### Platform: CTFLearn

#### Link: https://ctflearn.com/challenge/142

#### Difficulty: Medium

Solution:

![image-20210327164923114](C:\Users\98299\AppData\Roaming\Typora\typora-user-images\image-20210327164923114.png)

Going through the link provided we get a jpg file

![image-20210327165141074](C:\Users\98299\AppData\Roaming\Typora\typora-user-images\image-20210327165141074.png)

![image-20210327165200386](C:\Users\98299\AppData\Roaming\Typora\typora-user-images\image-20210327165200386.png)

To analyze the jpg file, we first check the file type of it:

![image-20210327165419520](C:\Users\98299\AppData\Roaming\Typora\typora-user-images\image-20210327165419520.png)

From the result we know that it is really the file type as it seems,

So we go on analyze the file using strings command to see if the flag is hidden in it.

![image-20210327165707677](C:\Users\98299\AppData\Roaming\Typora\typora-user-images\image-20210327165707677.png)

Here we found two important information, one is another link that leads to the download of a zip file

![image-20210327165922673](C:\Users\98299\AppData\Roaming\Typora\typora-user-images\image-20210327165922673.png)

And The lower part

A unlock key and a password. At the end of it is a flag, but as it says, it is not so simple.

In the file extracted from zip, there is a folder called Did I Forget Again, after open it, it looks like this:

![image-20210327170433877](C:\Users\98299\AppData\Roaming\Typora\typora-user-images\image-20210327170433877.png)

With only a jpg file, it is kind of strange, so I use ls -a and find there is a hidden file called '.Processing.cerb4'

![image-20210327170535480](C:\Users\98299\AppData\Roaming\Typora\typora-user-images\image-20210327170535480.png)

To know what kind of file it is, use file to find out

![image-20210327170636744](C:\Users\98299\AppData\Roaming\Typora\typora-user-images\image-20210327170636744.png)

It seems that it is a zip archive, so use unzip to unzip it

Then a password is required to unzip, so I tried the hint it gives us in the previous strings step, I tried password one and the unlock_key one, but none of them is correct. Then I think the 'U' in unlock_key: 'Nothing Is As It SeemsU' looks strange, so I tried 'Nothing Is As It Seems' and It is correct. The file is unzipped.

The U is omitted maybe because of the hint it gives us with the picture name 'Loo Nothing Become Useless ack'.

After the file is extracted, a jpg called skycoder.jpg is found:

![image-20210327171232277](C:\Users\98299\AppData\Roaming\Typora\typora-user-images\image-20210327171232277.png)

After carefully checking the picture, the flag is found at the corner of it:

![image-20210327171404519](C:\Users\98299\AppData\Roaming\Typora\typora-user-images\image-20210327171404519.png)

And the flag is CTFlearn{hack_complete}