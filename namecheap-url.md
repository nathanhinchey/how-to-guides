#NOTE: This needs to be updated. All you need to do is put a CNAME file in your project and point at it. URL Frames are not necessary.

#Making a namecheap URL point at your github project

* Go to your namecheap dashboard
* Select the relevant domain name
* click on All Host Records
* ![All Host Records](namecheapallhost.png)
* Decide whether you want to use the main domain or a subdomain:

##Main domain
namecheap doesn't allow CNAMEs to point at urls that include a / character. In order to make it appear you have a certain root URL, you can do this:
* set the IP ADDRESS/URL column in the @ row to the target URL
* set that RECORD TYPE drop down to URL Frame
* Set the IP ADDRESS/URL column in the WWW row to point to the top level URL (if you don't want a WWW)
* set that RECORD TYPE drop down to URL Redirect
![namecheap screenshot](/namecheapurl.png)

*note: your project repo would be called `a` in this picture example; I used it so it would all fit in the frame*

##Subdomain
To make it look like a subdomain, do this in the SUB-DOMAIN SETTINGS section:
* in the HOST NAME column right what you want the subdomain to be
  * (setting mycoolproject will make the URL mycoolproject.mydomain.com)
* Put your github project URL in the IP ADDRESS/URL column
* Set the RECORD TYPE dropdown to URL Frame
![subdomain screenshot](/namecheapurlsubdomain.png)
*note: your project repo would be called `a` in this picture example; I used it so it would all fit in the frame*
