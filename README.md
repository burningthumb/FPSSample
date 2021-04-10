![](Documentation/Images/Banner.png)

# FPS Sample

**This project is based on Unity 2019.2.21f and no longer being actively maintained.**

Due to is heavy reliance on an obsolete version of Unity DOTS the effort required to move it beyond this verion of Unity is more than I am prepared to commit.  If you are interested in moving it forward beyond this I will glady work with you to incorporate and verify changes.

Having said that, since you can open it in Unity 2019 its not so bad as a project from which you can extract some of the many resourced.

At one time, several years ago, this was a fully functional, first person multiplayer shooter game made in
Unity. This repository includes full source and assets. It was developed by a small
team from Unity Technologies. 
Visit the [landing page](https://unity.com/fps-sample) for more high
level information about the project. Or reach out [in the forum](https://forum.unity.com/forums/fps-sample-game.184).

I updated it to Unity 2019 and merged the macOS build stuff (but did not test it) you can find online elsewhere. Unfortunately the Burst compiler does not work with this version of Unity on macOS 11 as Unity misidentifies macOS 11 as Linux and tries to run the wrong executables.

The project is using a number of technologies that have been changed so much that you will not find them very useful. The assets are high quality and you may find them very useful.

## Status and prerequisites

Current status at a glance:

__Unity version:__   2019.2.21f1
 
__Platforms:__ Windows (client and server), Linux (server only), Mac (client and server - untested)


## Getting the project

To get the project folder you need to clone the project.
Note, that 

> __IMPORTANT__: 
> This project uses Git Large Files Support (LFS). Downloading a zip file using the green button on Github
> **will not work**. You must clone the project with a version of git that has LFS.
> You can download Git LFS here: https://git-lfs.github.com/.

The project size is about 18GB (size of Assets folder). Your cloned repository
will be almost double of that due to git state. If it is much smaller,
you most likely did not have LFS when you cloned.

## Getting the right version of Unity

Once you have cloned the repository, you should install
the version of Unity that is listed above in the prerequisites section. Make
sure you include windows standalone support in your installation (and Linux support
if you want to build the Linux headless server).

## Opening the project for the first time

The following guide should take you to the point where
you can hit play in the editor and run around the levels and also build a
standalone version of the game and use it to spin up a server and connect a
few clients to it.

The first time you open the project you need patience! It takes a while
to import all the assets.

Once the editor is ready, open the _Project Tools Window_ by
navigating to ___FPS Sample > Windows > Project tools___.

It should look like this:

![](Documentation/Images/ProjectTools.png)

Keep this window docked as you will use it a lot. From here you can open the
levels, build assetbundles and build standalone players. Because this is a
multiplayer game you will need to work with standalone players a lot.

### Trying out preview mode

From the Project Tools window click __Open__ next to Level_00. Our levels are
split into multiple scenes but using these buttons will ensure you open all the scenes
that make up a level.

Once opened, try entering playmode in the editor. You should now
be able to run around in the level. This is what we call 'preview mode'. Here
you can move around and test your level, player traversal and weapons.

### Building bundles and standalone

Leave playmode again and in the Project Tools window, verify that
it says "Building for: StandaloneWindows64..." under the Game headline.
If it does not, change your platform in the usual way, using File > Build
settings window.

Now, in the Project Tools window in the bundles section, press __All \[force\]__.

This will build the levels and other assets into assetbundles. The first time
around this will take a significant amount of time as all shaders have to be
compiled.

Once you have built the bundles, hit __Build game__ in the game section.
This builds the standalone player. Again, first time will be slow.

> __NOTE__: Due to a limitation in Unity 2018.3, you have to look out for errors like this `Maximum number (256) of shader keywords exceeded, keyword <KEYWORD_NAME> will be ignored.` and similar. If you get these, you can close and open Unity and then try and build again. The errors are relatively harmless but can lead to graphical artifacts as some shaders will have wrong keywords.

### Using the quick start launcher

When this is done, locate the "Quick start" section at the bottom of the
Project Tools window. Fill out the settings like this:

> Mode: __Multiplayer__\
> Level: __Level_00__\
> Clients: __1__\
> Headless: __Checked__\
> Use editor: __Unused__

Now hit the green __Start__ button. This should launch two processes: one is
a standalone, headless server, the other is a client that will attempt to
connect to the server.

Congratulations! If you made it this far you should celebrate a bit!

## More information

Check out the [Documentation](Documentation/) folder for more information. In particular, the [Getting Started Guide](Documentation/GettingStarted.md) is a good place to, well, start.

## License

Our intention is that you can use everything in this project as a starting
point or as bits and pieces in your own Unity games. For the legal words, see
[LICENSE.md](LICENSE.md).