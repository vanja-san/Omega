# Omega

![screenshot](http://i.imgur.com/sqznDsp.jpg)
Enter a fantasy world with tanks, magic, succubus.

![screenshot](http://i.imgur.com/jyBp3sJ.jpg)
Taste some epileptic shit.

![screenshot](http://i.imgur.com/Y6e0TGh.jpg)
Travel in your dreams and subconscious.

What's a startpage/homepage ?
-------------------------------

It's a local website, namely you'll be able to access it thanks to files present on your computer (in general, it'll be a .htm file), and some browser like Firefox Mozilla and Google Chrome will allow you to set a custom homepage. What's more, thanks to some add-ons/extensions such as 'New Tab Homepage' for FF or 'New Tab Redirect' for Chrome, you'll be able to set this said startpage as you new tab page (amazing isn't it ?). There are a lot of custom startpage on the net, you can check this list of startpage http://startpages.github.io/ or search some of them on github/deviantart. 


What's the structure of 'Omega' ?
-------------------------------

There are 4 differents folders and five files (.htm and .css) : 
- the first folder `avatar` is filled with the avatars used for each theme, they're named `avatar_theme01.png`, ..., `avatar_theme03.png`.
- the second folder `background` contains the three themes I used, you will find in each folder (`theme01`, `theme02` and `theme03`) six backgrounds.
- the `icons` folder has the icons I used, there is only one file : the favicon (ie the icon in the tab).
- the `js` folder is very important since you'll have to edit some files to change the weather location or modify some functionalities.
- the `index.htm` file is the most important file since you'll need it to open the startpage on your browser, if you want to change the structure of the startpage you'll have to edit it.
- the three `.css` files (`theme01.css`, theme02.css` and theme03.css`) are also necessary since they'll allow you to have different custom themes.
- the `.css` file will be needed if you want to change the aspect of the startpage, namely the background, the font-family, the size of a picture, etc.


Features of 'Omega'
-------------------------------

There are two main features :
- first, you can set three (and even more) themes with different avatar and backgrounds, to change a theme, you can click one of the three squares in the search bar, the first theme corresponds to the first square on the left, the second the one in the middle, and the third the square on the right.
- second, in the search bar, by entering some special keys, such as `-y jazz music`, you'll be able to search directly on youtube and not on Google. Another exemple with `-w moe`, it'll search 'moe' on wikipedia. I took the code from another existing startpage, but can't seem to remember it now, will put the credits the moment I found it.

How can I customize 'Omega' ?
-------------------------------

### TITLES & LINKS :
- open the `.htm` file in a text editor (personally I use Sublime), search for `http://link1.com/` and replace it with the URL of the said site (if we take Facebook, it'll be `https://www.facebook.com/`).
- you'll have to do the same thing for your favorites links on the sidebar, search for `http://fav1.com/` and replace the URL. Change the string `FAV1` with the name of the said site.

### THEMES :
- if you want to edit the themes available, first of all open the `background` folder and replace the six backgrounds by the ones you want (be sure to rename them correctly, ie `background01.png`, ..., `background06.png`).
- then, open the `avatar` folder and replace the avatar of the theme you edit with the one you want : if you edited the second theme, you'll have to rename your avatar `avatar_theme02.png`.
- you'll notice that when you hover one of the background in this startpage, there'll be a transparent color div, you'll have to enter the color code for each background you used (unfortunately for you!). To do that, open `theme01.css` in a text editor and edit the value of `background` for every `#picture[number between 1 and 6]:before`. For example, if I want to have a black div when hovering the first background, I will have the following code : 

``` javascript
#picture1:before {
	background: rgba(0,0,0,.5);
}
```
the first three numbers are the RGB values (you can find them on GIMP, PS, or you can use Google), and the last value correspond to the transparency value (0 means that the div will be completely transparent, on the contrary 1 means that the div won't be transparent).

- you can also change the value of bakground of the element `.main` which is simply the background of the box (you can see it next to the sixth background).
- if you want to add a fourth theme, you'll have to create a new folder called `theme04` in the `background` one and fill it with six backgrounds. Plus, add a picture called `avatar_theme04` in the `avatar` folder, otherwise there won't be an avatar and it'll be a bit ugly (in my opinion).
- after that, create a file called `theme04.css` and open it in a text editor. Open one of the others `.css` file, for instance `theme01.css`, and copy/paste its code in `theme04.css`.
You'll have to change the value of every elements :

``` javascript 
.avatar {
	background-image: url("avatar/avatar_theme04.png") !important;
}
```

``` javascript 
#picture1 {
	background-image: url("background/theme04/background01.png") !important;
}
```
same thing for the others `#picture[number between 1 and 6]`. And don't forget to change the value of `background` for the elements `#picture[number between 1 and 6]:before` and `.main`

- next, you'll have to open `index.htm` in a text editor and add the following code :

``` javascript 
<button onclick="swapStyleSheet('theme04.css')" id="fourth_btn"></button>
```

after 


``` javascript 
<button onclick="swapStyleSheet('theme03.css')" id="third_btn"></button>
```

- finally, open `style.css` in a text editor and add the following code (the default background value is black, you can change it for another color) :

``` javascript
		#fourth_btn {
			background: #000000;
		}
``` 

- you can also change the color of the squares for each theme, you'll have to edit in `style.css` the value of `background` for the element `#first_btn`, `#second_btn` and `#third_btn`.

### SEARCH 
- open the `js` folder and edit `search.js` in a text editor , you'll have to modify the following code 
``` javascript
case "-u":
query = query.substr(3);
window.location = "https://userstyles.org/styles/browse?search_terms=" 
break;
```
- first, you have to decide of a website, I will take `bato.to and a special key for this said site, I will take -b, thus you'll have the following code

``` javascript
case "-b":
query = query.substr(3);
window.location = "https://userstyles.org/styles/browse?search_terms=" 
break;
```
- after that, you'll need to replace the value of `window.location`, in the example of batoto you'll have to go to the site and search for something, for example if I'm looking for Hinamatsuri (a pretty gud manga, you should read it asap), the link will be `http://bato.to/search?name=Hinamatsuri&name_cond=c`, you'll have to copy the link before 'Hinamatsuri', namely `http://bato.to/search?name=`, and you'll have the following code 

``` javascript
case "-b":
query = query.substr(3);
window.location = "http://bato.to/search?name=" 
break;
```
How to use 'Omega' ?
-------------------------------
First of all, right click on the `.htm` file and open it with a browser of your choice.

### FOR FIREFOX MOZILLA
- go to the settings or copy/paste `about:preferences` in the URL bar. In `General`, copy/paste the URL of the startpage (it should be something like `file:///C:/Users/[Your name]/Documents/SPIRIT/index.htm` in `Home Page` and choose the option `Show my home page` for `When Firefox starts`.
- download the add-on `New Tab Homepage` (https://addons.mozilla.org/en-US/firefox/addon/new-tab-homepage/), it'll redirect you to your homepage each time you open a new tab.

### FOR GOOGLE CHROME
- go to the settings. In `Appearance`, check `show home page` and modify the link with the URL of the startpage.
- download the extension `New Tab Redirect` (https://chrome.google.com/webstore/detail/new-tab-redirect/icpgjfneehieebagbmdbhnlpiopdcmna?hl=en)

Before using the startpage, I suggest you to :
- download the font I used, namely `Roboto` (https://www.fontsquirrel.com/fonts/roboto) and `Meiryo`, they're free, lucky you !

Source and Credits
-------------------------------
The background and avatar used are from three artists :
- lack : http://www.pixiv.net/member.php?id=83739
- gashi-gashi : www.pixiv.net/member.php?id=5447&lang=en
- yktmr10 : http://www.pixiv.net/member.php?id=9127068

Where can I find you works ?
-------------------------------

I have a deviantart page : nicknameisfortheweak.deviantart.com

And that's it, I hope you'll enjoy this startpage if you see this submission ! Like usual, if you find this startpage cool or bad, if you have questions, suggestions, there is a section called 'Comments', you can use it everytime !
