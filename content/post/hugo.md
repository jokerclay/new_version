---
title: "Hugo"
date: 2021-09-16T09:18:18+08:00
draft: true
---

# 1. install hugo

```
sudo apt-get install hugo 
```

output

```
sudo apt-get install hugo                                                         
[sudo] password for clay: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
hugo is already the newest version (0.82.1-1).
The following packages were automatically installed and are no longer required:
  libapache2-mod-php oracle-instantclient-basic python3-qrcode
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 1298 not upgraded.

```



# 2. create a new site

```
hugo new site blog
```

output

```
Congratulations! Your new Hugo site is created in /home/clay/Documents/hugo/blog.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.
                                                                               
```



# 3. site's basic structure

```
cd blog
tree blog
```

output

```
.
├── archetypes
│   └── default.md
├── config.toml
├── content
├── data
├── layouts
├── static
└── themes

```



# 4. get a theme

## (1) go to hugo gallery   https://themes.gohugo.io/

## (2) choose a theme you like 

### I choose this dark theme    https://github.com/guangmean/Niello



## (3) go to the themes folder and clone it 

```
cd themes
```

```
git clone https://github.com/guangmean/Niello.git
```

output

```
git clone https://github.com/guangmean/Niello.git   
Cloning into 'Niello'...
remote: Enumerating objects: 282, done.
remote: Total 282 (delta 0), reused 0 (delta 0), pack-reused 282
Receiving objects: 100% (282/282), 1.17 MiB | 149.00 KiB/s, done.
Resolving deltas: 100% (135/135), done.

```

```
ls    Niello
```



# 5. set theme

## use any text editor you like ,change the `config.toml` file

**before**

```
baseURL = "http://example.org/"languageCode = "en-us"title = "My New Hugo Site"
```

**after**

note :  the following a block of code is getting from the theme's README file, 

if you use a different theme, you may want to read the readme file of the theme you choosed, then change a little as you need.



```
baseURL = "https://blog.clayliu.com/"languageCode = "cn"title = "Clay's Blog"theme = "Niello"staticDir = ["static", "themes/Niello/static"][params]keywords = ""description = ""copyright = "&#xA9; 2021 by clayliu. All Rights Reserved."sharethis = ""[menu]    [[menu.niello]]    name = "Home"    url = "/"    weight = 1    [[menu.niello]]    name = "Contact"    url = "/post/contact/"    weight = 2
```





# 6. run the website in the dev env

```
hugo server -D                                                                                             
port 1313 already in use, attempting to use an available port
Start building sites … 

                   | EN  
-------------------+-----
  Pages            |  4  
  Paginator pages  |  0  
  Non-page files   |  0  
  Static files     | 14  
  Processed images |  0  
  Aliases          |  1  
  Sitemaps         |  1  
  Cleaned          |  0  

Built in 7 ms
Watching for changes in /home/clay/Documents/hugo/blog/{archetypes,content,data,layouts,static,themes}
Watching for config changes in /home/clay/Documents/hugo/blog/config.toml
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:33323/ (bind address 127.0.0.1)
Press Ctrl+C to stop

```



**the default port is 1313, if it is already in used, hugo will change the port and you will see it in the log ** `Web Server is available at http://localhost:33323/ (bind address 127.0.0.1)`

**if you run into some error or the page  check if  you write `theme = "theme's_name"`** in your `config.toml` file


# hugo deploy



