# Updated Apns-Sharp Library now Powering G-Push Mail #

First I apologize for the lack of updates to this project.  It's been too long!  With that said, I've finally updated the project to 1.0.2.0 which includes a substantial set of changes to the Notifications library in particular.

Previously, I had taken the code I was using at the time in my application, forked it, and tweaked it into this library.  I was too busy to actually switch my application (G-Push Mail) over to this library, and life went on.  As I noticed bugs (some big ones!), I fixed them in my application, but those changes never made it to this project.

Well, I've finally got a chance to fix this library, and I'm announcing today that my production application: G-Push Mail is now running using the Apns-Sharp library!  Basically, this means that the library will get more attention.  Any time I notice a bug in my production app, or decide to enhance G-Push Mail's apns capabilities, Apns-Sharp will benefit from the changes!

I do have to admit though, that the only part I'm using in projection right now is the Notifications.  I don't use In-App purchases in my app anymore, so I haven't tested the AppStore part of the library very thoroughly.  I do plan on using the Feedback library in the very near future!

Thanks to all those who have filed bugs, and continue to do so.  I promise it won't be months to fix any bugs that do pop up this time!

Last but not least, I need a shameless plug for G-Push Mail
[G-Push Mail iTunes Link](http://itunes.apple.com/us/app/g-push-mail/id319506917?mt=8)