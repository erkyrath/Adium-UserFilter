# UserFilter

## A very simple username filter plugin for [Adium][]

- Copyright 2016 by Andrew Plotkin
- GPLv2 license -- see [License.txt](License.txt)
- Originally based on the [SpamFilter plugin][spamfilter] by Thijs Alkemade.

[spamfilter]: https://bitbucket.org/xnyhps/adium-spamfilter-plugin
[Adium]: https://adium.im/

This is a crude filter plugin for [Adium][]. It allows you to block any message from a sender with a given account name.

I made this for one reason: to block Slackbot messages when connected to [Slack][] via the XMPP gateway. I wouldn't use it on real people, because XMPP already has features for blocking people.

[Slack]: http://slack.com/

## Compiling

Compiling Adium plugins requires some fiddling around.

First, you have to compile the Adium frameworks. Go to the [Adium release page][Adium-release] and download the source package which matches your version of Adium. (I used 1.5.10.2.)

[Adium-release]: https://trac.adium.im/wiki/PreviousReleases

Open `Adium.xcodeproj` in Xcode and use the "Build" command. This build fails (for me) because the OpenSSL framework is not found. But that's okay! All we need are the frameworks, and those got built okay.

Open the `Products` list in Xcode, select `Adium.framework`, right-click, and do "Show in Finder". Drag `Adium.framework` and `AdiumLibpurple.framework` into the `Frameworks` folder of the Adium-UserFilter source code.

Also, create a symlink called `Adium-Repo` which points to the Adium source directory:

    ln -s ~/Develop/Adium Adium-Repo

Now you can close `Adium.xcodeproj` and open `userfilter.xcodeproj`. The "Build" command should succeed.







