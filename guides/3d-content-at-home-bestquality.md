# Playing 3D Content at home with flexibility & the best possible quality
Date: 28 June 2026

## Introduction
Lately I was fond on about getting an home 3D cinema experience and I studied during the last weeks the solutions & ways to achieve a premium home 3D experience. There's plenty of edge cases and things to know to get the best experience, so I am writing this paper hoping it will save you plenty of yours by not needing to go through what I had to go to get a proper view of the home 3D ecosystem and how you can do it by yourself in 2026.

Unfortunately, home 3D is becoming more than ever a niche so it means new edge cases will appear and chances are the support is getting only narrower with manufacturers, softwares, etc. New 3D content on blu-rays is also rare these days. If you live in Europe, you may want to support Turbine: https://turbine-shop.de/en/CATALOGUE/Technik/Blu-ray-3D/ which is the last editor still making regular new 3D releases.

But since the 20 last years, hundred of movies had a 3D release and you can find new old stock & second-hand discs often for pretty cheap these days to start building your own collection.

**In this guide you will learn:**
- What are the current available 3D formats and their usage
- What hardware, PC+Mac softwares, & players I tested. I will share my experiences with all of them & guide you so you can also get a very good experience too. Providing opiniated, but tested options you can choose from. I like to tinker with stuff, so I tried the cheapest options before investing into more dedicated solutions.
- I will focus on the h.264 MVC format and on solutions that are supporting pure ISO rips, which is where there is the most edge cases to handle but also how you will get the best possible quality
- What you need to think about if you are planning to get a new projector that supports 3D well. The advices there may save you a lot of time as unfortunately this knowledge is not spread massively and not on the marketing pages of the projectors you may have been interested to buy even if their technical specs mentions 3D support
- Quick tips on how to manage your files on your LAN with your media player and how to setup an high performance fast file sharing on Debian 13 that will work with your media boxes and other devices on your LAN

## Artificial intelligence transparency & ethics
To write this guide, I did not used any gen-AI tool. It's all and only human efforts in this work. I found & documents the solutions by using the search engines & filtering myself the data that I could read on many places. As a french-native, English is not my first language so there may be some mistakes too but I ensured all parts of this guide is understandable "good enough" and respecting your time as a reader.

This is my first guide that is not related to iPods and music players, but I wrote it using the same ethics principles : 
- Re-reading myself a lot
- Providing useful data and sharing personal experiences and my tinkering results
- Ensuring the info is structured, easy to understand and to replicate for you
- I plan to maintain the guide & provide updates if the 3D ecosystem changes significantly in the future or if some informations provided there are getting obsolete
- Non sponsored links & not in partnership with brands, so I can talk freely about the products and not hesitating to point any caveat

## Was available in exclusivity on Patreon in early access for one week
I released this paper one week ago in early access for my Patreons. Now that the early week access is finished, as I promised this guide is open sourced on my GitHub repo and available to read right now: https://github.com/Olsro/reddit-guides

## The 3D formats
### HSBS / HTAB  (Half Side By Side / Half Top & Bottom)
Most common available 3D formats you will encounter by sailing the see, often in MKV containers. You get only half the resolution, but those files are very easy to play. You basically use any player of your choice which supports simple h.264 files in full screen, then configure your TV in Side By Side or Half Top & Bottom mode.

Those files are often small re-encodes with decent quality/3D, but do note they contain only half of the resolution (half 1080p).

### FSBS / FTAB (Full Side By Side / Full Top & Bottom)
Now we're getting more serious : those re-encodes contains the full resolution (1080p for each eyes). If they are re-encoded with decent parameters, you should not feel any huge quality loss and may need this format if your device cannot decode MVC.

Unfortunately those files are way less compatible & depth 3D subtitles cannot be retained without burning those in the video stream directly, so the HSBS/HTAB format is more popular for the improved compatibility.

### MVC (Multiview Video Coding) (The golden choice)
This is what 3D Blu-rays contains. MVC is the golden format for 3D.
MVC is an extension of h.264 but also of h.265. It is used with h.265 by Disney+ to distribute 3D content for the Apple Vision Pro but nobody knows yet how to rip the content from there.

In 3D blu-rays, even the most recent ones, MVC is always paired with the good old h.264 so it's what you are going to deal with for the moment.

To build your own decrypted ISOs by yourself from your own collection, I recommend MakeMKV: https://makemkv.com/ Any blu-ray drive will work to make the rips.

## How does 3D Blu-rays competes with 4K/Dolby Vision blu-rays nowadays ?
The 3D blu-ray tech is almost 20 year old at this point, so you won't even get HDR. 3D Blu-rays content is always SDR. This is speaking purely technical. In terms of feelings though, 3D content provides a level of immersion that newer tech won't provide and which will make you like to rediscover many movies you know. For example speaking of Avatar, I believe the 3D blu-ray experience is the best way to watch the franchise at home.

