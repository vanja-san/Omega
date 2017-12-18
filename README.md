# Omega

![screenshot](https://s1.gifyu.com/images/Screenshot-1196.png)
1st theme

![screenshot](https://s1.gifyu.com/images/Screenshot-1195.png)
2nd theme

![screenshot](https://s1.gifyu.com/images/Screenshot-1198.png)
3rd theme

[Live Demo.](https://catgrills.github.io/Omega/)

About
-------------------------------

<i>Omega</i> is a startpage featuring three different themes.

A startpage/homepage is a local website, namely you'll be able to access it thanks to files present on your computer (in general, it'll be a .htm file), and some browser like Firefox Mozilla and Google Chrome will allow you to set a custom homepage. What's more, thanks to some add-ons/extensions such as 'New Tab Homepage' for FF or 'New Tab Redirect' for Chrome, you'll be able to set this said startpage as you new tab page (amazing isn't it ?). There are a lot of custom startpage on the net, you can check this list of startpage http://startpages.github.io/ or search some of them on github/deviantart. 

Instruction
-------------------------------

<strong>Step 1 : Right click on the <i>.htm</i> file and open it with a browser of your choice</strong>

<strong>Step 2 : Set the startpage as the homepage </strong>
<ul>

<p>For Mozilla Firefox</p>
<ol> 
<li> go to the settings or copy/paste <i>about:preferences</i> in the URL bar. In <i>General</i>, copy/paste the URL of the startpage (it should be something like <i>file:///C:/Users/[Your name]/Documents/OMEGA/index.htm</i> in <i>Home Page</i> and choose the option <i>Show my home page</i> for <i>When Firefox starts</i>.</li>
<li> download the add-on <i>New Tab Homepage</i> (https://addons.mozilla.org/en-US/firefox/addon/new-tab-homepage/), it'll redirect you to your homepage each time you open a new tab.</li>
</ol>
<br>
<p>For Google Chrome</p>
<ol> 
<li> go to the settings. In <i>Appearance</i>, check <i>show home page</i> and modify the link with the URL of the startpage. </li>
<li> download the extension <i>New Tab Redirect</i> (https://chrome.google.com/webstore/detail/new-tab-redirect/icpgjfneehieebagbmdbhnlpiopdcmna?hl=en). </li>
</li>
</ul>
</ol>

<strong>Step 3 : Install the font </strong>

I use several fonts for the startpage.
<ol>
<li> <a href="https://www.fontsquirrel.com/fonts/roboto">Roboto</a></li>
<li> <a href="https://www.freejapanesefont.com/kf-himaji/">KFhimaji</a></li>
</ol>

Structure
-------------------------------

<span> There are 4 differents folders and 5 files (.htm and .css). </span>
<ol>
<li>the folder <i>avatar</i> is filled with the avatars used for each theme. Each file is named <i>avatar_theme01.png</i>, <i>avatar_theme02.png</i>, <i>avatar_theme03.png</i>.</li>
<li>the folder <i>background</i> contains four subfolders themes : <i>background_01</i>, <i>background_02</i>, <i>background_03</i> and <i>misc</i>. You will find in each folder the illustrations used for each theme, and the main background in <i>misc</i>.</li>
<li>the folder <i>icons</i> contains the favicon.</li>
<li>the folder <i>js</i> has 2 javascript files.</li>
<li>the file <i>index.htm</i>.</li>
<li>3 files <i>.css</i>, namely <i>theme01.css</i>, <i>theme02.css</i> and <i>theme03.css</i>.</li>
</ol>

Features
-------------------------------

<span><i>Omega</i> has two main features.</span>
<ol>
<li>You can set 3 (or more) themes with different avatar and backgrounds. To switch between theme, you have to click one of the three circles in the header : the first theme corresponds to the first square on the left, the second the one in the middle, and the third the square on the right.</li>
<li>In the search bar, by entering some special keys, such as `-y jazz music`, you'll be able to search directly on youtube and not on Google. Another exemple with `-w moe`, it'll search 'moe' on wikipedia.</li>
</ol>

Customizing
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

Disclaimer
-------------------------------

<span>Source of the illustrations used.</span>
<ol>
<li><a href="https://www.pixiv.net/member.php?id=2525531">tokiti (ときち)</a>
<li><a href="https://www.pixiv.net/member.php?id=1225492)">くらら</a></li>
<li><a href="https://www.pixiv.net/member.php?id=598083">kotake96 (コタケ)</a></li>
</ol>

Report
-------------------------------

If you find some issues or bug when using this stratpage, don't hesitate to report it in the comments.
