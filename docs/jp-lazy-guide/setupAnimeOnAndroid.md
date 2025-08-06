# Setup: Anime on Android

- `asbplayer` is a browser video player that supports uploading of `Anime` and `subtitle` to be able hover over the words to use `Yomitan`

---

## Download and Install

- Download your `Anime` and `JP Subtitle`
    - To get `JP subtitles` go to [Jimaku](https://jimaku.cc/)

- (Optional) For streaming video, download [asbplayer](https://chromewebstore.google.com/detail/asbplayer-language-learni/hkledmpjpaehamkiehglnbelcpdflcab) extension

Requirements

- [Yomitan on Android](setupYomitanOnAndroid.md) already set-up

---

## Setting Up

1. In your browser, go to `edge://flags`
    - Search for `Experimental Web Platform features` > `Enabled`

    ![Enable Experimental Web Platform Android](../img/enable-experimental-web-platform-android.png){height=200 width=400}

2. Go to [asbplayer](https://killergerbah.github.io/asbplayer/)
    - Ignore `request permission` to `Anki` and installing of `Chrome extension`

3. Upload your `Anime` and `Subtitle` to the `asbplayer` by clicking the `folder` icon on the top left

    === "Upload Files"
        ![Pick Anime Android](../img/pick-anime-android.png){height=200 width=400}
    === "Pick Anime and Sub"
        ![Pick Anime & Subtitle Android](../img/pick-anime-sub-android.png){height=200 width=400}

4. `Landscape` your `Android` to have a proper view of the `asbplayer` and click the button on the top-right to `full-screen`

    ![Android Player Buttons](../img/android-player-buttons.png){height=400 width=800}

5. You can now mine with `Yomitan` by hovering over the words on the subtitle
    - See [Anime Mining Demo](setupAnimeOnPC.md/#info-1-anime-mining-demo)
    - Unfortunately, to get `Picture`, `screenshot` manually and upload it to your card details in `Ankidroid`

    ![Android Player Mining](../img/android-player-mining.png){height=400 width=800}


Wow! Setting up the Mining tools is finally done, how about checking Sub Guide?

[Proceed to Sub Guide](subGuide.md){ .md-button .md-button }

<small>If you have any problems check [FAQs](setupAnimeOnAndroid.md/#faqs)</small>

---

## Extra Info and Tips

#### Info 1: Anime Mining Demo

??? info "Anime Mining Demo <small>(click here)</small>"

    <iframe width="560" height="315" src="https://www.youtube.com/embed/MAiNi_ME6zw" title="Mining Demo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

#### Tip 1: Synchronizing Subtitle

??? tip "Synchronizing Subtitle <small>(click here)</small>"

    Depending on the source of your `Anime`, the `Subtitle` could be out of sync, to remedy that problem:

    - +100ms - `CTRL + SHIFT + LEFT ARROW KEY`

    - -100ms - `CTRL + SHIFT + RIGHT ARROW KEY`

#### Tip 2: Skip Audio Recording when Mining

??? tip "Skip Audio Recording when Mining <small>(click here)</small>"

    - You can skip the audio recording when mining as it is time consuming

    - If you also manage to do your Anki Cards below 5s each, you will barely hear the recorded Audio

---

## FAQs

#### Question 1: How to use Monolingual Setup on Android?

??? question "How to use Monolingual Setup on Android? <small>(click here)</small>"

    1. Go to your `Yomitan` settings > `Dictionary` > Enable `all`

        ![Dictionary Toggle](../img/dictionary-toggle.png){height=250 width=500}

#### Question 2: Why Enable Experimental Web Platform features?

??? question "Why Enable Experimental Web Platform features? <small>(click here)</small>"

    - Some `Anime` have multiple `audio sources` such as `en` and `jp`, by enabling this we can pick `jp` source if it's not the default

#### Question 3: Why Ignore Request Permission to Anki?

??? question "Why Ignore Request Permission to Anki? <small>(click here)</small>"

    - Because we are using the normal method where we can use the full features of `Anki` and `Yomitan` setup

#### Question 4: Why not install the Chrome Extension?

??? question "Why not install the Chrome Extension? <small>(click here)</small>"

    - Same as `Question 3`, `asbplayer` has a built-in `Anki` support that lacks the feature of our own `Anki` and `Yomitan` support