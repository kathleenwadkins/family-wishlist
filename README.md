# Our Family Wish List

A shareable Christmas wish list for Kathleen, Todd, James, Emma and Bennett.
Family taps "I'm getting this one!" and everyone else sees it wrapped up, so nobody doubles up.

- `index.html` and `config.js`: the page (hosted on GitHub Pages)
- `apps-script/Code.gs`: the Google Sheet helper that saves the list and claims and reads product links

## One-time setup (about 5 minutes)

### 1. Make the Google Sheet helper
1. Go to sheets.google.com and create a blank sheet. Name it "Family Wish List".
2. In the sheet, click **Extensions > Apps Script**.
3. Delete what's in the editor, paste in everything from `apps-script/Code.gs`, and click Save.
4. Near the top, change `'CHANGE-ME'` to a passcode only you will know. Save again.
5. Pick **setup** in the function menu at the top and click **Run**. Approve the permissions Google asks for. It's your own script, so click "Advanced" then "Go to ... (unsafe)" if Google warns you.
6. Click **Deploy > New deployment**. Click the gear and pick **Web app**.
   - Execute as: **Me**
   - Who has access: **Anyone**
7. Click **Deploy** and copy the **Web app URL** (it ends in `/exec`).

### 2. Connect the page
Open `config.js` and paste that URL between the quotes.

### 3. Put it on GitHub Pages
1. On github.com, create a new public repository named `family-wishlist`.
2. Click **Add file > Upload files** and upload `index.html`, `config.js` and this README. (Don't upload the `apps-script` folder. It's already in your Sheet.)
3. Go to **Settings > Pages**, set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**, and save.
4. In a minute or two it's live at `https://kathleenwadkins.github.io/family-wishlist/`.

## Using it
- **Add a gift:** scroll to the bottom and tap **Kathleen's tools**, then enter your passcode. Paste a product link and tap **Read link**. Check the name and price, pick who it's for, and tap **Add to the list**. Some stores (Amazon often) block link reading. If so, type the name and price yourself.
- **Edit or remove:** while unlocked, every gift shows Edit and Remove buttons.
- **Share:** send family the link. Add `#todd` (or `#emma`, etc.) to the end to open straight to one person's list.
- **Claims:** anyone can mark a gift, and anyone can free it back up with "Not getting it after all?". Everything is saved in the Sheet, so you can also see who's getting what there.

## If you change Code.gs later
Use **Deploy > Manage deployments > Edit (pencil) > Version: New version > Deploy**, so the same URL keeps working.
