<p align="center">
	<a href="https://github.com/kainatquaderee/miku">
		<img src="./common/public/logo_filled.png" width="250">
	</a>
</p>
<h1 align="center"><b>Miku</b></h1>

<h4 align="center"><b>Stream anime torrents, real-time with no waiting for downloads</b></h4>

**Miku** is a fork of [Miru](https://github.com/ThaUnknown/miru/) + [Migu](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://github.com/NoCrypt/migu&ved=2ahUKEwivlZaG3pmIAxVGcGwGHY52EyIQjjh6BAgREAE&usg=AOvVaw1wjpbOsEBCZx32uoqiwV8K) that focused on better **mobile** experience with added features and polished the experience by a mile.

## **Features**

Includes all original Miru features, plus:

- Toggleable AMOLED theme
- Optional Discord Rich Presence
- Optional Auto-update
- Free APK download on GitHub Releases
- Split Android builds by CPU architecture
- Auto-update with automatic CPU architecture selection
- Independent seeding speed control
- Close button on miniplayer
- Miniplayer doesn’t load on startup
- Swipe gestures for brightness and volume control on Android
- Scroll wheel for volume control on PC
- Redesigned Android navigation bar for improved usability
- Correctly implemented fullscreen mode on Android
- Safe area padding and margin adjustments on Android to avoid overlap with the status bar
- Imported Default Extension and RSS feed settings from PC to Android
- Auto fullscreen video playback on Android
- Scrollable RSS feed for more anime visibility on Android
- Double-tap to seek on Android
- Default seek duration set to 5 seconds
- Volume and brightness indicators for swipe and scroll gestures
- Torrent sorting by size (+seeders) to reduce bandwidth usage
- Default new release RSS set to "ASW" to minimize bandwidth usage
- Moved toast close button to the bottom for better reachability on Android
- Disabled smooth scrolling by default due to poor performance on my device
- Gesture lock on Android to prevent misclick

<br>
<details>
<summary><b>Removed and Implemented features on miru</b></summary>

- Proper back button functionality on Android ([better implementation on miru](https://github.com/ThaUnknown/miru/commit/32d1d03d11b380249e1f01b4cbbcb2f22591c403))
- Double-click back button to exit (removed for now due to above)
- Customizable seek duration ([implemented on miru](https://github.com/ThaUnknown/miru/commit/246e713c6e0eb3522d91dea9ecd2e9e29676ccbc) **without PR's author**) [[PR](https://github.com/ThaUnknown/miru/pull/391)]
- Right click or long press on RSS Section will open the anime episode list ([implemented on miru](https://github.com/ThaUnknown/miru/commit/1d05a71b39f725d7e193c35041818fc9a3857ac5))
- Toggleable auto skip intro/outro ([implemented on miru](https://github.com/ThaUnknown/miru/commit/848726bd2397b857a7c6e954e27e50130dd86db8)) (**Possibly that's inspired by Mr NoCrypt's commit since it includes indonesia langugage and using `:active` instead of `:hover`**)
- Home section re-ordering on android ([implemented on miru](https://github.com/ThaUnknown/miru/commit/a50b78590f2d024d5f2237edca44a1ed16d1aa2f)) (**Possibly that's [Mr NoCrypt's commit](https://github.com/NoCrypt/migu/commit/2ff58ca5bbd3390baaf87ac7a20b042810b549d1)**)

<br>

> Hey ThaUnknown, It's fine if you want to commit features from this repo. But please if possible co-author the people who made said features. I genuinely kinda feel bad for the guy who [PR'ed](https://github.com/ThaUnknown/miru/pull/391) the Seek Duration on your repo.

</details>



## **Building and Development**

<sub>[~~*good luck he said lol. he doesn't want others to build. why? $$$$$$$$ 😂*~~](https://github.com/ThaUnknown/miru/#:~:text=Building%20and%20Development-,good%20luck,-Dependencies%3A)</sub>

<u>***Please do! I highly encourage this!***</u>
thanks to wonderful person:[NoCrypt](https://github.com/NoCrypt) for providing this amazing instructions.
### Requirements
- PNPM (or any package manager)
- NodeJS 20+
- Docker (with WSL support if you're on Windows)
- AND 
- Android Studio (SDK 34)
- Java 21 (JDK)

### Building for PC (Electron)
1. Navigate to the Electron directory:
   ```bash
   cd electron
   ```
2. Install dependencies:
   ```bash
   pnpm install
   ```
3. Development:
   ```bash
   pnpm start
   ```
4. Release:
   ```bash
   pnpm build
   ```

### Building for Android (Capacitor)
1. Navigate to the Capacitor directory:
   ```bash
   cd capacitor
   ```
2. Install dependencies:
   ```bash
   pnpm install
   ```
3. Check what's missing:
   ```bash
   pnpm exec cap doctor
   ```
4. (First time only) Build native code:
   - Windows:
     ```bash
     pnpm build:native-win
     ```
   - Linux:
     ```bash
     pnpm build:native
     ```
5. (Optional) Generate assets (if built-in forked capacitor/assets doesn’t work):
   ```bash
   pnpm dlx @capacitor/assets generate --iconBackgroundColor #20a2ff --iconBackgroundColorDark #20a2ff --splashBackgroundColor #20a2ff --splashBackgroundColorDark #20a2ff --android
   ```
6. Open the Android project:
   ```bash
   pnpm exec cap open android
   ```
7. Connect your phone with ADB.
8. Development:
   ```bash
   pnpm dev:start
   ```
9. Release:
   ```bash
   pnpm build:app
   ```

## License

This project acknowledges and complies with the GPLv3 license.
