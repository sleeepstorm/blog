---
title: "Strict Time - turn off your computer for good"
date: 2022-7-23
---

![Title Image](https://th.bing.com/th/id/R.30cd94aa80ddb61ed0a64c12a0af194f?rik=rXvFJJYKlB0GLQ&pid=ImgRaw&r=0)

## What is Strict Time?

Strict Time is an app created by the author of this blog Nikhil Harry ([@nikhilhex](https://github.com/nikhilhex)). Strict Time was created in [C#](https://docs.microsoft.com/en-us/dotnet/csharp/) using [Windows Forms](https://en.wikipedia.org/wiki/Windows_Forms). Strict Time is licensed under [GPL-2.0](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html). You can contribute to Strict Time [here](https://github.com/nikhilhex/Strict-Time/tree/master).

## What does Strict Time do?

As you see in the title, I put:
> Turn off your computer. For good.

 Have you ever had to go somewhere? A meeting, home from work, to work, you're just working on that one project then you end up being late? Just turn on Strict Time and it will turn off your computer at the exact time you enter and gives you the option to have a warning display or no warning display. You can't cancel your shut down though that is planned to be added.

## How does Strict Time work?

Jumping into the code of Strict Time, when you click the *Start* button to prepare the shutdown here is what it does:

1. Create a [Timer](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.timer?view=windowsdesktop-6.0) and make it tick every 100 ms (to be honest, 60000 ms would be the best because I removed implementation for entering seconds) 

2. Check to see if it's time to turn off the computer using:
```
// dtp is the timer
Math.Floor(((TimeSpan)dtp.Value.TimeOfDay - DateTime.Now.TimeOfDay).TotalSeconds) == 0
```
3. Check what the user entered in a [switch](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/statements/selection-statements#the-switch-statement) statement. 

4. Run `Process.Start()` to shut down the computer. Read my [last post](https://www.nikhilharry.com/blog/2022/07/14/My-Experience-Wth-Process-Start.html) (except the sleep command that doesn't use `Process.Start()`).

The entire code looks like this:
```
 if (Math.Floor(((TimeSpan)dtp.Value.TimeOfDay - DateTime.Now.TimeOfDay).TotalSeconds) == 0)
            {
                switch (comboBox1.Text)
                {
                    case "Log Out":
                        Process.Start(@"C:\Windows\System32\cmd.exe", "/C shutdown /l");
                        break;
                    case "Hibernate":
                        Process.Start(@"C:\Windows\System32\cmd.exe", "/C shutdown /h");
                        break;
                    case "Sleep":
                        Process.Start(@"C:\Windows\System32\cmd.exe", "/C rundll32.exe powrprof.dll, SetSuspendState Sleep");
                        break;
                    case "Shut Down":
                        Process.Start(@"C:\Windows\System32\cmd.exe", "/C shutdown /s");
                        break;
                    case "Shut Down (No Warning)":
                        Process.Start(@"C:\Windows\System32\cmd.exe", " /C shutdown /p");
                        break;
                }
```

## Conclusion

If you need Strict Time, it's possible to navigate to the repo I linked above and click on the latest release. I won't be posting next week though the week prior, I can post.
