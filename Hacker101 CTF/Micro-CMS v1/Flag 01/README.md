# Flag [1/4]

## Process

After viewing all of the existing pages on the challenge, I then attempted to mess around with the page ID parameter to see if there were any hidden pages. And low and behold, I hit page 6 - the forbidden page.

![Screenshot](https://i.imgur.com/qD93Eri.png)

This was without a doubt a flag in my mind, so now I had my first target. I then continued to create a page, and noticed that pages could be edited. 

![Screenshot](https://i.imgur.com/kFNq3rq.png)

So, in order to acess the contents of the infamous page 6, I changed the ID parameter of my new page (in the ```/edit/x``` portion of the URL) to 6 and boom - I was able to edit and view the contents of page 6, resulted in a flag.

![Screenshot](https://i.imgur.com/v3QbMYQ.png)
