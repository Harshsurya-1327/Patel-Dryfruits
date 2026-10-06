# New pages — Gifting, Custom Gift Order, Bulk & Corporate Gifting

Built inside the existing Minimog 5.9.0 theme architecture. No framework changes.
Only 9 files were added — nothing existing was modified or removed.

## New files
- `sections/gift-collection-tabs.liquid` (+ `assets/gift-collection-tabs.css`, `.js`)
  Tabbed product grid ("All Boxes / Festive Hampers / ..."). Each tab is a block
  pointing at a real Shopify collection.
- `sections/custom-order-form.liquid` (+ `assets/gift-forms.css`)
  Cream header banner + image + form, for the Custom Gift Order page.
- `sections/bulk-enquiry-form.liquid` (shares `assets/gift-forms.css`)
  Cream header banner + image + form, for the Bulk & Corporate Gifting page.
- `templates/page.gifting.json`
- `templates/page.custom-gift-order.json`
- `templates/page.bulk-corporate-gifting.json`

## Everything else reuses existing Minimog sections (no new code):
- Hero banner → `slider.liquid`
- "Two ways to gift" cards → `custom-content.liquid` (layout_3 blocks)
- USP icon bar → `icon-box.liquid`
- "Not sure what to pick?" WhatsApp banner → `promotion-banner.liquid`
- "Gift by occasion" grid → `collection-list.liquid`
- FAQ accordion → `collapsible-tabs.liquid`
- "Follow Our Instagram" grid → `gallery.liquid`
- Header / announcement bar / footer → global sections, untouched

## To set up before launch (all done in the theme editor, no code needed)
1. Create the pages in Shopify Admin → Online Store → Pages:
   - "Gifting" → assign template `page.gifting`
   - "Custom Gift Order" → assign template `page.custom-gift-order`
   - "Bulk & Corporate Gifting" → assign template `page.bulk-corporate-gifting`
2. In the Gifting page's **Gift collection tabs** section, assign a real
   collection to each tab block (All Boxes / Festive Hampers / Premium Trays /
   Mini Favours / Corporate Sets).
3. In **Gift by occasion**, assign a collection + image to each of the 5 blocks.
4. Upload hero, banner, USP icons, and form side-images via the theme editor
   image pickers (all currently blank placeholders).
5. Add the 3 pages to the main menu / footer menu as needed.
6. Confirm the WhatsApp number (currently `919081091710`, from the Figma) and
   swap in the real one if different.

## Forms
Both forms use Shopify's native `{% form 'contact' %}` — no app required.
Submissions email the store's customer notification address with all field
labels included (e.g. "Occasion", "Budget per Box", "No. of Units"). Each form
also submits a hidden `Form Type` field so the two enquiry types are easy to
tell apart in the inbox.
