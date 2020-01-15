# wiki-java-8
Fix for [MediaWiki Java bot](https://github.com/MER-C/wiki-java) written by [MER-C](https://github.com/MER-C) that works under Java 8.

#### Problem
The bot's framework keeps developing but now it requires JDK 11 to run. I needed Java 8 one. There is release [0.35](https://github.com/MER-C/wiki-java/releases/tag/0.35) from May 2018, however MediaWiki API changed since then and my bot was unable to log in. The method *getToken* is no longer supported and therefore it returns unsupplied response and the whole login process fails.

#### Workaround
I adjusted **Wiki.java** core class to use a new method *getToken2020* that handles obtaining login token in a way, that is described [HERE](https://github.com/MediaWiki-Bot/MediaWiki-Bot/issues/83). This allowed my bot to login and work with my MediaWiki.

#### Proposed future development
Since the MediaWiki API depends on version, the bot should be able to differ between "old" and "new" login and use method to obatin the login token accordingly. **This is currently not implemented**.
