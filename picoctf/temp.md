# PicoCTF Writeups

<br />

## GET aHEAD
#### https://play.picoctf.org/practice/challenge/132
![image](https://github.com/tas/ctf-writeups/assets/5200537/65bb750e-b763-4911-90a8-76d1e8c87047)
<details>
  <summary>PicoCTF Hints</summary>

  ```markdown
  1. Maybe you have more than 2 choices
  2. Check out tools like Burpsuite to modify your requests and look at the responses
  ```
</details>

### Solution
When opening the website, we're greeted with two buttons to choose 'red' or 'blue', changing the page's background.

Let's take a look at the source code. (CTRL + U)

![image](https://github.com/tas/ctf-writeups/assets/5200537/687eabc0-2edf-469a-a36b-74a7d7f10650)

The biggest thing to note is that different HTTP requests are sent for each color, ```GET``` for red & ```POST``` for blue.

Let's intercept a request into BurpSuite & take a closer look;

![image](https://github.com/tas/ctf-writeups/assets/5200537/f22b53ae-89b7-4e06-8016-6c5c7b162be7)

Using a [list of HTTP request methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods), we can try different requests to see if different hidden colors exist.

Given the name of the CTF, a ```HEAD``` request seems applicable.

![image](https://github.com/tas/ctf-writeups/assets/5200537/59f44119-8eb9-416f-bdf2-f9bf482cfb0a)

As expected, the ```HEAD``` request returns the flag in the response.
<br />

<br />

<br />

## Cookies
#### https://play.picoctf.org/practice/challenge/173
![image](https://github.com/tas/ctf-writeups/assets/5200537/50e635b7-dde8-4086-9629-969bc567420a)
<details>
  <summary>PicoCTF Hints</summary>

  ```markdown
  None.
  ```
</details>

### Solution

Biggest things that stand out when first opening the page are the cookie references & the searchbar.

![image](https://github.com/tas/ctf-writeups/assets/5200537/60ab099b-40f5-4819-8eb4-fabfb142b25f)

We can assume the main point of this CTF is cookie related, so lets put some information in the searchbar and intercept with BurpSuite.

![image](https://github.com/tas/ctf-writeups/assets/5200537/6001eb6c-5766-4c7a-a031-fcb3a72d4d01)

We get an invalid cookie error, however BurpSuite lets us change that. 

Let's change our ```-1``` cookie to something other than a negative number.

![image](https://github.com/tas/ctf-writeups/assets/5200537/b3d6d645-9466-4ff9-9850-7bc0933eba59)

Setting ```Cookie: name``` to ```3``` gives us a success message, but states "Not very special".

Let's iterate through these cookies (using BurpSuite's repeater) and see if we find anything informative.

![image](https://github.com/tas/ctf-writeups/assets/5200537/dc13ebf8-bbd4-4c2e-b260-6052db4d26da)

Setting ```Cookie: name=``` to ```18``` gives us our flag.










## Filler Title
### Filler Header
Filler Text. Filler Text. Filler Text. 
