---
hide:
  - footer
---

- I recommend you to follow the current guide that's not on the Archive

??? danger "I'm aware that this is an Archive <small>(click here)</small>"

    # Setup: VN on PC

    - [Textractor](setupVnOnPCOld.md/#setup-textractor) is a tool used to extract `text` from `Visual Novels`

    - [Clipboard Inserter](setupVnOnPCOld.md/#setup-clipboard-inserter) is used to copy and paste the text extracted by `Textractor` into a `Texthooker` page where you can use `Yomitan` to scan the words and mine it into `Anki`

    ---

    Requirements:

    - [Yomitan On PC](setupYomitanOnPC.md) already set-up

    - Download [Textractor 5.2.0](https://drive.google.com/drive/folders/1wm2mjxBdrkb4TR9WtUc4aLfaCAoC3EUF?usp=sharing) and extract([?](https://www.webhostinghub.com/help/learn/website/managing-files/extract-file)) (Pass: `lazyguide`)
        
        - Some versions are messed up so I recommend sticking to this
        
        - (Optional) If you don't want to `Alt + Tab` or don't have a 2nd monitor to display `Texthooker Page`:
            - [VN Texthooker on Android](https://rentry.co/android-texthook) and [Android Setup](setupLnOnAndroid.md)

    [Clipboard Inserter](setupVnOnPCOld.md/#setup-clipboard-inserter)

    - Download `Clipboard Inserter` from [Chrome/Edge](https://chrome.google.com/webstore/detail/clipboard-inserter/deahejllghicakhplliloeheabddjajm) or [Firefox](https://addons.mozilla.org/en-US/firefox/addon/lap-clipboard-inserter/)

    - `Clipboard Inserter` is used with `Texthooker Page` from the [Textractor 5.2.0](https://drive.google.com/drive/folders/1wm2mjxBdrkb4TR9WtUc4aLfaCAoC3EUF?usp=sharing) and extract([?](https://www.webhostinghub.com/help/learn/website/managing-files/extract-file)) (Pass: `lazyguide`)
        - Alternative [Texthooker Page w/Websocket](https://github.com/Renji-XD/texthooker-ui) (only for know-how)


    Set the System Locale - JP

    - This is required for `Visual Novel` to `run`

    ??? note "Set: System Locale - JP <small>(click here)</small>"

        1. In your `PC`, press `Win + R` key

        2. Type `intl.cpl` > `enter`

        3. `Administrative` > `Change System Locale...` > `Japanese (Japan)` > Restart your `PC`
            - This doesn't affect your `language` on `PC`

            ![System Locale JP](../img/system-locale-jp.png){height=250 width=500}

    ---

    ## Setup: Textractor

    1. Open the `Textractor` folder > `x86` > `Textractor`
        - 99% of the time `x86` is better
        - You can also create a `shortcut` or pin it to your taskbar

        ![Textractor App](../img/textractor-app.png){height=250 width=500}

    2. Open `Textractor` app and check `Extensions`, if something is missing from my list, you can drag it from the folder into the extension window

        ![Textractor Extensions](../img/textractor-extensions.png){height=500 width=1000}

    3. Open your `Visual Novel` then on your `Textractor` > `Attach to game` > `Find your Visual Novel`
        - Sometimes it is named engine, not actual VN name e.g. SiglusEngine
        - It should look like this after attaching

            ![Textracting](../img/textracting.png){height=500 width=1000}

    4. On your `Visual Novel`, play it so it can generate the text from the game, after 1-2 dialogues, check back on your `Texthooker` and find a `suitable hooked text` from the drop-down menu
        - Check [Extra Info and Tips](setupVnOnPC.md/#extra-info-and-tips) if you have trouble finding the proper hook or the text is messy

    5. If it's working properly it should look like this:
        - Click `Save hook(s)` if everything is alright

    === "Textractor and Regex Filter"
        ![Textractor Working](../img/textractor-working.png){height=300 width=600}
    === "Visual Novel Sample"
        ![Visual Novel Sample](../img/visual-novel-sample.png){height=500 width=1000}

    It is now texthooking, proceed to [Clipboard Inserter](setupVnOnPCOld.md/#setup-clipboard-inserter) to be able to use the text from `Textractor` and use `Yomitan` on it

    ---

    ## Setup: Clipboard Inserter

    1. Go to `chrome://extensions` or `edge://extensions` or `about:addons`(firefox) and go to `Clipboard Inserter` extension settings

    2. Make sure for:
        - Chrome/Edge: `Allow access to file URLs` is enabled
        - Firefox: `Access your data for all websites` is enabled

        === "Chrome/Edge"
            ![Chrome/Edge URL Access](../img/chromium-url-access.png){height=150 width=300}
        === "Firefox"
            ![Firefox Yomitan Access to all websites](../img/firefox-url-access.png){height=300 width=600}

    3. Go to `Textractor 5.2.0` folder and open `texthooker` page

        ![Texthooker PC Page](../img/texthooker-pc-page.png){height=150 width=300}

    4. Turn on `Clipboard Inserter` Extension by clicking on it at the `Texthooker Page` located at the top right

        ![Clipboard Inserter](../img/clipboard-inserter.png){height=50 width=100}

    5. If working as intended it should paste anything you copy or from textractor:
        - You can now use Yomitan on it

        ![Texthooker Working](../img/texthooker-paste.png){height=300 width=600}


    Now that the Clipboard Inserter is working, let's proceed on knowing how to play Visual Novel on Android

    [Proceed to VN on Android Setup](setupVnOnAndroid.md){ .md-button .md-button }

    <small>If you have any problems check [FAQs](setupVnOnPCOld.md/#faqs)</small>

    ---

    ## Extra Info and Tips

    #### Info 1: Finding the proper texthook

    ??? info "Finding the proper texthook <small>(click here)</small>"

        - Some VNs is hard to hook, messed and/or missing text, on which case **you need to manually find a hook**([video guide](https://www.youtube.com/watch?v=eecEOacF6mw)) or **search the internet for one** (e.g. Riddle Joker hookcode) then `add hook` > `save hook`

        - Some **VNs problem is the version itself**, you'll be safe using `JP` only version rather than steam/multi-language versions

    #### Info 2: Using Regex to remove unnecessary text

    ??? info "Using Regex to remove unnecessary text <small>(click here)</small>"

        - When all text is present **but there is unnecessary unwanted text**, you need to use [regex filter](https://github.com/Artikash/Textractor/wiki/FAQ#textractor-is-extracting-text-mostly-correctly-but-theres-some-extra-characters-as-markupgarbage-eg-a-n-in-place-of-every-line-break-is-there-a-way-to-clean-the-text) which is usually on the 2nd tab of Textractor

        - For regex you need some techy knowledge or search around for a specific VN

    #### Info 3: Setting the dialogue speed to max to prevent missing text

    ??? info "Setting the dialogue speed to max to prevent missing text <small>(click here)</small>"

        - Some Visual Novels are sensitive, and that it will only textract a portion of its text since the dialogue appeared slowly
            - Max up the dialogue speed in the VN settings

    #### Tip 1: Getting Visual Novels

    ??? tip "Getting Visual Novels <small>(click here)</small>"

        To get VNs, search around the web, go to `nyaa` or discord servers that have them or `BUY` them

        - If you pm me, I can give you more details

    ## FAQs