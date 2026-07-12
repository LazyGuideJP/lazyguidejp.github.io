---
hide:
  - footer
---

- すべてのガイドを1ページにまとめています。多くの手順が元のガイドと分岐するためです。
    - 混乱を避けるため、不要なガイド（例：Yomitan）がある場合はその都度記載します。

- 作業中
    - [自動スクリーンショット](setupLinux.md/#screenshot-mining)には対応していますが、自動音声録音にはまだ対応していません。（必要であれば[GSM](https://github.com/bpwhelan/GameSentenceMiner)も使えますが、私の「Lazy」スタイルには少し機能が多すぎます。）

---

??? note "事前にインストールするパッケージ <small>(クリックして開く)</small>"
    ## 事前にインストールするパッケージ

    このガイドを最初から最後まで進める予定であれば、以下をまとめてインストールしてください。

    **Pacman**

    - 7zip（任意）
    - Anki
    - Flatpak
    - Python（OCR・マンガ用）
    - Zen Browser（任意・Firefoxベース）
    - Fcitx5
    - Mozc
    - Noto Sans JP
    ```
    sudo pacman -S p7zip anki flatpak python python-pip tk zen-browser-bin fcitx5-im fcitx5-mozc noto-fonts-cjk
    ```

    **Flatpak**

    - OBS Studio
    ```
    flatpak install flathub -y com.obsproject.Studio
    ```

    **Paru (AUR)**

    - Faugus Launcher（ビジュアルノベル用）
    ```
    paru -S --noconfirm faugus-launcher
    ```

---

??? note "日本語入力とフォント表示 <small>(クリックして開く)</small>"
    ## 日本語入力とフォント表示

    **日本語入力のインストール**

    1. まず、`fcitx5`、`mozc`、`Noto Sans JP`フォントをインストールします。
    ```
    sudo pacman -S fcitx5-im fcitx5-mozc noto-fonts-cjk
    ```

    2. ファイルを作成して開きます。
    ```
    mkdir -p ~/.config/environment.d
    nano ~/.config/environment.d/fcitx.conf
    ```

    3. 以下の設定を貼り付けます。
    ```
    GTK_IM_MODULE=fcitx
    QT_IM_MODULE=fcitx
    SDL_IM_MODULE=fcitx
    XMODIFIERS=@im=fcitx
    ```

    4. `CTRL + O` → `ENTER` → `CTRL + X`で保存して終了します。

    5. ターミナルを閉じて構いません。

    **日本語入力の設定**

    1. PCを再ログインまたは再起動します。

    2. KDE システム設定 → キーボード → 仮想キーボード → `Fcitx 5 Wayland Launcher` を選択します。

    3. KDE システム設定 → キーボード → キーバインドの設定 → 日本語キーボードオプション → **「全角/半角キーを追加のEscキーとして使用」** を **OFF** にします。

    4. KDE システム設定 → 入力メソッド → `Mozc` を追加します。（既に追加されている場合もあります。）

    **フォント表示**

    1. `~/.config/fontconfig/fonts.conf` を開きます。

    2. `fonts.conf` の内容を、[Arch Wiki](https://wiki.archlinux.org/title/Font_configuration/Examples#CJK,_but_other_Latin_fonts_are_preferred) を参考に、以下の設定へ置き換えます。

        ??? note "font.conf <small>(クリックして開く)</small>"
            ```
            <?xml version="1.0"?>
            <!DOCTYPE fontconfig SYSTEM "urn:fontconfig:fonts.dtd">
            <fontconfig>
            <!-- Default serif font -->
            <alias binding="strong">
                <family>serif</family>
                <prefer>
                <family>PT Serif</family>
                </prefer>
            </alias>

            <!-- Default sans-serif font -->
            <alias binding="strong">
                <family>sans-serif</family>
                <prefer>
                <family>Roboto</family>
                </prefer>
            </alias>

            <!-- Default monospace font -->
            <alias binding="strong">
                <family>monospace</family>
                <prefer>
                <family>Cascadia Code PL</family>
                </prefer>
            </alias>

            <!-- Default system-ui font -->
            <alias binding="strong">
                <family>system-ui</family>
                <prefer>
                <family>Roboto</family>
                </prefer>
            </alias>

            <!-- Serif CJK -->

            <!-- Default serif when the "lang" attribute is not given -->
            <!-- You can change this font to the language variant you want -->
            <match target="pattern">
                <test name="family">
                <string>serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Serif CJK SC</string>
                </edit>
            </match>

            <!-- Japanese -->
            <!-- "lang=ja" or "lang=ja-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>ja</string>
                </test>
                <test name="family">
                <string>serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Serif CJK JP</string>
                </edit>
            </match>

            <!-- Korean -->
            <!-- "lang=ko" or "lang=ko-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>ko</string>
                </test>
                <test name="family">
                <string>serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Serif CJK KR</string>
                </edit>
            </match>

            <!-- Chinese -->
            <!-- "lang=zh" or "lang=zh-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh</string>
                </test>
                <test name="family">
                <string>serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Serif CJK SC</string>
                </edit>
            </match>
            <!-- "lang=zh-hans" or "lang=zh-hans-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hans</string>
                </test>
                <test name="family">
                <string>serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Serif CJK SC</string>
                </edit>
            </match>
            <!-- "lang=zh-hant" or "lang=zh-hant-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hant</string>
                </test>
                <test name="family">
                <string>serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Serif CJK TC</string>
                </edit>
            </match>
            <!-- Compatible -->
            <!-- "lang=zh-cn" or "lang=zh-cn-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-cn</string>
                </test>
                <test name="family">
                <string>serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Serif CJK SC</string>
                </edit>
            </match>
            <!-- "lang=zh-tw" or "lang=zh-tw-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-tw</string>
                </test>
                <test name="family">
                <string>serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Serif CJK TC</string>
                </edit>
            </match>

            <!-- Sans CJK -->

            <!-- Default sans-serif when the "lang" attribute is not given -->
            <!-- You can change this font to the language variant you want -->
            <match target="pattern">
                <test name="family">
                <string>sans-serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK SC</string>
                </edit>
            </match>

            <!-- Japanese -->
            <!-- "lang=ja" or "lang=ja-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>ja</string>
                </test>
                <test name="family">
                <string>sans-serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK JP</string>
                </edit>
            </match>

            <!-- Korean -->
            <!-- "lang=ko" or "lang=ko-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>ko</string>
                </test>
                <test name="family">
                <string>sans-serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK KR</string>
                </edit>
            </match>

            <!-- Chinese -->
            <!-- "lang=zh" or "lang=zh-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh</string>
                </test>
                <test name="family">
                <string>sans-serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK SC</string>
                </edit>
            </match>
            <!-- "lang=zh-hans" or "lang=zh-hans-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hans</string>
                </test>
                <test name="family">
                <string>sans-serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK SC</string>
                </edit>
            </match>
            <!-- "lang=zh-hant" or "lang=zh-hant-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hant</string>
                </test>
                <test name="family">
                <string>sans-serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK TC</string>
                </edit>
            </match>
            <!-- "lang=zh-hant-hk" or "lang=zh-hant-hk-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hant-hk</string>
                </test>
                <test name="family">
                <string>sans-serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK HK</string>
                </edit>
            </match>
            <!-- Compatible -->
            <!-- "lang=zh-cn" or "lang=zh-cn-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-cn</string>
                </test>
                <test name="family">
                <string>sans-serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK SC</string>
                </edit>
            </match>
            <!-- "lang=zh-tw" or "lang=zh-tw-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-tw</string>
                </test>
                <test name="family">
                <string>sans-serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK TC</string>
                </edit>
            </match>
            <!-- "lang=zh-hk" or "lang=zh-hk-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hk</string>
                </test>
                <test name="family">
                <string>sans-serif</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK HK</string>
                </edit>
            </match>

            <!-- Mono CJK -->

            <!-- Default monospace when the "lang" attribute is not given -->
            <!-- You can change this font to the language variant you want -->
            <match target="pattern">
                <test name="family">
                <string>monospace</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans Mono CJK SC</string>
                </edit>
            </match>

            <!-- Japanese -->
            <!-- "lang=ja" or "lang=ja-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>ja</string>
                </test>
                <test name="family">
                <string>monospace</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans Mono CJK JP</string>
                </edit>
            </match>

            <!-- Korean -->
            <!-- "lang=ko" or "lang=ko-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>ko</string>
                </test>
                <test name="family">
                <string>monospace</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans Mono CJK KR</string>
                </edit>
            </match>

            <!-- Chinese -->
            <!-- "lang=zh" or "lang=zh-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh</string>
                </test>
                <test name="family">
                <string>monospace</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans Mono CJK SC</string>
                </edit>
            </match>
            <!-- "lang=zh-hans" or "lang=zh-hans-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hans</string>
                </test>
                <test name="family">
                <string>monospace</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans Mono CJK SC</string>
                </edit>
            </match>
            <!-- "lang=zh-hant" or "lang=zh-hant-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hant</string>
                </test>
                <test name="family">
                <string>monospace</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans Mono CJK TC</string>
                </edit>
            </match>
            <!-- "lang=zh-hant-hk" or "lang=zh-hant-hk-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hant-hk</string>
                </test>
                <test name="family">
                <string>monospace</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans Mono CJK HK</string>
                </edit>
            </match>
            <!-- Compatible -->
            <!-- "lang=zh-cn" or "lang=zh-cn-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-cn</string>
                </test>
                <test name="family">
                <string>monospace</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans Mono CJK SC</string>
                </edit>
            </match>
            <!-- "lang=zh-tw" or "lang=zh-tw-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-tw</string>
                </test>
                <test name="family">
                <string>monospace</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans Mono CJK TC</string>
                </edit>
            </match>
            <!-- "lang=zh-hk" or "lang=zh-hk-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hk</string>
                </test>
                <test name="family">
                <string>monospace</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans Mono CJK HK</string>
                </edit>
            </match>

            <!-- System UI CJK -->

            <!-- Default system-ui when the "lang" attribute is not given -->
            <!-- You can change this font to the language variant you want -->
            <match target="pattern">
                <test name="family">
                <string>system-ui</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK SC</string>
                </edit>
            </match>

            <!-- Japanese -->
            <!-- "lang=ja" or "lang=ja-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>ja</string>
                </test>
                <test name="family">
                <string>system-ui</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK JP</string>
                </edit>
            </match>

            <!-- Korean -->
            <!-- "lang=ko" or "lang=ko-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>ko</string>
                </test>
                <test name="family">
                <string>system-ui</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK KR</string>
                </edit>
            </match>

            <!-- Chinese -->
            <!-- "lang=zh" or "lang=zh-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh</string>
                </test>
                <test name="family">
                <string>system-ui</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK SC</string>
                </edit>
            </match>
            <!-- "lang=zh-hans" or "lang=zh-hans-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hans</string>
                </test>
                <test name="family">
                <string>system-ui</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK SC</string>
                </edit>
            </match>
            <!-- "lang=zh-hant" or "lang=zh-hant-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hant</string>
                </test>
                <test name="family">
                <string>system-ui</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK TC</string>
                </edit>
            </match>
            <!-- "lang=zh-hant-hk" or "lang=zh-hant-hk-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hant-hk</string>
                </test>
                <test name="family">
                <string>system-ui</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK HK</string>
                </edit>
            </match>
            <!-- Compatible -->
            <!-- "lang=zh-cn" or "lang=zh-cn-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-cn</string>
                </test>
                <test name="family">
                <string>system-ui</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK SC</string>
                </edit>
            </match>
            <!-- "lang=zh-tw" or "lang=zh-tw-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-tw</string>
                </test>
                <test name="family">
                <string>system-ui</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK TC</string>
                </edit>
            </match>
            <!-- "lang=zh-hk" or "lang=zh-hk-*" -->
            <match target="pattern">
                <test name="lang" compare="contains">
                <string>zh-hk</string>
                </test>
                <test name="family">
                <string>system-ui</string>
                </test>
                <edit name="family" mode="append" binding="strong">
                <string>Noto Sans CJK HK</string>
                </edit>
            </match>
            </fontconfig>
            ```

    3. ターミナルで以下のコマンドを実行し、フォントキャッシュを更新します。
    ```
    fc-cache -fv
    ```

    4. Zen Browser または Firefox の設定を開き、**詳細設定**からフォントを `Noto Sans CJK JP` に変更します。

    5. 完了です！

---

???note "Anki <small>(クリックして開く)</small>"
    ## Anki

    **Ankiのインストール**

    - `Anki` をインストールします。

    ```bash
    sudo pacman -S anki
    ```

    **Ankiのセットアップ**

    1. [Setup: Anki](./setupAnki.md) の手順に従ってください。
        - 手順2で `addons` を展開する場所は `~/.var/app/net.ankiweb.Anki/data/Anki2/` です。

    2. 完了です！

---

???note "Yomitan <small>(クリックして開く)</small>"
    ## Yomitan

    **Yomitanのセットアップ**

    1. [Setup: Yomitan PC](./setupYomitanOnPC.md) に進み、Firefox版の手順に従ってください（Zen Browserでも同じ手順です）。

    2. 完了です！

---

???note "自動スクショ <small>(クリックして開く)</small>"
    ## 自動スクショ

    **必要なもの**

    - [auto_screenshot](https://drive.google.com/drive/folders/1L_coaSRpdWoj7fKZFhgkttZROxm3YeHY?usp=sharing) Ankiアドオンをダウンロードします（作成者: kamper）

    - `Anki` と `OBS Studio` をインストールします。

    ```bash
    flatpak install flathub -y com.obsproject.Studio
    ```

    **スクリーンショット採掘のセットアップ**

    1. Ankiを開き、`Ctrl + Shift + A` または `Tools` → `Add-ons` → `View Files` を選択して `addons` フォルダを開きます。

    2. `auto_screenshot.7z`（パスワード: `lazyguide`）を展開し、`auto_screenshot` フォルダを `addons` フォルダへコピーします。

    3. `Anki` を再起動し、`Tools` → `Mining Mode` → `OBS` を選択します（まだ設定していない場合）。
        - スクリーンショット機能を無効にしたい場合は、`OBS Mode` をオフにしてください。

    4. `OBS Studio` を起動し、自動設定ウィザードが表示された場合はスキップします。
        - 左下の `ソース` → `スクリーンキャプチャ`　→ `OK` を選択し、画面全体または特定のアプリケーションを追加します。

            ![OBS Studio - Adding Source](../img/obs-adding-source.png){height=400 width=800}

    5. `OBS Studio` のメニューバーから `Tools` → `WebSocket Server Settings` を開き、`Enable WebSocket Server` を有効にし、`Enable Authentication` を無効にします。

        ![OBS Studio - Websocket](../img/obs-websocket.png){height=300 width=600}

    6. システムトレイの `OBS Studio` アイコンを右クリックし、必要であれば `Hide` を選択します。
        - `Anki` と `OBS Studio` は常に起動した状態にしておいてください。

    7. これで採掘時に、現在設定している `Scene` の内容が自動でスクリーンショットされます。
        - 採掘時にエラーが出る場合は、`Mining Mode: OBS` が有効で `OBS Studio` が起動していることを確認したうえで、`Anki` を再起動してください。

---

???note "「作業中」　ノベルゲーム <small>(クリックして開く)</small>"
    ## ビジュアルノベル

    ※この方法は、現在のところSteam以外のビジュアルノベルのみで動作確認しています。

    **必要なもの**

    - [PC版Yomitan](setupYomitanOnPC.md) のセットアップが完了していること
    - [Textractor 5.2.0](https://drive.google.com/drive/folders/1up23CRT4JDMYeHlhhTISrBQHlLB1xezZ?usp=sharing) をダウンロードして展開([?](https://www.webhostinghub.com/help/learn/website/managing-files/extract-file))してください（パスワード：`lazyguide`）

    - `Faugus Launcher` をインストール
    ```
    paru -S --noconfirm faugus-launcher
    ```

    **システムロケールを日本語に設定**

    1. ターミナルで以下を開きます。
    ```
    sudo nano /etc/locale.gen
    ```

    2. 下へスクロールし、`#ja_JP.UTF-8 UTF-8` の先頭の `#` を削除して、`ja_JP.UTF-8 UTF-8` にします。
        - アルファベット順に並んでいるので、よく探してください。

    3. 次のコマンドを実行します。
    ```
    sudo locale-gen
    ```

    **ビジュアルノベルのセットアップ**

    1. `Faugus Launcher` を開き、`Settings` > `Global Environment Variables` から以下を追加します。
        - `LC_ALL=ja_jp.UTF-8`
        - `TZ=Asia/Tokyo`
        - `PROTON_ENABLE_WAYLAND=0`（任意：動画が再生されないなど、互換性向上のため）
        ![Faugus Launcher - Settings](../img/faugus-launcher-settings.png){height=400 width=800}

    2. `Faugus Launcher` の `＋ (Add)` ボタン > `Game/App` > `Path` から、ビジュアルノベルの `.exe` ファイルを指定します。

    3. VNを右クリック > `Edit` > `Tools` タブ > `Additional Application` を有効化 > `Path` に `Textractor` の `.exe` を指定します（x86版推奨）。
        ![Faugus Launcher - Textractor](../img/faugus-launcher-vn-setup.png){height=400 width=800}

    4. あとは [PC版VNセットアップ](setupVnOnPC.md) の `Textractor` セクションの **手順3** から進めてください。
        - `Textractor` で日本語が □（四角）で表示される場合は、[Info 3: Textractorで日本語が四角になる場合](setupVnOnPC.md/#info-3-textractor-not-showing-japanese-characters-properly-square-like-glyphs) を確認してください。

    5. 完了です！ビジュアルノベルをお楽しみください。

---

???note "「作業中」　小説 <small>(クリックして開く)</small>"
    ## ライトノベル

    **ライトノベルのセットアップ**

    1. [PC版ライトノベルセットアップ](./setupLnOnPC.md) の手順にそのまま従ってください。

    2. 完了です！

---

???note "「作業中」　OCR <small>(クリックして開く)</small>"
    ## OCR

    **OCR関連パッケージのインストール**

    - ターミナルで以下を実行します。
    ```
    sudo pacman -S python python-pip tk
    ```

    **OCRセットアップ**

    1. ターミナルでPython仮想環境を作成します。
    ```
    mkdir -p ~/venvs
    python3 -m venv ~/venvs/jptools-env
    source ~/venvs/jptools-env/bin/activate.fish
    ```

    2. `owocr` をインストールします。
    ```
    pip install "owocr[mangaocr,screenai,lens]"
    ```

    3. 標準スクリーンショットアプリ `Spectacle` を使用します。
        - `Meta + Shift + S` > `オプション`

    4. `General` タブで以下を設定します。
        - スクリーンショット後 > 「画像をクリップボードにコピー」
        - `Region Selection` > 両方とも「何もしない」

    5. `Save Location`（2番目のタブ）へ移動します。
        - 保存先を `"/path/to/your/OCR Picture/"` に設定します。
            - このパスは後述の **手順10** と **OCR Shortcut** でも使用します。

    6. ショートカット
        - `Region Capture（領域を撮影）` を `Meta + Shift + S` に設定します（デフォルトとして使用）。

    7. 撮影後に右下へ表示される通知は、不要であればオフにして構いません。

    8. 使用方法
        - OCR：撮影後に `Save` を押すと、自動でOCRが実行されます。
        - OCRを使わない場合：`Copy`（クリップボードへコピー）または `Save As...` を使用してください。

    9. `OWOCR` はフォルダー（推奨）またはクリップボードのどちらでも使用できます。

    10. フォルダー監視（保存して閉じる）
    ```
    source ~/venvs/jptools-env/bin/activate.fish
    owocr -e glens -w clipboard -j -d -r "/path/to/your/OCR Picture/"
    ```

    11. クリップボード
    ```
    source ~/venvs/jptools-env/bin/activate.fish
    owocr -e screenai -w clipboard -j -d -r clipboard
    ```

    12. 完了です！

    **OCRショートカット（自動起動）**

    1. ショートカットファイルを作成します。
    ```
    mkdir -p ~/scripts
    nano ~/scripts/start_owocr.sh
    ```

    2. 以下を貼り付けて保存します（フォルダー方式推奨）。
        - フォルダー（保存先を変更してください）
        ```
        #!/usr/bin/env fish
        source ~/venvs/jptools-env/bin/activate.fish
        owocr -e lens -w clipboard -j -d -r "/path/to/your/OCR Picture/"
        chmod +x ~/scripts/start_owocr.sh
        ```

        - クリップボード
        ```
        source ~/venvs/jptools-env/bin/activate.fish
        owocr -e lens -w clipboard -j -d -r clipboard
        chmod +x ~/scripts/start_owocr.sh
        ```

    3. KDEの「システム設定」> 「自動起動」から `start_owocr.sh` を追加します（再起動後に自動実行されます）。

    4. （任意）タスクバーの `owocr`（uwuアイコン）> `Configure` > `Engines`
        - Primary：`Chrome Screen AI`
        - Secondary：`Manga OCR (segmented)`

    5. 完了です！

---

???note "「作業中」　漫画 <small>(クリックして開く)</small>"
    ## マンガ

    **マンガ関連パッケージのインストール**

    - ターミナルで以下を実行します。
    ```
    sudo pacman -S python python-pip tk
    ```

    **OCR**

    - [OCR](setupLinux.md/#ocr) の手順を参照してください。

    **Mokuro（オンライン処理）**

    1. [PC版マンガセットアップ - オンライン処理](setupMangaOnPC.md/#online-processing-method) の手順をそのまま実行してください。

    **Mokuro（ローカル処理）**

    1. `owocr` で作成した `jptools-env` 環境をそのまま使えます（Pythonは毎回仮想環境を有効化する必要があります）。
    ```
    source ~/jptools-env/bin/activate.fish
    ```

            初めて仮想環境を作成する場合はこちらを実行してください。
            ```
            python3 -m venv ~/jptools-env
            source ~/jptools-env/bin/activate.fish
            ```

    2. `mokuro` をインストールします。
    ```
    pip3 install mokuro
    ```

    3. ターミナルで以下のいずれかを実行します。
        - マンガ全巻を処理する場合
            - `mokuro --parent_dir F:\Manga\Saenai`
                - パスは実際のフォルダーに置き換えてください。
                - `Saenai` はマンガ名（スペースなし）に変更してください。
                - `Saenai` フォルダー内には `Vol1`、`Vol2`、`Vol3`... のように順番に並べてください。

        - 特定の巻だけ処理する場合
            - `mokuro F:\Manga\Saenai\Vol3`
                - パス、マンガ名、巻数を実際のものに置き換えてください。

        ??? examplecode "フォルダー構成 <small>(クリックして開く)</small>"

            ```
            ├── Manga Folder
            │   ├── _ocr folder
            │   ├── .html
            │   ├── .mokuro
            │   └── .zip
            │       └── マンガ画像 (.jpg/.png)
            ```

    4. 完了です！

    **処理済みマンガを読む**

    1. [PC版マンガセットアップ - 処理済みマンガを読む](setupMangaOnPC.md/#reading-processed-manga) の手順に従ってください。

    2. 完了です！

---

???note "「作業中」　アニメ <small>(クリックして開く)</small>"
    ## アニメ

    **必要なもの**

    - [PC版Yomitan](setupYomitanOnPC.md) のセットアップが完了していること

    **アニメのセットアップ**

    1. [PC版アニメセットアップ](setupAnimeOnPC.md) の手順をそのまま実行してください。
        - Chrome / Edge 用の説明は無視してください。

    2. 完了です！

---

思ったより「Lazy Guide」ではありませんでしたね？これでLinux環境のセットアップは完了です！

続いてサブガイドも見てみましょう。

[サブガイドへ進む](subGuide.md){ .md-button .md-button }