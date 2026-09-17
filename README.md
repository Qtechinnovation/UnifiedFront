# UnifiedFront

A Decentralized, Local, Cross Platform Web App Store, built on apps.json.

### Why UnifiedFront?

On many platforms, storage, performance, and/or local apps are restricted. This makes installing apps much more difficult. Take, for example, ChromeOS. By default, you cannot install any local apps. You can enable Android/Linux apps, but if your Chromebook is managed by an organization that disables these, your only option is the Chrome Web Store. This can work, but apps installed from here generally only function if you have internet, can be blocked by network filters, and can be taken away at any time because they really aren't even installed on your Chromebook at all. And even this can be disabled through organization management, leaving you with no dedicated app store to install apps from.

### How does UnifiedFront solve this problem?

UnifiedFront is built on a single, simple file, called apps.json. All you have to do is download a launcher, (like our bundled launcher, UnifiedLauncher), and initialize a folder, and you can use this single folder with a simple apps.json database file to install apps in one click from any app store across the internet that supports apps.json. Since apps.json is an open, forward compatible standard, you can use any storefront and any launcher that supports apps.json. This is further complimented by some of the design constraints of apps for this platform:

1.  Portability

Because of CORS limitations, only single file HTML web apps are supported currently supported, because multiple file app support is significantly more difficult to implement. This has the side effect of making it incredibly easy to swap launchers and simplifies the standard for apps.json significantly.

2. Ease of use

Because the entire standard is a single folder and one file, all you have to do is open one folder, and you can install any app in one click.

3. File size

Because these are all HTML files, they are incredibly lightweight, with dramatically smaller file sizes than native apps.

Due to all of these design constraints, some interesting use cases become possible.

- A local app store for web based platforms like ChromeOS

- An incredibly portable app solution for taking your apps on the go (you can put a launcher, apps folder, and hundreds of apps with you on a USB stick and use them on any device, since neither the store nor the launcher care where your apps are located)

- A quick and easy target to test or deploy simple HTML applications like simulations or games

### How did we achieve this?

UnifiedFront uses Chromium's File System Access API to grant access to a folder, open things from within it, and manipulate entries in apps.json. This has the unfortunate consequence of making it incompatible with Firefox and WebKit, but implementations for those platforms would sacrifice on simplicity, portability, or ease of use. That does not mean implementations for any of these platforms are off the table in the future, but unless a similar API becomes available for Firefox or Webkit, I will not be building support into UnifiedFront for these platforms.
