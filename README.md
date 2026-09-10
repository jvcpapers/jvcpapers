# jvcpapers.com — JVC International LLC

Five plain HTML pages with a Roxcel-style navigation: a slim contact bar on top, logo on the left, menu with dropdown submenus, and an enquiry button on the right. No framework, no build step, nothing to keep updated.

## Pages

| File | What's on it |
|---|---|
| `index.html` | Home. Hero, current buying interest panel, what we buy and what we sell, grade cards, company background. |
| `about.html` | Our story, our experience (two sides: selling to us / buying from us), how we work in five steps. |
| `products.html` | DSOCC #12, Grade #11 DLK, other OCC grades, each with the quality we buy on. |
| `markets.html` | Where we sell (five South Indian states), where we buy (supply regions), shipment and terms. |
| `contact.html` | Enquiry form and direct contact details. |
| `assets/` | Logo in three sizes with a transparent background, plus the favicon. |

The dropdown menu items jump straight to sections: About us goes to `about.html#story`, `#experience`, `#how-we-work`; Products goes to `products.html#dsocc-12`, `#grade-11`, `#other-occ`.

## Publishing on Cloudflare

1. Cloudflare dashboard → **Workers & Pages** → **Create** → **Pages** → **Upload assets**.
2. Name the project `jvcpapers`, drag in this whole folder, deploy.
3. Open the project → **Custom domains** → **Set up a domain** → `jvcpapers.com`. Add `www.jvcpapers.com` too if you want both.
4. DNS is added automatically because the domain is already in the account. Live in a minute or two.

To change anything later, edit the file and upload the folder again.

## Email

`ops@jvcpapers.com` needs a mailbox before you send this out. Cloudflare Email Routing (free, under **Email** in the dashboard) forwards it to an inbox you already have, which is enough to start. Google Workspace or Zoho Mail is the step up when you want to send from that address too.

## Things to change before you launch

Search the files for `EDIT`. There are four:

1. **Grade #11 quality** in `products.html`. Your brief left this blank, so those four points are standard trade wording. Replace them with your own specification.
2. **Supply regions** in `markets.html`. Europe, North America, Middle East, Southeast Asia and Australia are placeholders — trim to where you actually buy.
3. **Phone and address** in `contact.html`. The block is written and commented out; delete the `<!--` and `-->` and fill it in.
4. **Phone and address** in the footer of every page, same thing.

Also worth a look:
- The hero panel on the home page says "Current buying interest". Update it whenever your requirement changes — it is the first thing a supplier reads.
- The five states on `markets.html` and in the hero panel. Trim or extend to match where you actually place material.
- "40+ years" appears on the home page and on `about.html`.

## A note on editing

The styles sit in a `<style>` block at the top of each page, identical on all five. If you change a colour or a size, copy the whole block to the other four pages so they stay in step. Same for the header and footer markup.

## The enquiry form

The form opens the visitor's email app with everything filled in, addressed to `ops@jvcpapers.com`. It works everywhere and costs nothing, but it does rely on the visitor having a mail app set up.

To have submissions arrive as email regardless, sign up at Formspree or Web3Forms, then in `contact.html` replace `<form id="enquiry">` with `<form action="https://formspree.io/f/YOUR_ID" method="POST">` and delete the last `<script>` block on that page. Nothing else changes.
