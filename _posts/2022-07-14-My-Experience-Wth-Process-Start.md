---
title: "My Experience With Process.Start();"
date: 2022-7-14
comments_id: 1
---

[*Edited: July 15, 2022*]

![Title Image](http://www.iconsoftwaresolutions.com/wp-content/uploads/2015/05/net.jpg)

(*Credit: [Icon Software Solutions](http://www.iconsoftwaresolutions.com/microsoft-net)*)

## What is `Process.Start();`?

`System.Diagnostics.Process.Start();` is a C# method in which is used to start processes. This method can easily be misunderstood for it's purpose/purposes. Check out the documentation [here](https://docs.microsoft.com/en-us/dotnet/api/system.diagnostics.process.start?view=net-6.0) for more on `Process.Start();`.


## Uses for `Process.Start();`.

According to the documentation I listed above, `Process.Start();` has a couple of uses:

> 1. `Start(String, String, String, SecureString, String)`: Starts a process resource by specifying the name of an application, a set of command-line arguments, a user name, a password, and a domain and associates the resource with a new Process component.
> 2. `Start(String, String, SecureString, String)`: Starts a process resource by specifying the name of an application, a user name, a password, and a domain and associates the resource with a new Process component.
> 3. `Start(String, String)`: Starts a process resource by specifying the name of an application and a set of command-line arguments, and associates the resource with a new Process component.
> 4. `Start(String)`: Starts a process resource by specifying the name of a document or application file and associates the resource with a new Process component.
> 5. `Start(ProcessStartInfo)`: Starts the process resource that is specified by the parameter containing process start information (for example, the file name of the process to start) and associates the resource with a new Process component.
> 6. `Start()`: Starts (or reuses) the process resource that is specified by the StartInfo property of this Process component and associates it with the component.
> 7. `Start(String, IEnumerable<String>)`: Starts a process resource by specifying the name of an application and a set of command line arguments.

My use for `Process.Start();` is here:
> `Start(String, String)`: Starts a process resource by specifying the name of an application and a set of command-line arguments, and associates the resource with a new Process component.


## Where I went wrong with `Process.Start();`
So, you might be asking how I came across and what my purpose was for with `Process.Start();` and it all started when I came across [this](https://stackoverflow.com/a/104258) post. The answer I linked for th epost actually had incorrect code but I never came across `Process.Start();` before. I eventually integrated that into my app but it wasn't working. After debugging dome errors, here was my solution:

Original:
```
Process.Start("shutdown", "/s");
```
What `Process.Start();` actually does is different to what I thought it did. If you click **Windows key + R** it opens **Run** which I thought `Process.Start();` would do, execute code in **Run**. When the realization came to me for what it actually does after researching a bit and coming across [this](https://stackoverflow.com/a/24933240) post. Technically the code there is correct but the way I approached it with a solution in which came to have a couple of errors.

Attempt 1:
```
Process.Start("cmd.exe", "/c shutdown /s");
```
This is almost working, though there are a few minor errors:

Attempt 2-4:
```
// Changed /c to /C
//Added file path to cmd.exe, it was trying to find the Command Prompt in the project folder
// Shuts off your computer:
Process.Start(@"C:\Windows\System32\cmd.exe", "/C shutdown /s");
```
## Conclusion
Even if some aspects of code can not always work the way you want, you have to work for it and you can it. Stay tuned for next week's post.
