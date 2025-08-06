# Setup Yomitan Android

- Yomitan is a word hover dictionary for Japanese
- Used for `mining` to `Anki`
- Yomitan [Light](../img/yomitan-light.png) | [Dark](../img/yomitan-dark.png) Mode ([CSS](https://pastebin.com/T9EkQQwm))

---

## Download and Install

- Install [Edge Canary](https://play.google.com/store/apps/details?id=com.microsoft.emmx.canary)

- Download from [here](https://drive.google.com/drive/folders/1DHJ18Lk2_tVYWJ1Adhe8XByuyFBGuTr_?usp=sharing):
    - `Font`
    - `yomitan dictionary`
    - `lazyGuide-yomitan-settings`(download both)

- After Downloading:
    - Extract([?](https://www.webhostinghub.com/help/learn/website/managing-files/extract-file)) `Font.7z` and `yomitan dictionary.7z` (Pass: `lazyguide`)
    - `yomitan dictionary.7z` should only be extracted once, `don't extract the dictionary` itself

---

## Setting Up

1. Go to `Menu` > `Settings` > `About Microsoft Edge` > `Privacy and Terms` > tap `Edge Canary build number` 7 times
    - `Developer Options` should be enabled

    ![Edge Canary Build Number](../img/edge-canary-build-number.png){height=200 width=400}

2. Go back in `Settings` > `Developer Options` > `Extension install by id` > paste this:
    ```
    idelnfbbmikgfiejhgmddlbkfgiifnnn
    ```

3. Click `Add` Yomitan Extension then wait a moment until it finishes downloading
    - The `Welcome Page` should appear automatically or go to `Settings` > `Extensions` > Tap `Yomitan Popup Dictionary` > `Settings(Cog Icon)`

4. On the `Welcome Page` turn on `Enable optional permissions`

    ![Enable optional permissions](../img/enable-optional-permissions.png){height=200 width=400}

5. Next, go to `Settings Page` or `Settings` > `Extensions` > Tap `Yomitan Popup Dictionary` > `Settings(Cog Icon)`

6. Go to `Dictionary` > `Configure installed and enabled dictionaries...` > `Import`
    - Import all the dictionaries from `yomitan dictionary` folder (You can select them all and import all at once)
    - Turn ON `Jitendex` and put it as priority #1 (very top)

    ![Dictionary Import](../img/yomitan-dictionary-import.png){height=250 width=500}

7. Then Scroll down, in `Backup` > `Import Settings` > `lazyGuide-yomitan-settings` (the file from [here](setupYomitanOnAndroid.md/#download-and-install))
    - Pick either:
        - `lazyGuide-local-audio-yomitan-settings` (Install: [Yomitan Local Audio](setupYomitanOnAndroid.md/#info-1-android-yomitan-local-audio))
        - `lazyGuide-non-local-audio-yomitan-settings`

        ![Yomitan Import Settings](../img/yomitan-import-settings.png){align=left height=300 width=600}

8. Pick `Android (Anime, LN & Manga)` profile (`Default` and `Editing`)

    ![Yomitan Profile](../img/yomitan-profile-android.png){align=left height=300 width=600}

Yomitan setup is done, next is ShareX for convenient Mining

[Proceed to ShareX Setup](setupShareX.md){ .md-button .md-button }

<small>If you have any problems check [FAQs](setupYomitanOnAndroid.md/#faqs)</small>

---

## Extra Info and Tips

#### Info 1: Android Yomitan Local Audio

??? info "Android Yomitan Local Audio <small>(click here)</small>"

    Requirements:
    
    - Make sure you have [PC Yomitan Local Audio](setupYomitanOnPC.md/#info-1-yomitan-local-audio) setup

    - You have [Ankiconnect Android](https://github.com/KamWithK/AnkiconnectAndroid/releases/latest) installed

    - Here's the [source](https://github.com/Aquafina-water-bottle/AnkiconnectAndroid/tree/local_audio#additional-instructions-local-audio) for more info or updates

    - This setup takes **3gb+** of space

    ---

    1. Within `Anki` on `PC`: `Tools` > `Local Audio Server` > `Generate Android database`
        - This would take 30mins+ (Anki will be unuseable but you can mine)
    
    2. Within `Anki` on `PC`: either `Ctrl + Shift + A` or `Tools` > `Add-ons` > select `Local Audio Server for Yomitan` > `View Files`
        - There will be a file named `android` or `android.db`

    3. On your android, open `AnkiConnect Android` > `Settings` > `Print Local Audio Directory`
        - This will show you the path as well as generate the folder
    
    4. On that location from 3rd step, usually: `Android/data/com.kamwithk.ankiconnectandroid/files/`
        - Paste the `android` file ON `files` folder from `PC` (2nd step)
        - The result should be: `Android/data/com.kamwithk.ankiconnectandroid/files/android.db`
    
    5. My `local-audio-yomitan-settings` profile: `Android (Anime, LN & Manga)`
        - OR if you are not using my profile:
            - Go to `Yomitan settings` > `Audio` > `Configure audio playback sources...` > `Add` > `Custom URL (JSON)`
            - Paste `http://localhost:8765/localaudio/get/?sources=jpod,jpod_alternate,nhk16,forvo&term={term}&reading={reading}` and make sure it's on the top
    
    6. To ensure it's working, check that all sources are present
        - If it doesn't work, make sure AnkiConnect Android `Start Service` is running
        - Battery saving/optimization is off for AnkiConnect Android, Ankidroid and Edge Canary

        ![Yomitan Local Audio Check](../img/yomitan-local-audio-check.gif){height=250 width=500}

        DONE!

#### Info 2: Yomitan Light and Dark Mode

??? info "Yomitan Light and Dark Mode <small>(click here)</small>"

    To change the Yomitan theme, go to `Yomitan settings` > `Appearance` > `Theme`

    ![Yomitan Theme](../img/yomitan-theme.png){height=300 width=600}

---

## FAQs

#### Question 1: Can I add a Yomitan dictionary of my choice?

??? question "Can I add, delete or modify a Yomitan dictionary of my choice? <small>(click here)</small>"

    - Yes, most dictionaries should be compatible with the Anki format

#### Question 2: When will you update the dictionaries/should I do it myself?

??? question "When will you update the dictionaries/should I do it myself? <small>(click here)</small>"

    - I will seldomly update; no need to stress over the latest one; it barely changes its content as a dictionary
        - My goal is longterm stability without worrying about updates
        - You can update it youself if you want to chase the latest fad

#### Question 3: How can I use sentence card?

??? question "How can I use sentence card? <small>(click here)</small>"

    In your `Yomitan settings` > `Anki` > `configure Anki card format...`

    ![Sentence Card Instruction 1](../img/sentence-card-instruction-1.png){height=300 width=600}
    
    In `Terms` scroll down and find `IsSentenceCard` and put `1` then close the window

    ![Sentence Card Instruction 2](../img/sentence-card-instruction-2.png){height=300 width=600}

    Now apply it on every profile under `Editing Profile` and make sure `Monolingual`, `Bilingual`, `Android (Anime, LN & Manga)` and `Android (VN)` got their config changed

    ![Yomitan Profile](../img/yomitan-profiles.png){align=left height=300 width=600}
