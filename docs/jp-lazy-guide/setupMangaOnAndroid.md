# Setup: Manga on Android

- You can use your `Android` to read `Manga` using `Edge Canary` to scan words using `yomitan` on it

- This includes automated `Manga` screenshot even if you are in `Android`

---

## Download and Install

- Download and Install [Ankiconnect Android](https://github.com/KamWithK/AnkiconnectAndroid/releases/latest/) in Assets `.apk` file

- Install [Ankidroid](https://play.google.com/store/apps/details?id=com.ichi2.anki)

Requirements:

- [Yomitan On Android](setupYomitanOnAndroid.md) already set-up

- Processed Manga from [Setup: Mokuro Manga](setupMangaOnPC.md/#setup-mokuro-manga)

- File compressor such as [7z](https://www.7-zip.org/)

---

## Setting Up

1. Compress your Manga files(the one that contain `img` or `.png` files) into `.zip` format (NOT `.7z`)
    - To compress, `Right click` on the folder > `7-Zip` > `Compress...` > `Archive Format: .zip` > `OK`

2. Transfer your `Processed Manga` to your `Android` device
    - ALL the files: the compressed `manga` .zip file itself, `_ocr` and `.mokuro` file

3. Open `Ankiconnect Android` > `settings` > `CORS Host` > `https://reader.mokuro.app`

    ![CORS Host](../img/cors-host.png){height=200 width=400}

4. `Start the Service` on `AnkiConnect Android` and make sure `AnkiDroid` is also opened

5. Open your `Edge Canary` > go to [Mokuro Reader](https://reader.mokuro.app/) > `Upload` icon (top right) > `choose files` (NOT `choose directory`)
    - Go to the directory of your manga and upload `.html`, `.mokuro` and `.zip` files (from `Step 2`)

    ![Mokuro Android Upload](../img/mokuro-upload-android.png){height=150 width=300}

    ??? examplecode "Folder Structure <small>(click here)</small>"
        
        ```
        ├── Manga Folder
        │   ├── _ocr folder
        │   ├── .html
        │   ├── .mokuro
        │   └── .zip
        │    │    └── manga img file (.jpg/.png)
        ```



6. In the top right, go to `settings` > `Profile` > `Select a File` > [Mokuro Profile](https://drive.google.com/drive/folders/17EzQL9ONQ3MVsCJwC7ejmL0317EwdR--?usp=sharing) > `Import Profiles` > Select `Mobile Profile`
    - Alternatively you can make your own profile just make sure to set-up everything on `Anki Connect` portion

7. To be able to mine, simply add the word using `Yomitan` by `Tap Holding` to scan the word
    - To screenshot, make sure to double click/tap inside the `text border` (its invisible by default)

    ![Mokuro Settings](../img/mokuro-yomitan.png){height=400 width=800}

8. You should now be able to mine and screenshot in your Manga with ease

You are now finally done in setting up Manga Mining in Android, how about checking out Anime Mining?

[Proceed to Setup: Anime on PC Setup](setupAnimeOnPC.md){ .md-button .md-button }

<small>If you have any problems check [FAQs](setupMangaOnAndroid.md/#faqs)</small>

---

## Extra Info and Tips

#### Info 1: Android Mining Demo

??? info "Android Mining Demo <small>(click here)</small>"

    - Mining Demo with Manga screenshot
    - This is `outdated` but shows the fundamental function
    - To actually screenshot you need to double tap or hold tap on the `text border`

    ![Android Manga Mining](../img/android-manga-mining.gif){height=200 width=400}

## FAQs

#### Question 1: How to use Monolingual Setup on Android?

??? question "How to use Monolingual Setup on Android? <small>(click here)</small>"

    1. Go to your `Yomitan` settings > `Dictionary` > Enable `all`

        ![Dictionary Toggle](../img/dictionary-toggle.png){height=250 width=500}