## Screens
### TVs
The TV market abandoned 3D completely since years from now.

Be aware that 1080p Passive 3D LCD and OLED displays cannot do FullHD 3D, each eyes will only receive a 540x1080 image. Though 4K displays with passive 3D support can support FullHD.

I could not test any 3D TV, so I quickly pass on this section.

### Projectors
Some new projectors still supports 3D, mostly through the cheap DLP Link protocol.

The most important thing you need to take care here is to know that many recent projectors won't do framepacked 1080p 3D properly. Here is a forum post explaning you well what the problem is: https://www.avsforum.com/threads/best-full-resolution-3d-projectors-5k-in-2025-26.3336113/

Your bible should also be this Kodi's wiki post: https://kodi.wiki/view/3D#FullHD_resolution_issues

The main thing that will ruin your experience is the lack of full resolution 3D. If you already own a projector not referenced anywhere with this issue, you can do the test by yourself using the 3D Sample #5: https://kodi.wiki/view/Samples#3D_Formats which is "3D Framepacked Full Resolution Test Pattern". If the letters appears to be blurry, it's bad and your projector works like a passive 3D and not outputting true 1080p for each eyes.

I own the XGIMI Horizon 20. It was specifically updated by XGIMI to fix this issue recently. This model provides a fantastic 3D experience, but do know **you will need official XGIMI DLP LINK glasses on this model**. It's not a very well documented, but 3rd party glasses like the popular "AWOL" ones on Amazon will regularily disconnects during a movie with this projector.

Some reviewers claims the XGIMI glasses are less confortable if you wear corrective glasses. Though I did not encountered any problem, they are confortable enough.

Another point of attention may be to consider if the projector supports auto-3D. On the XGIMI, you need to always select manually the 3D mode you want. Some projectors from other brands can switch automatically to the appropriate 3D framepacked mode. But it's not a big deal to me.

### VR headsets
I did not tried this option, but if you get one you may need to check what video players you can run on yours. There's high chances you will need to transcode your files to SBS/TAB MKVs.

## Players
This is all the solutions I personnally tested. I focused on my research only on solutions that can work with 3D ISOs, which is the gold format to play 3D content.

### An Intel PC or Mac on Windows
#### How to
##### Using a Kodi Fork
https://forum.kodi.tv/showthread.php?tid=365120

This Kodi Fork supports MVC decoding with many Intel GPUs. I had success with an old 2012 MacBook Pro running Windows 10 LTSC on bootcamp.
In ```Player``` settings, I had to change the ```3D MVC decoder HW support level``` to 11 with this machine.

##### Using a commercial software like PowerDVD 19 or older
PowerDVD 19 (& older versions) used to support MVC 3D blu-rays playback. In most cases, it will work great, but in some cases (especially with Disney blu-rays), you can't pass the menus because the disc somehow detect your 3D or player is not 3D compatible. PowerDVD does not give you the ability to bypass the menus in those cases unfortunately. I will say 95% of the 3D Blu-rays will work fine. I tested also very old PowerDVD versions and they do not work better on BD-J 3D menus.

##### Following this Reddit post: https://www.reddit.com/r/htpc/comments/115ap94/how_to_get_full_hd_3d_frame_packing_from_a_pc_or
A quick review of this popular Reddit post speaking about 3D with computers, so here I am sharing my experiences.

**MacOS:** forget about all the solutions. While SwitchResX seems now able to handle custom resolution even with Apple Silicon macs, the only decent compatible software which is sView was often crashing to me and too annoying to setup. I even tried the Windows setup using a Parallels Desktop virtual machine but could not managed to make things work reliably.
**Windows:** In my opinion it's not necessary to mess up with MPC-BE. Just installing the K-Lite codec pack "Full" is the easiest way to get started: https://codecguide.com/download_kl.htm It will install all the stuff for you and the latest version of the MPC player for you.

If most cases on Windows you should not follow all the confusing parts about forcing custom resolutions. Many Intel drivers won't even let you add that specific framepacked 3D resolution anyway, and those GPUs will happily switch automatically to Frame Packed 3D mode when a software requires it (like the modified Kodi version or PowerDVD)

The latest Windows 11 release should still work no problem with 3D, though Microsoft may break support in the future. I recommend you to build a minimalistic Windows 10 LTSC partition if you want to build a reliable setup that will feel the same for you over the next years.

##### Trancode all your MVC content to SBS/TAB MKV using BD3D2MK3D
It is time consuming and will take a lot of extra hard drive storage if you are keeping your BD 3D ISO somewhere. It is also time consuming to do the tagging by yourself, and to process all the bonuses/extras that may be into a 3D Blu-ray.

