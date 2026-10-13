# An Open Door — stewardship page

A single web page for the 2026 stewardship campaign of the Parish of St Barnabas and St Paul
with St Thomas the Martyr, Oxford. One HTML file, no build step, no dependencies.

```
index.html             the page
leaflet.pdf            the printed leaflet, offered as a download
logo-st-barnabas.png   parish logo, lifted from the leaflet
logo-st-thomas.png     parish logo, lifted from the leaflet
photo-nave.jpg         the photograph, lifted from the leaflet
GOOGLE-FORM.md         what to put in the Google Form
README.md              this file
```

---

## Do this first

**1. Make the Google Form.** Follow `GOOGLE-FORM.md`. It takes about fifteen minutes.

**2. Connect it.** Open `index.html`, scroll to the bottom, and find this line:

```js
const FORM_URL = "PASTE_YOUR_GOOGLE_FORM_LINK_HERE";
```

Paste your form link between the quotation marks and save. Until you do, the page shows a
yellow notice where the form belongs — visible to anyone looking at the site, so do this
before you tell people the address.

**3. Check it.** Double-click `index.html` to open it in a browser. The form should appear
embedded in the page and the gold button should open it in a new tab.

---

## Publishing it on GitHub Pages

1. On [github.com](https://github.com), click **New repository**. Name it something like
   `open-door`. Set it to **Public** — GitHub Pages will not serve a private repo on a free
   account. Tick nothing else, and click **Create**.
2. On the new repository page, click **uploading an existing file**.
3. Drag in all four files from this folder. Scroll down, click **Commit changes**.
4. Go to **Settings → Pages**. Under *Build and deployment*, set **Source** to
   `Deploy from a branch`, **Branch** to `main`, folder `/ (root)`. Click **Save**.
5. Wait two or three minutes, then reload that Settings → Pages screen. Your address appears
   at the top, in the form:

   ```
   https://YOUR-USERNAME.github.io/open-door/
   ```

That address is what goes on the pew sheet, in the newsletter, and in the email to the
congregation.

### Changing something later

Click the file in GitHub, click the pencil icon, edit, then **Commit changes**. The live site
updates within a minute or two. Everything on the page — the figures, the dates, the bank
details, the wording — is plain text in `index.html` and safe to edit.

### A tidier address

If the parish already owns a domain, you can point something like `giving.sbarnabas.org.uk` at
this page: add a `CNAME` file in the repository containing that one line, then add a CNAME
record with your domain provider pointing to `YOUR-USERNAME.github.io`. Your website host can
do this in a few minutes if it is unfamiliar territory.

The simplest alternative, if you would rather not: ask whoever maintains sbarnabas.org.uk to
add a menu link called **Giving** that points at the GitHub Pages address.

---

## Fonts

The page asks for **Gill Sans** for body text and **Recoleta** for the display headings, exactly
as in the leaflet. Anyone whose device has them will see them — which covers most Macs and
iPhones for Gill Sans, and Windows machines with Microsoft Office installed.

Both are commercial fonts, and the desktop licences used to make the leaflet do **not** permit
serving them from a website. So they are not embedded here, and no font files for them sit in
this repository. Instead the page falls back to two free, openly licensed near-matches:

- **Cabin** in place of Gill Sans. Cabin was drawn in the humanist tradition of Edward Johnston
  and Eric Gill, so the proportions and feel are close.
- **Fraunces** in place of Recoleta. A warm serif with the same soft terminals and slight
  quirkiness. Most visitors will see this one, since almost nobody has Recoleta installed.

If the parish ever wants the exact fonts for every visitor, that means buying webfont licences
from Monotype (Gill Sans) and Latinotype (Recoleta). It is then a drop-in swap — add the font
files and an `@font-face` block, and the existing CSS picks them up with no other change.

### Self-hosting the free fonts

The two fallback fonts load from Google's servers, which means visitors' browsers make a
request to Google. If you would rather they did not, download both families from
[fonts.google.com](https://fonts.google.com), put the `.woff2` files in this folder, delete the
three `<link>` tags near the top of `index.html`, and add `@font-face` rules in their place.
It is a twenty-minute job and makes the page entirely self-contained.

## Logos

`logo-st-barnabas.png` and `logo-st-thomas.png` were extracted from your leaflet PDF at full
resolution with transparent backgrounds, so they sit cleanly on the cream background and will
stay sharp on a retina screen. They are centred side by side, with a thin divider between them,
and they stack one above the other on a narrow phone. Each links to the church's own website.

If you have the original vector artwork (`.svg`, `.ai` or `.eps`), an SVG version would be
sharper still and a fraction of the file size — drop it in and change the `src` and the file
extension.

## The photograph

`photo-nave.jpg` is the picture of the nave at Mass from page 1 of your leaflet, saved at full
resolution for the web.

**To use a different picture:** put your own `.jpg` in this folder, then change one word in
`index.html` — find `photo-nave.jpg` and replace it with your filename. Change the `alt="..."`
wording too, which is what a blind visitor's screen reader reads aloud.

Two things that catch people out when a picture does not appear:

- **Capital letters matter.** `Photo.JPG` and `photo.jpg` are different files as far as the web
  server is concerned, even though your Mac treats them as the same. Whatever you type in
  `index.html` must match the filename exactly, including the extension.
- **The file has to be in the repository.** Dragging it into the GitHub upload box is not
  enough on its own — you must then scroll down and click **Commit changes**.

The picture is cropped to a 4:3 letterbox on a computer and a taller shape on a phone, so it
works either way round. Two numbers in `index.html` control that, both commented:

- `padding-top:75%` — the shape of the frame. Larger means taller.
- `object-position:center 72%` — which part of the picture shows through. Larger means lower
  down the image.

## Notes on what is in the page

- **Everything is in one file.** The CSS is inline, there are no fonts or scripts loaded from
  elsewhere, and nothing tracks anyone. The page works offline and will still work in ten
  years.
- **The bank details are public**, exactly as they are in the printed leaflet. The page carries
  a short warning telling people to telephone the Parish Office if they are ever asked to pay
  into a different account. Church payment-redirection fraud is common enough to be worth that
  line; please leave it in.
- **It is designed for a phone**, because most people will arrive by tapping a link or scanning
  a code in church rather than sitting at a desk.
- **It prints sensibly** if anyone wants a paper copy — the form and buttons drop away.

## Worth doing before launch

- Add a **photograph**. The page is handsome but entirely typographic. A picture of the open
  west door or the new organ case, dropped in below the first paragraph, would lift it
  considerably. Any `.jpg` in this folder can be shown with
  `<img src="yourphoto.jpg" alt="The west door of St Barnabas, open" style="width:100%;border-radius:3px;margin:20px 0">`.
- Get a **QR code** made for the address and put it on the pew sheet and the poster. Plenty of
  free generators will do this once you know the URL.
- Ask one person who is not confident with computers to try it on their phone and report back.
  That test is worth more than any amount of checking by people who already know how it works.
