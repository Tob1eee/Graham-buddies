# Graham Buddies — Mango Graham Website (HTML + CSS + PyScript)

Event-Driven Programming final project. HTML = structure, CSS = design, **PyScript (Python) = all interactivity**.

**Graham Buddies** is a dessert business specializing in Mango Graham. Tagline: *Your Sweetest Buddy.*

## Run it
PyScript loads `main.py` with `fetch`, so the site must be opened through a web server. Double-clicking `index.html` will **not** work (the product menu will stay empty).

**Option 1: VS Code Live Server.** Open the project folder in VS Code, open `index.html`, and click **Go Live**.

**Option 2: Python server.**
```bash
python -m http.server 8000
# then open http://localhost:8000
```

An internet connection is needed for the PyScript CDN (release 2024.11.1) and Google Fonts. The first load takes a few seconds while Python starts in the browser.

## Files
| File | Purpose |
|---|---|
| `index.html` | Page structure and PyScript setup |
| `styles.css` | Palette, layout, responsive design, reduced-motion |
| `main.py` | Python data, helper functions and event handlers |
| `logo.jpg` | Official logo, used unchanged |
| `Header.jpg` | Hero photo |
| `MangoGrahamCup.jpg`, `LargeMangoGraham.jpg`, `FamilySizeMangoGraham.jpg`, `MangoGrahamOver.jpg` | Product photos |
| `Advertisement.mp4`, `poster.jpg` | 30-second promotional video and its preview image |

## Event-driven map (all in `main.py`)
| Event | Handler | Result |
|---|---|---|
| click filter chip | `on_filter_click` | catalog re-filtered |
| input on quantity | `on_product_quantity_input` | live price preview / error |
| click Add to Cart | `on_add_to_cart` | cart count + totals update, toast |
| click +, −, Remove | `on_cart_click` | quantities/removal, totals update |
| change cart quantity | `on_cart_quantity_change` | validated and recalculated |
| change Delivery/Pickup | `on_mode_change` | address field + delivery fee |
| submit order / contact form | `on_order_submit`, `on_contact_submit` | validation errors or demo confirmation |
| input message | `on_message_input` | live character counter |

## Customize
- Prices, names, descriptions: `PRODUCTS` list in `main.py`. Delivery fee: `DELIVERY_FEE`.
- Promo video: replace `Advertisement.mp4` (and `poster.jpg`, the preview image) with your own files, keeping the same names.
- Product photos: put the images next to `index.html` and set each product's `"img"` in `PRODUCTS` (`main.py`).
- Business contact details, social links and reviews are placeholders in `index.html`.

## Demo notes
Checkout and contact forms are local demos: nothing is sent and no payment is processed. Testimonials are sample content.

## Team contributions

| Member | Role | Main contribution | Files |
|---|---|---|---|
| **Diez** | Repository and documentation | README, project file preparation, whole-site testing and bug reports | `README.md`, repository |
| **Dumulong** | Promo video and media | Repository creation and collaborator invites, promotional video, logo and product photo organization, video section, presentation recording coordination | `Advertisement.mp4`, `poster.jpg`, image files, video section in `index.html` |
| **Tabasa** | HTML | Page structure, section IDs used by the Python code, navigation links, form labels, image alt text, website demonstration in the video | `index.html` |
| **Sabalande** | CSS | Color palette variables, layout and product cards, hover and focus effects, responsive rules, reduced-motion support | `styles.css` |
| **Rubio** | PyScript | Product data, cart calculations, validation, and the event handlers for clicks, typing, changes and form submissions, with explanatory comments | `main.py` |

### Details
- **Diez:** wrote this README (setup steps, feature list, event-handler map and contributions), prepared the project files, and tested the full website, reporting problems to the member who owned that part. *Note:* the first file upload was made while signed in to the repository owner's account, so those commits appear under Dumulong's account, but that work was done by Diez. His other commits are under his own account.
- **Dumulong:** created and published the public repository and invited the group as collaborators. Produced the 30-second promotional advertisement and its preview image, organized the logo and product photos, added the video section, and coordinated the recording and editing of the presentation video.
- **Tabasa:** built the HTML structure: sections (hero, video, menu, about, features, reviews, contact), the IDs that `main.py` looks for, navigation, labels and alt text. Demonstrated the website in the presentation.
- **Sabalande:** designed the look in `styles.css`: the cream, mango yellow, golden honey, graham brown and caramel palette as CSS variables, rounded cards, hover effects, focus outlines, and the responsive layout for phones and tablets.
- **Rubio:** wrote the Python logic: the `PRODUCTS` list, the `cart` dictionary, helper functions (`peso`, `parse_quantity`, `cart_subtotal`, `delivery_fee`, `validate_contact`), the render functions, and every `@when` event handler listed above.

Each member's commits are visible in the repository's commit history. The presentation video was recorded as separate clips by each member and then edited together, with every member appearing and speaking.
