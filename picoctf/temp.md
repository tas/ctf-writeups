# PicoCTF Writeups

## GET aHEAD
![image](https://github.com/tas/ctf-writeups/assets/5200537/65bb750e-b763-4911-90a8-76d1e8c87047)
<details>
  <summary>Hints</summary>

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

![image](https://github.com/tas/ctf-writeups/assets/5200537/b133fc5a-0d04-4982-b16f-e61a087c321f)

And with that, we get the flag.




























## Filler Title
### Filler Header
Filler Text. Filler Text. Filler Text. 
