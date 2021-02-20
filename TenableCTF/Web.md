# Tenable CTF

## Web

---

### **Stay Away Creepy Crawlers**
A robots.txt file tells search engine crawlers which pages or files the crawler can or can't request from your site. This is used mainly to avoid overloading your site with requests. With that in mind, this challenge was about accessing this file. 
Connecting to `http://167.71.246.232:8080/robots.txt` the following text was presented:
```
User-agent: *
Disallow: /admin/
# flag{mr_roboto}
```
> flag{mr_roboto}


### **Source of all evil**
To get the flag for this challenge we only needed to see the source code on the website which had an html comment with the flag.
> flag{best_implants_ever}


### **Can't find it**
As the name suggests, when connecting to a page that did not exist, the 404 error returned the flag as a message.
> flag{404_oh_no}


### **Show me what you got**
The challenge text said something about indexes. That said, we searched for folders in the directory. The folder `images` was found, and when accessing it there was the `aljdi3sd.txt` file wich had the flag inside.
> flag{disable_directory_indexes}


### **Certificate of Authenticity**
Talking about authenticity, the first thing that comes to mind is `https`. Trying to access the page with `https` it showed a warning that the connection was not private. In that warning there was a link to see the certificate (in FIrefox) which had the flag in it.
> flag{selfsignedcert}


### **Headers for you inspiration**
All we had to do was to check the headers when the page is loaded (refreshing the page with the `Network` tab opened).
> flag{headersftw}