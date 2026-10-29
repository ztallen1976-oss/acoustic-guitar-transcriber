# Fingerstyle Transcriber

Turns a recording of solo fingerstyle acoustic guitar into tab with rhythm,
with playback, a waveform and downloads for MuseScore and Guitar Pro.
All the work happens in the visitor's web browser, so recordings are never uploaded.

There are two parts below:
- **Part 1: Putting it online with GitHub Pages** (one time, about 10 minutes)
- **Part 2: Using the app** (every time)

---------------------------------------------------------------------------

## Part 1: Putting it online with GitHub Pages

You'll end up with your own web address like
`https://YOUR-NAME.github.io/guitar-transcriber/`.
It's a separate site, so it won't touch your 8th grade website.

### Step 1. Unzip this package

1. Find `guitar-transcriber.zip` in your Downloads folder.
2. Right-click it and choose **Extract All…**, then click **Extract**.
3. A folder called `guitar-transcriber` opens. Inside it you should see:
   - `index.html`
   - `README.md` (this file)
   - `START HERE.txt` (a copy of this file)
   - a folder called `model`
   - a folder called `sample`

   Leave this window open. You'll drag these files in Step 3.

### Step 2. Make a new repository (a project folder on GitHub)

1. Go to **github.com** and sign in. This is the same account you use for your other site.
2. In the top-right corner, click the **+** button, then **New repository**.
3. In **Repository name**, type: `guitar-transcriber`
   (lowercase, with the dash. This becomes part of the web address.)
4. Make sure **Public** is selected. GitHub Pages on a free account needs Public.
5. Leave everything else as it is. Don't tick "Add a README file".
6. Click the green **Create repository** button at the bottom.

### Step 3. Upload the files

1. On the page that appears, find the line that says
   *"…or create a new file or **uploading an existing file**"* and click
   **uploading an existing file**.
2. Go back to the open `guitar-transcriber` folder from Step 1.
3. Press **Ctrl + A** to select everything **inside** the folder (the files and both folders).
4. Drag them onto the GitHub page, onto the area that says "Drag files here".

   > Important: drag the things **inside** the folder, not the
   > `guitar-transcriber` folder itself. `index.html` must sit at the top level,
   > not inside another folder, or the site will show a 404 error.

5. Wait until every file shows in the list (the bigger files take a few seconds).
   You should see `index.html`, `README.md`, `START HERE.txt`, and the `model` and `sample` files.
6. Scroll down and click the green **Commit changes** button.

### Step 4. Turn on GitHub Pages

1. At the top of your repository page, click **Settings** (the gear icon, far right).
2. In the left-hand menu, click **Pages**.
3. Under **Build and deployment** → **Source**, choose **Deploy from a branch**.
4. Under **Branch**, choose **main**, leave the folder as **/ (root)**, and click **Save**.

### Step 5. Open your site

1. Wait 1–3 minutes, then refresh the Settings → Pages screen.
2. A box appears at the top saying **"Your site is live at …"** with your address.
   Click **Visit site**.
3. Bookmark it. That's your transcriber. You can share the address with anyone.

### If something goes wrong

| What you see | What to do |
|---|---|
| **404 "There isn't a GitHub Pages site here"** | Wait a few more minutes and refresh. If it stays, check that `index.html` is at the top level of the repository and not inside a folder. If it is inside a folder, delete the repository (Settings → bottom of the page → Delete) and do Steps 2–4 again. |
| The page loads but says the note detector couldn't load | You need an internet connection; the page downloads its listening engine from cdn.jsdelivr.net. Try again on a different network, or check that a school or work filter isn't blocking that site. |
| No "Pages" option, or it says to upgrade | Make sure the repository is **Public** (Settings → General → scroll to "Danger Zone" → Change visibility). |
| The example song isn't showing | Check that the `sample` folder uploaded with all three files inside it. |

### Changing it later

- **To remove the example song** so the app opens empty: in the repository, open the `sample`
  folder, click each file, click the **…** menu (or the trash-can icon) and choose **Delete file**,
  then **Commit changes**.
- **To install an updated version**: open the repository, click **Add file → Upload files**,
  drag in the new files, and click **Commit changes**. Files with the same name are replaced.

---------------------------------------------------------------------------

## Part 2: Using the app

The same guide is inside the app: click **"How to use this"** at the top of the page.

1. **Drop in a recording.** Drag an MP3, WAV, M4A or FLAC onto the dashed box, or click it to
   pick a file. Solo guitar works best: no singing, little background noise, trimmed to just the
   song. It takes roughly 10 seconds for every minute of music.
2. **Tell it what you know** (optional). Type a title, and in "Anything we should know?" write
   things like `capo 2, DADGAD, 6/8, intro played freely`. Click **Apply requests**.
3. **Give it your rough tab** (optional). Paste any tab you already have, even if it's messy or
   only part of the song. It uses your strings and frets wherever they match the recording.
4. **Check it by ear.** Press ▶. Switch between **Recording**, **Tab** and **Both**. Click the
   waveform or the tab to jump around. Try **Speed 50%** for fast parts. Space bar = play/pause.
5. **Fix what sounds off** using the settings on the left. The tab redraws instantly.
   - Count feels doubled or halved → **½×** / **2×** next to Tempo
   - Lots of wrong notes → the tuning or capo is wrong; set them
   - Stray notes → slide "How many notes to keep" toward **Fewer**
   - Missing quiet notes → slide it toward **More**
   - x marks where there are no slaps → untick **Percussive hits**
   - Player speeds up and slows down → Timing: **Free timing (rubato)**
6. **Download.** The `.musicxml` file opens in **MuseScore** (free: musescore.org) or
   **Guitar Pro**, which show standard notation and tab together, let you fix any note, and print.
   The `.txt` file is plain text tab.

What to expect: a strong first draft that saves most of the grunt work. You'll still tidy some
note lengths and fingerings by ear, especially in fast passages, percussive playing and harp
harmonics.

### What's in this folder

- `index.html`: the whole app
- `model/`: the note-listening model (Spotify's open-source Basic Pitch, Apache 2.0 licence)
- `sample/`: the example recording that loads when the page opens

### Only on the Claude-hosted copy

"Read a photo of tab", and Claude reading your requests in your own words, only work in the copy
hosted on Claude. On GitHub, the request box uses a built-in reader that understands tuning, capo,
time signature, tempo, free timing, triplets, harmonics, slaps, and one or two voices.
