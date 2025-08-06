# Setup: ShareX

- ShareX is a automated tool used to `screenshot`, `audio record` and `OCR` to be pasted in `Anki` Cards conveniently
- `Required for mining` to anything that I use

---

## Download and Install

- Install [ShareX](https://getsharex.com/)
- Download [lazyGuide-ShareX-settings-17.0.0](https://drive.google.com/drive/folders/1vxkbfe7tr27NxWP5baFaLLmqnExt-3Ba?usp=sharing)
    - Works on newer ShareX Versions

---

## Setting Up

1. In `ShareX` > `Application Settings` > `Settings` > `Import` > `lazyGuide-ShareX-settings`
    - Ignore the random name files(it's empty), it's residue files that can't be removed upon export

2. In `ShareX` > `Hotkey Settings` > Change the keybinds/name if you like

    ![ShareX Hotkeys](../img/sharex-hotkeys.png){height=300 width=600}

3. On your `Hotkey Settings` look for:
    - `screenshot`
    - `screenshot snip`
    - `screenshot nsfw`
    - `screenshot nsfw snip`
    - `audio`
        - Then for each one: click the `COG` icon > `override screenshot folder` > change the `path`
        - Change the `LazyGuide` with your Anki profile name: `%ApplicationData%\Anki2\**YourAnkiProfileName**\collection.media`
            - Profile name is written on the top left bar of Anki, or `File` > `Profile` to set

            ![ShareX Path](../img/sharex-path.png){height=150 width=300}

4. For `audio`: `Hotkey settings` > `audio` > `screen recorder` > `screen recorder options`
    - Install `recorder devices`
    - Video source: `none`
    - Audio source: `virtual-audio-capturer`

5. Add/Mine the `word` on `Yomitan` first before using `screenshot` or `audio record` hotkey using `ShareX`
    - Make sure `Anki` is running to see the `Add(+)` button
    - Check out the [Mining Demo](index.md/#mining-demo)!

You are done setting up ShareX, next is Visual Novel for PC

[Proceed to VN on PC Setup](setupVnOnPC.md){ .md-button .md-button }

<small>If you have any problems check [FAQs](setupShareX.md/#faqs)</small>

---

## Extra Info and Tips

#### Info 1: Mining Demo

??? info "Mining Demo <small>(click here)</small>"

    Don't forget the Mining Demo!
    
    <iframe width="560" height="315" src="https://www.youtube.com/embed/tUiXU2gn75g" title="Mining Demo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

#### Info 2: Hotkey Function

??? info "Hotkey Function <small>(click here)</small>"

    - `screenshot` and `screenshot nsfw`: Captures your whole main screen
        - If you want to edit which monitor: `Hotkey settings` > `screenshot` > `Capture` > `Select region...`

    - `screenshot snip` and `screenshot nsfw snip`: Captures the region that you specify, similar to cropping

    - `OCR (manga_ocr)` is used in [Manga OCR](setupMangaOnPC.md/#setup-mangaocr) while `OCR` is your default ShareX OCR

#### Tip 1: Skip Audio Recording when Mining

??? tip "Skip Audio Recording when Mining <small>(click here)</small>"

    - You can skip the audio recording when mining as it is time consuming

    - If you also manage to do your Anki Cards below 5s each, you will barely hear the recorded Audio

---

## One-handed Mining using Mouse

??? info "One-handed Mining using Mouse <small>(click here)</small>"

    Download and Install [Autohotkey](https://www.autohotkey.com/)

    Download and Run Hotkeys from [here](https://drive.google.com/drive/folders/1ex79TQF7yAliekkR_4q3LK6PhueSM_wK?usp=sharing)

    #### Option 1: Alt + Screenshot Hotkey

    - Forward Mouse button = ALT for monolingual pop-up
    - Back Mouse button = Screenshot (non nsfw)

    #### Option 2: Audio + Screenshot Hotkey

    - Forward Mouse button = Audio recording
    - Back Mouse button = Screenshot (non nsfw)

    #### Option 3: Screenshot (NSFW) + Screenshot (non nsfw) Hotkey

    - Forward Mouse button = Screenshot
    - Back Mouse button = Screenshot (non nsfw)

---

## FAQs
