GWSAndroidGradle
================

A set of gradle build scripts for android java application development.

modules:

   app is non flavored and not using lombok or kotlin

   favoredapp is flavored but not using lombok or kotlin

   library is not flavored and not using lombok or kotlin

Downloading
-----------

I use JitPack to deploy my libraries so you can put this in your root build script:

```groovy
allprojects {
        repositories {
            jcenter()
            maven { url "https://jitpack.io" }
        }
   }

```

the maven url has to be after jcenter to work and than in the module build script:

```groovy
compile 'com.github.shareme:GWSAndroidGradle:{latest-release-number}@aar'

```

the latest-release-number will match the latest release listed in the github releases tab.


Implementation
--------------

Using the principle that gradle can load gradle snippets as plugins to separate out the
gradle build scripts concerns so that we get very readable module build scripts.

This set of build scripts is optimized for fast compiling on junk laptops, that means that I am
running the code qa stuff as local IDE plugins instead when I need that feedback.

Git Hashes:

   Implemented as cross-platform using the Grgit wrapper that wraps JGit libraries within the
   root build script as that is the only place where one can do gradle import statements. In the
   app modules than the git has is referenced as a rootProject ext global variable and stored in a
   buildConfigField buildTypes block.

   The main reason for this is so we track app module releases via the git hash to match up analytics
   crash reports with the correct release causing the problem via the stored git hash
   in the buildConfigField.

Proguard:

   Workaround for Samsung devices support lib goof/patch included, its known as the
   4.x fix and its marked with comments in the proguard-matches-android-optimize.pro file.

EditText:

   workaround for api 21 and 22 in res/values/dimens.xml and same in values-21 and values-22 res folders

App Sign Key:

   I use putting app key in buildsystem folder rather than some other local user folder.
   NOT SAFE for public repos, if you need with public repos you should change it to something reading from
   the command line as system.property that way you can still execute it on CI servers.

AndroidTest:

   Implemented system animations disable during testing via my own library of classes and the gradle
   build script tasks and the AndroidManifest.xml files in androidTest.

Travis CI:

   no-boot-anim fails on api-23 images so the travis CI stuff needs to not have used as a before script
   command.


Usage
-----



Changelog
---------




Credits
-------

Fred Grott(aka shareme  GrottWorkShop)
[MyGithubProfile](https://github.com/shareme/MyGithubProfile)

Computer language polyglot focusing on designing and developing Android Java Applications to Launch
people's lives for start-ups. Quality Java Software Engineer begets quality
GUI-intensive mobile applications.

Only FUNDED start-ups and no recruiters(No recruiters, PLEASE!)


### Repos

[Github](https://github.com/shareme)
[Bitbucket](https://bitbucket.org/fredgrott)

### Social

[G+](https://plus.google.com/u/0/+FredGrott/about)
[Twitter](https://twitter.com/fredgrott)
[Facebook](http://www.facebook.com/fredgrott)
[Reddit](http://www.reddit.com./user/fredgrott/)
[GeekList](https://geekli.st/fredgrott)

### Bookmarks

[Delicious](https://delicious.com/shareme)

### Design

[DeviantArt](http://shareme.deviantart.com)
[BeHance](https://www.behance.net/gwsfredgrott)
[Dribbble](https://dribbble.com/FredGrott)

### StartUps

[AngelList](https://angel.co/fred-grott)
[BuiltINChicago](http://www.builtinchicago.org/member/fred-grott)
[HackerNews](https://news.ycombinator.com/user?id=fredgrott)
[FounderDating](http://members.founderdating.com/profile/6572)


### Freelancing

[GunIO](https://gun.io/accounts/shareme)

### Questions

[StackOverflow](http://stackoverflow.com/users/237740/fred-grott)
[Quora](http://www.quora.com/Fred-Grott)

### CV

[LinkedIN](http://www.linkedin.com/in/shareme/en)
[Xing](https://www.xing.com/profile/Fred_Grott?sc_o=mxb_p)

### Slides

[SlideShare](http://www.slideshare.net/shareme)
[SpeakerDeck](https://speakerdeck.com/fredgrott)

### Articles, Blogging

[Medium](https://medium.com/@fredgrott)
[Blogger blog](http://grottworkshop.blogspot.com)
[Android Hacker Tumbler](https://www.tumblr.com/blog/androidhacker)

### Video

[YouTube channel](https://www.youtube.com/c/FredGrott?gvnc=1)
[Ustream](https://www.ustream.tv/manage-show/12940149)


### AboutMe

[AboutMe](https://about.me/fredgrott)


License
--------

[Apache 2.0 License](http://www.apache.org/licenses/LICENSE-2.0.txt)


Resources
---------

[Google Android Developer Site](http://developer.android.com)

[Google Android Developer Tool Site](http://tools.android.com)

[Google Android Developer Blog](http://android-developers.blogspot.com/)


[StackOverflow Android Questions](http://stackoverflow.com/questions/tagged/android)

[Gradle](http://gradle.org)

[Reddit-androidev](http://reddit.com/r/androdev/)

[AndroidChat at Slack](https://androidchat.slack.com/messages/development/)

[Amazon Android Dev Site](https://developer.amazon.com/public)

[JavaRanch Android Forum](http://www.coderanch.com/forums/f-93/Android)

[Android Development Tools G+ community](https://plus.google.com/communities/114791428968349268860)

[Android Development G+ Community](https://plus.google.com/communities/105153134372062985968)

[Android Developers G+ Community](https://plus.google.com/+AndroidDevelopers/posts)

[Android Design G+ Community](https://plus.google.com/communities/113499773637471211070)

[UX Design for Developers](https://plus.google.com/communities/103651070366324568638)

[Android MVP G+ Community](https://plus.google.com/communities/114285790907815804707)

