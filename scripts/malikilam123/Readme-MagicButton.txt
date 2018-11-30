The so-called Magic Button concept was one described by rockatron99889 here
https://groups.yahoo.com/neo/groups/zonemobius/conversations/topics/8251 .

As I understood it the basic concept is that we want the ability to trigger a
series of buttons bound to functions (like Overdub, HalfSpeed etc.) and,
instead of having those button triggers make the functions that they relate to
execute when the buttons are triggered, collect the functions that are invoked
and hold them without execution until they can all be executed at once when the
Magic Button is pushed.

So, I implemented that idea by creating two types of scripts that relate to
each other by passing values using global variables.  The first type of script
is what I call a Feeder Button script.  The Feeder Button script is quite
simple.  It basically just provides a means of turning on a switch (a Boolean
global variable) that will then me used to tell the Magic Button script that
the user wants the particular function related to the Feeder Button script to
be invoked when the Magic Button is triggered (along with whatever other
functions have been fed to the Magic Button by other Feeder Button triggers).

The Magic Button script basically just uses IF statements to check which Feeder
Buttons have been triggered since the last time the Magic Button was triggered
and then executes those functions simultaneously.

(The Magic Button sets the Feeder Button boolean variables back to untriggered
once it fires off the functions so that you can start from scratch on the next
round.)

What would be cool for phase two of the development of these scripts is to
setup the Magic Button to toggle itself on and off.  The idea is that on the
first press it invokes all of the functions fed to it, and on the second press
it turns them all off.  That can easily be accomplished by setting up a global
variable within the Magic Button script and building a structure which flip
flops the variable between 1 and 0 depending on whether it has been pushed an
odd or even number of times.  (I just haven't taken the time to do that.)
Then you can use IF statements to make the script either turn on or turn off
the functions.

When Rockman asked me to provide some example scripts it occurred to me that
doing so is largely just a matter of repetitious coding of the same thing over
and over again (trying to make sure that you don't mistype anything in the
process).  I figured that a computer could do that much better than I could, so
I created the attached Excel spreadsheet which will pretty much write any
Feeder Button script that Mobius can use and the IF statement for that Feeder
Button script to put in your Magic Button script.  (If you don't have Excel,
the free Open Office Calc will read this file and work just as well.)
Basically, I just grabbed the list of Mobius functions from the scripting
manual, put them in Excel so that you could just select (in cell B1 of the
sheet entitled "Feeder Build") the function that you want to use and then
Excel will create both the Feeder Button script (on the sheet entitled
"Feeder Script") and the IF statement to insert into your Magic Button
script (on the sheet entitled "MagicButtonIfScript").  You can then just
paste the contents of the Feeder Script excel sheet into a text file and paste
the contents of the MagicButtonIfScript excel sheet into your Magic Button text
file (script).  From there it should be smooth sailing.

I would love to hear any tracks you come up with using this setup.

Onelove, MalikilaM
