# Alexandro Galvez-Vega

# Project 7 - WordPress Pen Testing

Time spent: 10 hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pen Testing Report

### 1. Authenticated Stored Cross Site Scripting Through Post Messages

- [x] Summary: Code can be inserted through a post. 
  - Vulnerability types: XSS
  - Tested in version: 4.1.0
  - Fixed in version: 4.1.6
- [x] GIF Walkthrough:
<img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExMmY4Y2U2MTk3ZDg3ZDRlY2RiNTllOTg3N2JjYjY3NmVmZWE5NGY1OCZlcD12MV9pbnRlcm5hbF9naWZzX2dpZklkJmN0PWc/gQWJu9oZ03mDYa4dwP/giphy.gif" alt="E1">
 https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExMmY4Y2U2MTk3ZDg3ZDRlY2RiNTllOTg3N2JjYjY3NmVmZWE5NGY1OCZlcD12MV9pbnRlcm5hbF9naWZzX2dpZklkJmN0PWc/gQWJu9oZ03mDYa4dwP/giphy.gif

- [x] Steps to recreate: This is an easier one to create. First go to posts. Next, select add new post. Enter whatever title and make sure the text option is selected for the comment box. Add the code to the comment box. Submit. Then, visit the post area and select the appropriate post. Hovering over the link will show the alert. This is an example of the code insert <a href="[caption code=">]</a><a title=" onmouseover=alert('1')  ">link</a>. A editor account was used in this scenario.
- [x] Affected source code:
  - [Link 1](http://wpdistillery.vm/wp-admin/post-new.php)
  - [Link 2](http://127.0.0.1:8080/?p=43)
  
  
### 2. User Enumeration

- [x] Summary: Wpscan can be used to gather usernames and passwords. 
  - Vulnerability types: Enumeration
  - Tested in version:4.1.0
  - Fixed in version: 4.3.0
- [x] GIF Walkthrough:
<img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExNTMyNjBmMzBmODVlM2MwY2NhZjY4NzNkZGIxNDdjMmI3NDg3NjU4ZiZlcD12MV9pbnRlcm5hbF9naWZzX2dpZklkJmN0PWc/jYdxAmRS04k5XTZIHX/giphy.gif" alt="E2">
 https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExNTMyNjBmMzBmODVlM2MwY2NhZjY4NzNkZGIxNDdjMmI3NDg3NjU4ZiZlcD12MV9pbnRlcm5hbF9naWZzX2dpZklkJmN0PWc/jYdxAmRS04k5XTZIHX/giphy.gif

- [x] Steps to recreate: If one visits the login for the first time and inserts the wrong thing there is a hint that it might be able to be user enumerated. From there I entered docker in order to access kali. The command [wpscan --url http://127.0.0.1:8080/ --enumerate u] will return back all of the usernames. wpscan can also be used to obtain all of the passwords as well. An example of this is shown in the bottom youtube video. 
- [x] Affected source code:
  - [Link 1](http://wpdistillery.vm/wp-login.php)
  - [Link 2](http://127.0.0.1:8080/wp-login.php?loggedout=true)

### 3.  Authenticated Cross Site Scripting By Uploading Through Media

- [x] Summary: Code can be added by uploading images.
  - Vulnerability types: XSS
  - Tested in version: 4.1.0
  - Fixed in version: 4.1.16
- [x] GIF Walkthrough: 
<img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOWQ2M2U4ZjgxY2I2YjdlZmVjNDRhMGE2MDM0MmIwMWJlNTZhOWRhNiZlcD12MV9pbnRlcm5hbF9naWZzX2dpZklkJmN0PWc/opfphPwmRK3P01laiV/giphy.gif" alt="E3">
https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOWQ2M2U4ZjgxY2I2YjdlZmVjNDRhMGE2MDM0MmIwMWJlNTZhOWRhNiZlcD12MV9pbnRlcm5hbF9naWZzX2dpZklkJmN0PWc/opfphPwmRK3P01laiV/giphy.gif

- [x] Steps to recreate: This is another fairly straightforward set of steps. Go to media. Select add new media. Upload an image with some sort of command as the title. Click on the loaded piece of media. Select the option to view it using view attachment image. The alert will apear. This is an example bit of code used: Here <img src= a onerror=alert('Alert ')>.jpg. 
- [x] Affected source code:
  - [Link 1](http://127.0.0.1:8080/wp-admin/upload.php)
  - [Link 2](http://wpdistillery.vm/wp-admin/post-new.php)

### 4. (Optional) Vulnerability Name or ID

- [ ] Summary: 
  - Vulnerability types:
  - Tested in version:
  - Fixed in version: 
- [ ] GIF Walkthrough: 
- [ ] Steps to recreate: 
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

### 5. (Optional) Vulnerability Name or ID

- [ ] Summary: 
  - Vulnerability types:
  - Tested in version:
  - Fixed in version: 
- [ ] GIF Walkthrough: 
- [ ] Steps to recreate: 
- [ ] Affected source code:
  - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with  ...
<!-- Recommended GIF Tools:
[Kap](https://getkap.co/) for macOS
[ScreenToGif](https://www.screentogif.com/) for Windows
[peek](https://github.com/phw/peek) for Linux. -->

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.






# Extra Notes

# Previously Noted Vulnerabilities
## 1. XSS
## <xss onafterscriptexecute=alert(1)><script>1</script>
<br>
<img src="https://raw.githubusercontent.com/agalvezv/Week78Assignment/main/XSS%20Example.jpg" alt="XSS">

<br>
<br>

# Vulnerabilities
## 2. User enumeration
## wpscan –url http://127.0.0.1:8080/ –enumerate u
<br>
<img src="https://raw.githubusercontent.com/agalvezv/Week78Assignment/main/User%20Enumeration%20Example.jpg" alt="UE">

<br>
<br>

# Vulnerabilities
## 3. Password Bruteforce
## wpscan --url http://127.0.0.1:8080/ --passwords rockyou.txt
<br>
<img src="https://raw.githubusercontent.com/agalvezv/Week78Assignment/main/Enumeration%20and%20Bruteforce.jpg" alt="PB">

<br>
<br>

## Extra GIF: https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExMmY4Y2U2MTk3ZDg3ZDRlY2RiNTllOTg3N2JjYjY3NmVmZWE5NGY1OCZlcD12MV9pbnRlcm5hbF9naWZzX2dpZklkJmN0PWc/gQWJu9oZ03mDYa4dwP/giphy.gif
## Video: https://www.youtube.com/watch?v=9XydAX0R268
# Previously set to private. Now set to unlisted. 
