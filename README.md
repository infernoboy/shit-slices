# 💩 shit slices

A shittier, bash version of slices for iOS 11

## Usage

This is terminal based, so you'll need to ssh to your phone to run commands, or use NewTerm 2 on Cydia.

### Create a new slice

To create a new slice, open a terminal window and type

```
slices "Snapchat" create new-slice
```

In the above example:

`Snapchat` is the name of the app as shown under the app's icon (case sensitive)
`create` is to make a new slice
`new-slice` is the name I chose for the new slice

Once this command is run, the script will create 2 slices, one named `new-slice` and the other named `_original`. The `_original` profile name can't be changed, as it's a system profile. 

### Switch profiles

Continuing from the above example, the current active slice is `new-slice`. You can now open Snapchat, log out, and log in to a new account. To apply the original slice, type:

```
slices "Snapchat" original
```

To switch back to the other slice, type

```
slices "Snapchat" apply new-slice
```

### Delete a slice

```
slices "Snapchat" remove new-slice
```

### Delete all slices

```
slices "Snapchat" clean
```

### Delete all profiles

```
slices reset
```

## Activator

Since there's no UI, and it's a pain in the ass to enter these commands by hand, we can use Activator to setup easy app switching.

Go to activator settings, choose `Anywhere` < `Build` < `Icon Flick Up`, then choose Snapchat.

Then `Anywhere` < `Snapchat Icon Flick Up` < `Build` < `Run Command`

Then enter the command `slices "Snapchat" original`

Repeat the same process above, but do it for `Icon Flick Down`, and set the command to apply `new-slice`

Now swipe up on the snapchat icon, and wait a few seconds and Snapchat will open using the original slice.

Now swipe down on the snapchat icon, and wait a few seconds and Snapchat will open using new-slice.

Of course, the options are many here, and you don't have to use icon flick. You could also make a menu in activator with each slice as an option in the menu.

Because this script only moves the contents of the application data around, it shouldn't be detectable.

## Misc info

You can create as many slices as you want per app.

Slice names should not contain spaces.

This has been tested with the following apps:

 - Instagram  
 - Snapchat
 - Hangouts

Open an issue if you find that other apps work or don't work.

## Dependencies

Activator - https://rpetri.ch/repo/ https://github.com/rpetrich

PlUtil - http://repo.bingner.com http://github.com/sbingner

Link Identity Editor 2 - http://jakeashacks.com/cydia

## Originally created by

jlippold - https://github.com/jlippold/shit-slices
