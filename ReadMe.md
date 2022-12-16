# Determining the number of days in a month in JavaScript

Essentially, writing some code to determine the number of days in a given month of a given year with javascript is not the worlds most difficult task. It is the type of exercise that one would expect to be given as a newbie developer during a lab or lecture. The solution normally involves determining if the month is February, an month with 30 days or a month with 31 days, then (if February) checking if the year is a leap year. All these tests add up, however, and add several lines of code to your .js file. They are also unnecessary!

Apparently, the javascript Date function allows you to overflow the day number parameter that you pass, creating a date in the next month. Deliberately overflowing the day parameter and checking how far the resulting date overlaps into the next month is a quick way to tell how many days there were in the queried month. Here is a function that does this:


function daysInMonth(iMonth, iYear)
{
return 32 - new Date(iYear, iMonth, 32).getDate();
}