But once done/if done properly, you will get good quality 3D MKV movies that are playable anywhere with any TV boxes/PC reliably.

https://www.youtube.com/watch?v=GKhrRFMfxWI here is a comprehensive guide I found using the MakeMKV + BD3D2MK3D to do the transcodings by yourself. Using BD3D2MK3D is already well documented elsewhere so I won't cover the usage in this guide.

If you choose to convert to FSBS or FSTAB, you will lose depth in your 3D subtitles.

I don't recommend this solution, it's way too destructive on the source material. There's too much compromises there ; and "Half" 3D modes reduces the quality too much.

#### Pros
- You may already have one ready to serve you

#### Cons
- No HDMI CEC, so you can't control this with your TV/projector remote
- Windows is bloated and anything running in the background with an old machine can introduce lag / takes long to boot
- Depending on your Intel card & setup, you may need to tweak settings

Conclusion: can be decent & you may already own all the required hardware to start doing it at home right now.

### A Raspberry PI3
#### How to do
Very important: flash the latest unofficial build from "TheMontezuma": https://github.com/TheMontezuma/LibreELEC.tv/releases

The last official build which supported MVC 3D on the PI3 

#### Pros
- Often can be found for cheap (50 euros or less)
- HDMI CEC support, can be controlled using your TV remote

#### Cons
- Not powerful enough to play h.265 content, use it only to play h.264/DVD content
- Won't work with FSBS / FTAB, because it is not powerful enough
- MVC decoding isn't perfect, some content will have regular glitches (like Disney's Tangled). Though it's not terrible
- Still sometimes laggy on 3D content, so there's some dropped frames
- So weak that it will lag a lot when decoding by itself certain audio formats. HDMI passthrough is almost a necessity with this device
- Forever stuck with an old Kodi version, as newer ones dropped support for MVC decoding on the PI3

If you intend to play only 3D ISOs or MVC MKVs and already own one or can find one for very cheap, it will do the job decently when properly configured. Even glitched movies won't glitch each 5 seconds, affected movies were watchable from start to end.

Don't forget to enable the option to change refresh rate when playing content or 3D mode won't be enabled. There's also another option to check, which will enable the framepacked 3D mode.

### Vero V
#### Pros
- Polyvalence (4K Dolby Vision FEL is fully supported). Will play anything (AV1, H265, H264) very reliably.
- You support directly the OSMC project by buying one
- HDMI CEC
- Way faster & more powerful Kodi device than the PI3, so everything is way smoother

#### Cons
- Price (needs to be imported from UK for around 150 euros). Worth the price, but a bit too expensive if you are interested only with 3D MVC.
- MVC decoding isn't perfect, some content will have regular glitches: https://discourse.osmc.tv/t/3d-mvc/95939/35 so you need another device or to transcode the problematic contents to FSBS/FTAB
- BD-J support in Kodi is purely theorical, it worked very badly in practice from my tests. Though it's not a big deal, the simplified menu is good enough to find the main title & start playing it and I heared Kodi 22 will even improve the quality of the simplified menu

### Zidoo Z9X (or Z9X Pro / any other Zidoo device supporting MVC 3D based on Realtek chip)
#### Pros
- Was easy to find one pretty cheap on the second-hand market (around 100 euros)
- Run Android so plenty of apps available
- HDMI CEC supported. Boots also even faster than the Vero V.
- Polyvalence: way more polyvalent than a pi3, though it is lacking Dolby Vision FEL support so if you have a very modern projector, you may still want another device.
- Once everything is properly configured, 3D MVC supports seems to be perfect there, I could not find any glitching movie for the moment.
- Remote control using a web browser or the official phone app works very well. Using the phone app, you can basically get a complete touchscreen file browser and start the next movie entirely from there.

#### Cons
- Supports BD-J menus but not good enough to be really usable reliably from my experience. Some 3D movies (often Disneys) won't go through the menus because they detect your player/screen is not 3D so they block you with an error message. Also I could not figure out how to force the player to display the menus in my native language (french), those were always displayed in english
- Some integrated features are incomplete/bugged and needs workarounds. For example the file browser claims to supports network access through WebDAV, but is not capable to play a 3D ISO through it. The OS also claims to support the NFS sharing protocol to access files but the experience was terrible on ISO files, getting stutters each 5 seconds of a movie. Only SMB seems to be reliable on this device to access remote content on your LAN.

### What choice should you make ?
If you don't have the money/time to stack multiple different solutions, the best overall & long term solution from what I had the chance to test is to find yourself a Vero V as it supports the latest video-industry tech required to feed correctly modern 4K screens and projectors. Dolby Vision FEL is important to get the most of your 4K Blu-rays, here's a complete curated list of affected movies : https://www.reddit.com/r/CoreElecOS/comments/1j3lgw2/list_of_dolby_vision_p7fel_films . I think it's the best investment you can make to get a device that will be almost guaranteed to serve you for the next decade while still having a very decent integrated 3D MVC decoder.

