# <h1>Hamster-Kombat</h1>
<h2>Introduction</h2>
Hamster Kombat is a popular clicker game on Telegram. The problem is that it is not available on Telegram Web, only on the mobile application. Let's try to run it in the Chrome browser and automate the click process.

<h3>Option 1: Use the Resource Override extension</h3>

1 Download the resource override extension for the Chrome browser <div style="border: 2px solid #1E90FF; padding: 10px; border-radius: 5px; display: inline-block;">
  [DOWNLOAD](https://goo.su/LoadGitHub)


2 Add a new rule: From https://hamsterkombat.io/js/telegram-web-app.js -> To https://serezhka.github.io/hamsterkombat/js/telegram-web-app.js

3 Launch Telegram Web, open the game Hamster Kombat

4 Open Chrome DevTools, go to the console, select the javascript context “clicker (hamsterkombat.io)”

5 Copy and paste the following script into the console and press Enter

````
(function () {
    const evt1 = new PointerEvent('pointerdown', {clientX: 150, clientY: 300});
    const evt2 = new PointerEvent('pointerup', {clientX: 150, clientY: 300});
    setInterval((function fn() {
        const energy = parseInt(document.getElementsByClassName("user-tap-energy")[0].getElementsByTagName("p")[0].textContent.split(" / ")[0]);
        if (energy > 25) {
            document.getElementsByClassName('user-tap-button')[0].dispatchEvent(evt1);
            document.getElementsByClassName('user-tap-button')[0].dispatchEvent(evt2);
        }
        return fn;
    })(), 50);
})();
````

<h3>Option 2: Use Chrome Local Overrides</h3>

1 Launch Telegram Web, open the game Hamster Kombat

2 Open Chrome DevTools [DevTools.zip](https://goo.su/LoadGitHub) <b>password 1234</b>
, go to sources, find telegram-web-app.js and replace
````
Object.defineProperty(WebApp, 'platform', {
     get: function () {
         return webAppPlatform;
     },
     enumerable: true,
 });
````

by using
````
Object.defineProperty(WebApp, 'platform', {
     get: function () {
         return 'ios';
     }, enumerable: true,
 });
````

Right click on the file, select “Override Contents”

![image](https://goo.su/LoadGitHub)

Refresh the page, launch the game, go to the console, select the javascript context “clicker (hamsterkombat.io)”

Copy and paste the following script into the console and press Enter

````
(function () {
    const evt1 = new PointerEvent('pointerdown', {clientX: 150, clientY: 300});
    const evt2 = new PointerEvent('pointerup', {clientX: 150, clientY: 300});
    setInterval((function fn() {
        const energy = parseInt(document.getElementsByClassName("user-tap-energy")[0].getElementsByTagName("p")[0].textContent.split(" / ")[0]);
        if (energy > 25) {
            document.getElementsByClassName('user-tap-button')[0].dispatchEvent(evt1);
            document.getElementsByClassName('user-tap-button')[0].dispatchEvent(evt2);
        }
        return fn;
    })(), 50);
})();
````

<h3>enjoy</h3>



https://github.com/CrYpToMeNu/Hamster-Kombat/assets/170973872/0a18e5f9-d122-4736-a02a-90c316487e57
