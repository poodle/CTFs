# Micro-CMS v1

* Difficulty: **Easy**
* Flags Available: **4**
* Skills: **Web**

# Flag [1/4]

## Process

After viewing all of the existing pages on the challenge, I then attempted to append the page id to see if there were any hidden pages. And low and behold, I hit 6 - the forbidden page.

![Screenshot](https://i.imgur.com/qD93Eri.png)

This was without a doubt a flag in my mind, so I knew what to now target. I then continued to create a page, and noticed that pages could be edited. 

![Screenshot](https://i.imgur.com/kFNq3rq.png)

So, in order to acess the contents of the infamous page 6, I changed the id of my new page to 6 in the ```/edit/x``` portion of the URL and boom - I was able to edit and view the contents of page 6, resulted in a flag.

![Screenshot](https://i.imgur.com/v3QbMYQ.png)

# Flag [2/4]

## Process

This next flag was kind of a lucky guess to be honest. I assumed that the page's logic was all JavaScript so the classic ```<script>alert(1)</script>``` XSS.

![Screenshot](https://i.imgur.com/v3QbMYQ.png)

And sure enough, it worked and was actually a flag!

![Screenshot](https://i.imgur.com/u8nwPbB.png)

![Screenshot](https://i.imgur.com/Jx4oj9w.png)