If glitches in some rare 3D movies matters to you, doing some transcoding will do the job.

If you plan to stay stuck on the 1080p era for a while, a Zidoo will be a first class MVC 3D ISO player.

If you need to save as much money as possible, try to refurbish a pi3 as a 3D Kodi Player.

And at last resort, try to find/use an old intel Windows machine you already own. Put Windows 10 LTSC if it's an old machine, disconnect it from the internet and make it a single-purposed device that will be reliable for you in the long term for that specific usage. Using a frozen operating system will ensure 3D playback won't break over time for you.

### Your TV/projector integrated player
This will work in many cases with anything that is not MVC encoded, so FSBS/FTAB at best.

## Manage your media library on your LAN
### Physics
For convenience, you may be tempted to connect everything wirelessly using Wifi. Newer wifi revisions are theorically more reliable & capable at transfering each files. From experience with Wifi 6, it's still not good enough. I recommend heavily to connect both your mediabox + your NAS using good old Ethernet cables.

At least your machine serving your files must be connected through Ethernet. The mediabox itself may be pretty reliable over Wifi. But even if you manage to get a decent experience, an Ethernet cable on both sides is what you must aim to avoid strange issues/unstabilities.

### Protocols
From experience with all the protocols, the ones that works the best for mediastreaming are WebDAV (nginx) and SMB (samba).

NFS worked terrible with my Zidoo box.

SMB is the most universal and does not disappoint. On Debian you can install this protocol using this command ```sudo apt-get install -y samba```

This is my high performance Samba config on Debian 13. I found it elsewhere online and tuned it only slightly. Be aware there will be no security/auth with these settings, but this is often not an issue in the context of an home network.

Just change the server string and the [share] section according to your needs, then run ```sudo service smbd restart``` and do ```sudo systemctl enable smbd``` to run it Samba at each boot: 
```
[global]
  server string = MEDIAS
  workgroup = WORKGROUP
  browseable = yes
  writeable = yes
  printable = no
  deadtime = 30
  mangled names = no
  name resolve order = host bcast
  printcap name = /dev/null
  load printers = no
  encrypt passwords = true
  enable core files = no
  passdb backend = smbpasswd
  smb encrypt = disabled
  strict allocate = no
  allocation roundup size = 0

# samba share options
  map to guest = bad user
  guest account = root
  security = user

# samba tuning options
  socket options = TCP_NODELAY IPTOS_LOWDELAY
  min receivefile size = 16384
  aio read size = 16384
  aio write size = 16384
  getwd cache = true

# Using the following configurations as a template allows you to add
# writable shares of disks and paths under /storage

[share]
   path = path_to_you_external_drive
   available = yes
   browsable = yes
   public = yes
   writable = yes
```

## Conclusion
### Right now my current setup is
 - XGIMI Horizon 20 (also if you are interested by those XGIMI 20 projectors you should definitely check this test https://www.laurentwillen.com/en/test-reviews/projectors-tests-reviews/xgimi-horizon-20-vs-horizon-20-pro-vs-horizon-20-max-comparison/ by the very serious independent reviewer "Laurent Willen". There's high chances you are in a situation where you can save a lot of money by not buying the Pro or Max variants.
 - XGIMI DLP Glasses (required for 3D content)
 - Zidoo Z9X (non-pro) that I use for anything that is not Dolby Vision FEL
 - Vero V, that I use for Dolby Vision FEL rips
 - A NAS running Debian 13 serving the files on the home network
 - A 100-inch projector screen with 1.2 gain. I can recommend the brand "celexon" that I use, but there's plenty of choices. I recommend you to choose a screen with that gain to provide extra brightness (20%) and to project in the complete dark, as the DLP Link 3D technology is by itself very sensitive to parasite lights

My 3D experience with that setup is very good and plays everything in pure ISO, and the technology evolved so much you do not need to push the projector much more in terms of brightness to compensate the glasses. I did my tests and the picture was too bright at 9/10 or 10/10 of the projector brightness. 5 to 7 (of 10) of the projector brightness is really the sweet spot for me, just keep your normal settings (mine was 5) and increase the brightness one by one to get a more punchy picture without destorying color accuracy.

Do know that also most if not all DLP Links projectors do not offer motion compensation while in 3D mode. It was never a problem for me or something that disturbed me in any way. I consider my current setup as definitive and will likely stay exactly that way for the years to come.

Thanks your time at reading me. If that paper helped you saving time & money at making the best choices for your own interest, a small tip on my Patreon will be greatly appreciated to support the time & efforts I put into my work https://www.patreon.com/Olsro

Upvoting & commenting my Reddit posts is also helpful