# GOOGLE HACKING / DORKING 

* [What is dorking?] (# What-is-dorking?)
* [Importance] (# Importance)
* [Basic concepts] (# Basic-concepts)
* [How to use this in hacking?] (# How-to-use-this-in-hacking?)
* [Examples of dorks] (# Examples-of-dorks)
* [Dorks for sql and xss injection] (# Dorks-for-sql-and-xss injection)
* [Dorks to find cameras] (# Dorks-to-find-cameras)
* [OSINT and DORKS] (# OSINT-y-DORKS)
* [Final importance] (# Final-importance)


## What is dorking?

Google hacking or Dorking is nothing more than a way to search for things a little more specialized,
The name "Google Hacking" gives the impression that it is only used in google, but that is not correct.
Dorking is nothing more than an advanced search where we use operators that work as a filter
To direct the search directly to where we want, we also use symbols to search for exact words or phrases.
This will help us to search almost any search engine that we find on the internet.

## Importance

Knowing a little "Dorking" helps us in many aspects of our life, it is not just to search for vulnerable pages
remember that the term "Hacking" is first used when a person has mastered something to such a degree
who can see things from other points of view and thus get to see or achieve things that other people cannot,
If we get out of computer science a bit, we can use an example.

A mechanic who has worked with cars for years and specializes in engines, he eventually understands 
much better engine problems than any other mechanic, having much more experience on the subject,
You can tell that he is a "hacker" in mechanics by coming to know that.

Returning to the subject of Dorking it is very important that all people know a little about this, in this writing it will be about 
explain in as much detail as possible how to start and if you already know something about this you can reinforce basic themes.

## Basic concepts

As explained before, these advanced searches use operators and symbols, such as the following: 

Let's start with some very common operators:



* site: only searches for results within the web that goes after "site:"

      Example: site: www.google.com 
      This search will only show us results from the Google page 
      
* intitle or allintitle: This will only search the titles 
      
      Example: intitle: "Google dorking"
      This search will show us only articles that have the phrase "google dorkin" in their title
      
* inurl or allinurl: the results will be in the url of the pages 

      Example: inurl: /parameter.php?id=
      This search will show us page results where they contain "/parametro.php?id=" in their url.
      
      Note: This can be confused a bit at the beginning with the operator "site" because if we do not express well
      what we want to find and we put a website, it will show us the same result as the "site" operator.
      
      Remember that a link or url has the following syntax depending on whether the administrator of the page
      configured or not the links to be more friendly.
      
      Site with unfriendly links:
      `http / s: //www.examplewebsite.com/parameter1.php? id = 1 & parameter2.php? id = 22`
      
      Site with friendly links:
      `http / s: // www.examplewebsite.com / example`
      
* filetype or ext: only searches for files (doc, xls, txt ...) 
        
      Note: This operator is accompanied by one of the ones we have just seen.
      Example: site: www.paginaweb.com filetype: .pdf
      This search will show us the .pdf files that are "loose" or that are filtered on the net from the page www.paginaweb.com 
      
* related: searches for websites related to a certain one.
        
      Example: relates: www.google.com 
      It will show us pages similar to google, that is, it will show us other search engines
      
* cache: shows the result in the Google cache of a web page.
      
      Example: cache: www.google.com
      It will show us the web page saved in the google cache
      
* define: search word definitions

      Example: define: linux
      It will show us results where it is defined that it is linux
      
* Allintext or intext: it will look for the exact phrase that we put

      Example: Allintext: abcdefghijklmnopqrstuvwxyz
      It will show us pages where the alphabet comes from 
     
* weather: it will show us the weather of the part of the world that we want to see 

      Example: weather: Mexico
      It will show us the climate of Mexico City 
      
* stock: will show us financial information 

      Example: `` ``
               stock: TSLA
               stock: goog
               `` ''
      This will show us the financial information of the stock market 
      
* link: shows us the pages where the page we are looking for is linked 

      Example: link: www.youtube.com
      It will show us all the pages that link any youtube link on your page 
      
Now we are going to see some very important symbols:

* ”” (Quotes): search for exact phrase
       
      Example: "alert (Y000!)"
      In this case I am looking for my own nickname or my Twitter nick 
      
* `+ and -`: include or exclude any word

      example: animals -dogs
      This results in many pages that talk about animals but tries to exclude all the pages that talk about dogs
      
* `*` (asterisk): wildcard, any word, but a single word.
      
      Example: site: *. Google.com
      Which will show us all the google pages including their subdomains.
      
      
## How to use this in "hacking"?      

First of all, we have to be very clear about what we want to achieve, what we are going to look for and what we want to find.

In order to start Google hacking, seeing from a perspective where we want to find "information" that not everyone can find, we have to know
files that contain that information, we have to know the systems on which a web page is based, we have to be aware of everything a little. 

The first example we are going to see is how to find the "robots.txt" file, but first to find that file we have to know: What is it? What does it contain?
Why do the pages use it? We cannot search for something just by looking for it without knowing what it is.

The "robots.txt" file is for easy indexing of a website. This file is used to instruct the robots on what content they should and should not crawl and how they should do it. In easier words, this file is used to make the web page "safe" from google searches, since in the file come the pages that the administrator does not want to be seen in the google results, come on, that's how to exclude the pages not to be found.

This specific file is written as follows: 

`` ''
User-agent: *


Disallow: / example /
Disallow: / 1 / example /
Disallow: / 2 /
Disallow: / example2 /
Disallow: / example3 /
Disallow: / 3 / example4
Disallow: / I do not want to be seen
Allow: / I_if_want_ to be seen
Allow: / me_also

`` ''
It is used in the following way in the link of the page:

`https: // www.examplepage.com / robots.txt`

With which we have many ways to find it, for example ... we know where it is in the link, we know that it is used in the url:

we can do a search like the following:

`inurl: robots.txt` but this will show us very general results and it might find the file or something related to it

This is when we are going to actually use the operators, we are going to mix them up for best results:

Using the operator "site" + "inurl" and the symbol `*` we make the search much more specific:

`site: www.google.com inurl: robots.txt` with this we focus that the search is on the google page, and voila! gives us as a result: https://www.google.com/robots.txt

but if we want to make the search much more specific we can use:

`site: *. com.mx inurl: /robots.txt intext:" User-agent: "`

In this case we are reducing the results to only pages that have the domain .com together with .mx ".com.mx" which means that we are looking for pages
Mexicans since the .mx domain belongs to pages hosted in Mexico, when finding those pages the inurl operator: /robots.txt is applied, which reduces even more 
Pages found only those that contain the word "robots.txt" in their url, finally enter intext: "User-agent:" to further reduce the previous results 
and verifying that the pages found before have the word "user-agent:" in them, now we can ensure that the pages we find will show us the
robots.txt file for each page.

That's just one example of how to use operators to find cool stuff.

On the other hand, we can also focus on looking for pages that are made in a specific CMS, for example WORDPRESS, this has been characterized by being very comfortable to work in and quite easy since it contains many plugins that can be very helpful, but at the same time these plugins can come with many flaws that allow someone else to exploit various vulnerabilities. 

To find pages created in WORDPRESS, first we have to know a little about it, its basic structure of files and folders, the most important files ... etc, here I am going to try to explain a little to better understand why it is important to know that:

WORDPRESS uses the following structure in its url: 

`https: // yourdomain / wp-admin or https: // yourdomain / wordpress / wp-admin or https: // yourdomain / wp / wp-admin`

Your top important folders and files:
`` ''
* wp-admin: Folder where the WordPress back-end files are saved, this part of the installation is never modified.

* wp-content: It is the folder where all the content is saved in file format (not database)

* wp-includes: It is a folder of files that WordPress needs to work, its API and the main libraries are in this folder that is never modified either.

* index.php: it is the main file accessed and from where the rest of WordPress parts are loaded.

* wp-config-sample.php: This file is the template of what will finally be the WP-CONFIG.PHP file after the CMS installation

* xmlrpc.php: This is a file that offers communication through the XMLRPC.PHP protocol, WordPress currently receives many attacks through this file, so it is important to emphasize its security and protection.

* wp-login.php: It is a very important file, since it is the one in charge of managing the login of users, both normal users and administrators. 
`` ''

Now, with that in mind, we already have an idea of ​​how to find pages created in wordpress using dorking:

We know how wordpress behaves to create its url, to find pages we can use the following:

`inurl: / wordpress / wp-content`
`inurl: / wordpress / wp-admin`
`inurl: / wordpress / wp-includes`

Here we are looking directly for a folder in the wordpress directory using inurl, which will show us many pages where we will access (if we have the permission) directly to the wordpress files.

## dorks examples

In this part I will use as a complement a thread from my own twitter account where I have published many dorks that I find interesting and we will analyze some of them here:

The first one we are going to use will be:

inurl: wp-config.php intext: DB_PASSWORD -stackoverflow -wpbeginner -forum -forum -topic -blog -about -docs -articles

`https: //twitter.com/_Y000_/status/1205400779957440512? s = 20`

This dork allows us to find pages created in wordpress and we are looking specifically for the wp-config.php file, then we use intext: DB_PASSWORD to filter the results where that word is found, which is to find database configurations, we find information like: users, password, database name ... etc, very important information that should not be visible to any person, finally we have words with a "-" that means that we are excluding those words from our search.


Another very interesting dork is the following:

intitle: "Index Of" intext: "iCloud Photos" OR intext: "My Photo Stream" OR intext: "Camera Roll"

`https: //twitter.com/_Y000_/status/1205647749372203010? s = 20`

In this example we use intitle: "index of" which is to find directories within the web page, that means that we are looking for pages that contain a list of directories inside, normally these are not visible, then we are filtering the results between several intext and OR which means that we are looking for any of those 3 phrases.

In this case we are looking for vulnerable iCloud devices, with which we can see all the photos that are being shared. This dork can be modified to find different things.

But not only do we use the dorks to find folders or files, we can also find servers running a service: 

intitle: "Welcome to JBoss"
inurl: "8080 / jmx-console"

`` ''
https://twitter.com/_Y000_/status/1232415430876090368?s=20
https://twitter.com/_Y000_/status/1220447109842984963?s=20
`` ''
With those dorks we can find servers running the Jboss system. 

## Dorks for sql and xss injection

Dorking is closely related to sql and xss injections, as many hackers make use of dorks to find vulnerable pages. If you want to delve a little more into sql injections, I recommend that you go through this writing that I also created and focuses on that:

https://github.com/Y000o/sql_injection_basic/blob/master/sql_injection_basic.md

In this writing I try to explain in a very detailed way the bases for an sql injection either manually or automatically using tools.

Returning to the topic, making use of some dorks makes it easier to search to find pages vulnerable to sql and xss injections, some are: 

`` ''
specials.cfm? id =
store_listing.cfm? id =
store.cfm? id =
store_bycat.cfm? id =
storefront.cfm? id =
Store_ViewProducts.cfm? Cat =
store-details.cfm? id =
StoreRedirect.cfm? ID =
storefronts.cfm? title =
storeitem.cfm? item =
subcategories.cfm? id =
tuangou.cfm? bookid =
 
tek9.cfm?
template.cfm? Action = Item & pid =
topic.cfm? ID =
type.cfm? iType =
view_cart.cfm? title =
 
updatebasket.cfm? bookid =
updates.cfm? ID =
view.cfm? cid =
view_detail.cfm? ID =
viewitem.cfm? recor =
 
viewcart.cfm? CartId =
viewCart.cfm? userID =
viewCat_h.cfm? idCategory =
viewevent.cfm? EventID =
WsAncillary.cfm? ID =
 
viewPrd.cfm? idcategory =
ViewProduct.cfm? Misc =
voteList.cfm? item_ID =
whatsnew.cfm? idCategory =
WsPages.cfm? ID = HP
inurl: ". php? cid =" + intext: "online + betting"
 
inurl: ". php? cat =" + intext: "Paypal" + site: UK
inurl: ". php? cat =" + intext: "/ Buy Now /" + site: .net
inurl: ". php? id =" intext: "View cart"
inurl: ". php? id =" intext: "/ store /"
 
inurl: ". php? id =" intext: "Buy Now"
inurl: ". php? id =" intext: "add to cart"
inurl: ". php? id =" intext: "shopping"
inurl: ". php? id =" intext: "boutique"
inurl: ". php? cid =" intext: "Buy Now"
 
inurl: ". php? id =" intext: "/ shop /"
inurl: ". php? id =" intext: "toys"
inurl: ". php? cid ="
inurl: ". php? cid =" intext: "shopping"
inurl: ". php? cid =" intext: "add to cart"
inurl: ". php? cat ="
 
inurl: ". php? cid =" intext: "View cart"
inurl: ". php? cid =" intext: "boutique"
inurl: ". php? cid =" intext: "/ store /"
inurl: ". php? cid =" intext: "/ shop /"
inurl: ". php? cid =" intext: "Toys"
inurl: ". php? cat =" intext: "/ store /"

`` ''
## Dorks to find cameras

We can also find cameras in which we can enter

`` ''
inurl: /sample/LvAppl/lvappl.htm
allinurl: control / multiview
intitle: ”Live View / - AXIS"
`` ''

## OSINT and DORKS

Using Dorks we can also focus on OSINT, which is a set of techniques and tools to collect public information.

to search for names: 
`` ''
"Name" site: web page

"Name" site: http: //instagram.com

`` ''

usernames:

`` ''
inurl: username site: page

allinurl: username site: page
`` ''

Search for information about a web page, obtain pages related to it and all its subdomains:

`` ''
Searches on a web page:
site: http: //example.com

Similar pages:
related: http: //example.com 

Subdomains:
site: *. example.com -www
`` ''

Emails: 

`` ''
These will help us to collect emails from different web pages:

"
@example
.com ”site: page

HR "email" site: page filetype: csv | filetype: xls | filetype: xlsx

site: http: //example.com intext:
@gmail
.com filetype: xls

`` ''

an extra by @ pedr4uz:

`https: //twitter.com/pedr4uz? s = 20`

`` ''
"person_name" intext: cpf AND filetype: pdf

derived -> "person_name" intitle: approved + intext: cpf AND filetype: X
`` ''
# Final importance

As we were able to appreciate in this writing, knowing Dorking well opens up a world of possibilities, a world where it is easier for us to find information that anyone else would not find easily, by understanding this use of specialized searches well, we have a lot power, that is why it is good and I would like to make it very clear, much of the information we can find may be that it is protected and therefore we can get in trouble if we access without permission. Everything learned in this article is purely for educational purposes, whatever use they want to give is the decision of each one.
