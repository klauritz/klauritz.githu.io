---
layout: essay
type: essay
title: "Six Changes to Techfolio Designer"
date: 2018-08-2
labels:
  - Electron
  - ICS 391
---
# Introduction

To get used to working on developing the Techfolio Designer application, I was tasked with making 6 small changes to the current state of the application. This article will go over what files have been changed, what I learned about the system, and what problems I had and my solutions.

# 1. Change Background Color of Splash Page

For this assignment, I was tasked with changing th backgroud color of the splash page to light grey.

### Files Changed

`src/splash/SplashPage.html`

### What I Learned

I learned about the location of the splash page and how to style the html of the window.

### Problems Encountered

When expanding the window, I noticed that the light-grey background didn't extend to fit the whole window. I added `height: 100%` to the in-line styling to resolve the issue.

![Figure 1: Changing the Background Color][figure1]

# 2. Add "last modified" Timestamp to Splash Page

### Files Changed

`src/splash/SplashTable.jsx`

### What I Learned

I learned how to add an additional table, as well as how to use Moment.js with `moment().format('hh:mm:ss a')`. Looking at the Moment.js documentation showed me a lot of ways that this can be useful. It was also interesting to figure out when the table is updated. I found out that changing the time whenever the `mapStateToProps` function is called worked.

### Problems Encountered

For a while, whenever I used Moment.js functions, my Last Modified section wouldn't work. I found out that the format I was using was invalid, and I switched to using `hh:mm:ss a` instead and that fixed my problem.

![Figure 2: Add 'Last Modified'][figure2]

# 3. Add Menu Item to Config Menu

### Files Changed

`src/main/ConfigSubMenu.js`

### What I Learned

I learned how to build an additional button in the sub-menu and implementing a function to that menu. I wrote a simple function that would use `dialog.showMessageBox()` to show the time using `moment().format('hh:mm:ss a')` every time that the new menu item is clicked.

### Problems Encountered

I had trouble implementing `dialog` and importing it. I would get an error saying that dialog was not defined, but I eventually read that I had to import it like `import { dialog } from 'electron'` and when I did that, the application worked as desired.

![Figure 3: Add Menu Item to Config Menu][figure3]

# 4. Add Simple Validation to Set Github Repo Name

### Files Changed

`src/main/ConfigSubMenu.js`

### What I Learned

I learned how to take an input from a user prompt, as well as compare it and validate it. I also tried using a different dialog method, the `showErrorBox` instead of the Message Box. This one was much simpler to use. 

### Problems Encountered

Initially, I didn't know where to start on this one. I took a while searching the files for where to implement the validation, as well as where the program is requesting the input from the user. I eventually just took an educated guess and started working on the function called `setRemoteRepo()`. It ended up to be the correct location to put the validation and the application successfully validated the repo names I inputted.

![Figure 4: Simple Validation to Set Github Repo Name][figure4]

# 5 Allow Four Networks in the Simple Bio Editor

### Files Changed

`src/simplebioeditor/SimpleBioEditorTabNetwork.jsx`

### What I Learned

I first had to learn how to increase the Grid size of the Networks tab to accomodate an additional network input. After that, I implemented additional fields (network, username, url) in the entry consts and the tab then worked as desired.

### Problems Encountered

There weren't any problems encountered for this one. I found the task to be straightforward and I luckily didn't come acroess any complications.

![Figure 5: Four Networks][figure5]

# 6. Perform Simple Validation on Project and Essay Files

### Files Changed 

`src/techfolioeditor/TechFolioEditor.jsx`

### What I Learned

As I am taking ICS 314 concurrently, I actually did not know how to find regular expressions, or how to use regex. I read up a lot on it and used it to check the date format of the essays. I also learned how to get the string value of the essays by using `string`.

### Problems Encountered

The tricky part was finding out how to get the text from the essay file. I experimented a little and found out that `this.state.value` would return a string of the contents in the file. This was the first step. The other problem I had was trying to get a notification to pop up using `dialog.showMessageBox()`, but instead I opted to use the Node Notifier package to handle the notification.

![Figure 6: Simple Validation on Project and Essay Files][figure6]

# Conclusion

This assignment took a lot of thinking and time. It was frustrating at times to see that the problems that I spent so much time on ended up having a short and concise solution. Regardless, I learned a lot from this assignment, as it required me to dig into the applications code and try to understand a good portion of it. I look forward to learning a lot more as this course progresses.

[figure1]: https://klauritz.github.io/images/ics491-p1.png "Changing the Background Color"
[figure2]: https://klauritz.github.io/images/ics491-p2.png "Add 'Last Modified' Timestamp"
[figure3]: https://klauritz.github.io/images/ics491-p3.png "Add Menu Item to Config Menu"
[figure4]: https://klauritz.github.io/images/ics491-p4.png "Add Simple Validation to Set Repo Name"
[figure5]: https://klauritz.github.io/images/ics491-p5.png "Allow Four Networks in Simple Bio Editor"
[figure6]: https://klauritz.github.io/images/ics491-p6.png "Perform Simple Validation on Project and Essay Files"
