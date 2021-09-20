---
description: >-
  Specify a file to automatically open when a user accesses its folder through
  the File Manager.
---

# Automatically Opening Files

When you upload content to your Block, such as a web application, it may include folders containing large numbers of files and sub-folders. When a user accesses the content through the File Manager they risk being confused by which file it is they should open to begin using the uploaded application. 

{% hint style="info" %}
An example would be a web application with an `index.html` or `index.php` file. Alongside those files will be many other files you will not need the user to see.
{% endhint %}

Therefore, your Block provides the ability to specify a file to automatically open when a user uses the file manager to access the folder which it is stored within. Prefix the file you would like to automatically open with the string:

```text
--auto-open
```

**Only users that are not logged in to the Control Panel will benefit from the automatic opening of files.** This is so that an administrator logged in to the Control Panel is able to access the folder and change the files. 

{% hint style="info" %}
Here are a few examples:

`--auto-open.jpeg  
--auto-open-my-original-filename.php  
--auto-open_anythinghere.html`
{% endhint %}

{% hint style="warning" %}
It is important to keep the original file extension on the end of your file. Otherwise, your browser will not know how to open the file. 
{% endhint %}

