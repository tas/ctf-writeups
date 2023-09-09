# PicoCTF Writeups

<br />

## GET aHEAD

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
