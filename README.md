# SPELLING SLOTH
#### Video Demo:  <a href="https://www.youtube.com/watch?v=QCqkPZuwhIU" target="_blank">Watch a demonstration of the app here</a>
#### Description:

#### Overview and features

For my final project I have created a website to encourage young kids to practice spelling and times tables. It is aimed at ages 4 - 9 years. To make it engaging for children of this age, there are two mascots; Sammy, Spelling Sloth and Mikey, the Math Monkey. They provide instructions to learners, and congratulate them for correct answers. In addition, learners earn a point for each correct answer. Once enough points have been earnt, they earn a sticker. For spelling, there are 8 stickers to collect. The words are grouped by length of word, from 3 - 10. For times tables, there are 11 stickers, one for each times table, from 2 - 12.

#### Details

In a templates folder, there are html pages for stickers, times tables, spelling, registering, logging in and an index (welcome page). The backend of the website is programmed in python, using an app.py file. Dictionaries are used to store and retireve words and times tables questions. Flask is used to run the web application. Werzeug security is used to create a hash from the users' password. User details are stored in a database, using Sqlite3. The database also contains tables for tracking points earned by correctly answering spelling and maths quesitons. 

Mirriam Webster dictionary API is used to pull definitions for each word in the spelling questions. The definition is displayed on the html page, to help learners understand the word they are spelling. Learners can listen to audio recordings of each word. These are recordings were made by my wife and daughter. All audio is stored in a folder, and the mp3 links can be accessed through a dictionary (keys,values).

CSS files from Bootstrap are used to design the web pages. Javascript is used to control content, depending on certain conditions, such as whether the user is logged in or whether their answer is correct or incorrect. BootstrapLumen.css was downloaded from their website and is used as the basis for the website's design, including the style of the navbar and buttons. I edited this css file to make adjustments to some of the fonts. I also added my own style.css file. 

The spelling page uses an API (Merriam Webster) to search and retrive data for each word. A dictionary, words.py, written be me, contains a list of words, grouped by word length. The user can select which group to practice. App.py then randonly selects a word from the respective dictionary in words.py. The key, value is a link to an audio file (mp3), of a voice stating the word. The recordings were made by my wife. For the definition, the API retrieves this from Mirriam Webster. It is displayed next to the audio player. When the user types in their answer, Sammy the Spelling Sloth will present either a green box, congratuling them, or a red box telling them is it incorrect.

The maths page allow users to select times tables, from 2 to 12. Once selected, a question will appear. Learners are required to type their answer into an input text box. As with the spelling page, a mascot (Mikey the Maths Monkey) will tell the user whether they are correct or not. The questions are stored in times table lists, in a document called time_tables.py.

The stickers page uses for loops and if statements to read through the sql database and check how many points have been earned. This determines which stickers will be shown on the page. If a user has not achieved enough points, the sticker will be displayed as a sillouette. The user can see how many stickers they need and can look forward to filling in the sillouette with the actual sticker. Each sticker states how many points are needed, and how many the user currently has. It also states which group of questions they need to complete to earn points for that sticker (eg, 3 x timetables or 3-letter words).
Jinja is used to send data from app.py to the stickers page. Using the relevant syntax on the stickers page (curly brackets), the webpage will either display images from the silluette folder or from the images folder.

The app.py document manages the backend of the site. It uses functions with GET and POST to retrieve information and submit forms. This code allows the user to register an account, login, view their collected stickers and view spelling and timetable pages.Werkzeug security library is used to hash passwords. SQL is used to store a database of users details; username, age and hash. When a user logs in Flask_session is used to  keep track of the user id. @login_required is necessary to veiw certain pages, such as the stickers page. The login.html code include type="password" for the password input box. This ensures the digits are displayed as dots, to help with security. 
In order to manage the maths page, a tempTables.txt file is opened and written to when ever a question is presented. If the user answers incorrectly, the maths page will present the same question again, instead of randomly selecting a new one. This is to ensure the user can keep practicing questions they get wrong. The same is done fo spelling.
If statements and for loops are used throughout.
Imported libraries include requests, flask, sqlite3 and werkzeug security. 

SQL is used to store a database of users. It contains 3 tables: user details, timestables point, spelling points. This database is used to store user information and allow them to register and login. The 'points' tables are used to display the correct points and stickers on the stickers page. 

Javascript is used on the maths/spelling pages. Depending on the answer that the user provides, the script will change the text displayed and the colour of the box.

An error page will be displayed if the user provides incorrect details when logging in. It will also be displayed when registering if the details already exist, if any fields have not been completed or if the password don't match.




