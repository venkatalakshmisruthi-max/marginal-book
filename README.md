# marginal-book
# Marginalia Books – Website & Code Documentation
web page url:bright-frangipane-739c19.netlify.app/


A responsive online bookstore built with **HTML5 and CSS3 only** (no JavaScript, no frameworks).

---

## 1. Project Overview

| Item | Detail |
|---|---|
| Site name | Marginalia Books |
| Tagline | "Find Your Next Favorite Book." |
| Type | Single-page marketing and shop demo |
| Files | `index.html`, `style.css` |
| Languages | HTML5, CSS3 |
| JavaScript | None (mobile menu uses the CSS checkbox technique) |
| Frameworks | None (no Bootstrap, Tailwind or React) |
| Fonts | Fraunces (headings), Karla (body), loaded from Google Fonts |
| Page title | Marginalia Books – Find Your Next Favorite Book |
| Language attribute | `lang="en"` |

### Folder structure

```
/project
├── index.html
└── style.css
```

### How to run

1. Put both files in the same folder.
2. Open `index.html` in any modern browser.
3. An internet connection is needed for fonts and images (see section 8).

---

## 2. Design System

### Color palette (CSS variables in `:root`)

| Variable | Hex | Used for |
|---|---|---|
| `--cream` | `#FBF3E4` | Page background |
| `--beige` | `#EBDDC2` | Alternate sections, borders |
| `--burgundy` | `#6B1F2E` | Primary buttons, headings, offers background |
| `--burgundy-d` | `#4E1521` | Footer, dark text on orange |
| `--brown` | `#2B1A14` | Body text, best sellers and cart background |
| `--orange` | `#C98A3E` | Accents, stars, badges, newsletter background |
| `--muted` | `#6F5A4D` | Secondary text |

### Typography

| Role | Font | Notes |
|---|---|---|
| Headings, logo, prices | Fraunces (serif) | Weights 500 and 700, plus italic |
| Body, buttons, forms | Karla (sans-serif) | Weights 400, 500 and 700 |
| Heading sizes | `clamp()` | Scale fluidly between mobile and desktop |

### Other tokens

- `--shadow`: `0 10px 28px rgba(43,26,20,.14)`, used for card hover lift.
- `--ease`: `.3s ease`, the shared transition timing.
- Container: `.wrap` is `min(1180px, 92%)`, centered.

---

## 3. HTML Structure (in page order)

The page uses semantic elements: `header`, `nav`, `main`, `section`, `article`, `aside`, `blockquote`, `address`, `figure`, `footer`.

| # | Section | Element and ID | Purpose |
|---|---|---|---|
| 1 | Navigation | `<header class="site-header">` | Sticky nav bar |
| 2 | Hero | `<section id="home">` | Headline, CTAs, cover stack |
| 3 | Categories | `<section id="categories">` | 10 category cards |
| 4 | Featured Books | `<section id="featured">` | 4 product cards |
| 5 | Best Sellers | `<section id="bestsellers">` | 3 ranked horizontal cards (dark theme) |
| 6 | Authors | `<section id="authors">` | 4 author profiles |
| 7 | Offers | `<section id="offers">` | Sale banner and deal boxes |
| 8 | Shopping | `<section id="shop">` with `<aside id="cart">` | Product rows and cart summary |
| 9 | Why Choose Us | `<section>` (no ID) | 6 benefits |
| 10 | Reviews | `<section>` (no ID) | 3 testimonials |
| 11 | Newsletter | `<section class="newsletter">` | Email signup form |
| 12 | Contact | `<section id="contact">` | Details and contact form |
| 13 | Footer | `<footer class="footer">` | Links, contact, copyright |

### Navigation links and targets

| Link text | Target |
|---|---|
| Home | `#home` |
| Categories | `#categories` |
| Featured Books | `#featured` |
| Authors | `#authors` |
| Offers | `#offers` |
| Contact | `#contact` |
| Shopping bag icon | `#cart` |
| Sign in button | `#contact` (placeholder) |

### Navigation components

- **Logo:** a burgundy "M" mark plus the name "Marginalia Books".
- **Search bar:** `<input type="search">` inside a `<form action="#">`. It is design only and does not search.
- **Bag icon:** the 🛍 emoji with an orange counter showing **3**.
- **Mobile menu:** a hidden `<input type="checkbox" id="menu-toggle">` and a `<label class="burger">`. The CSS rule `.menu-toggle:checked ~ .nav-links` shows the menu.

---

## 4. Website Content Details

### 4.1 Hero

- Kicker: "Independent bookshop since 1987"
- H1: **Find Your Next Favorite Book.**
- Tagline: "Somewhere on our shelves is the story you'll still be thinking about next winter."
- Description: reader-run shop, 40,000+ titles, staff notes, free gift wrapping.
- Buttons: **Explore Books** (`#categories`), **Shop Now** (`#shop`).
- Highlighted bestseller: *Atomic Habits* by James Clear, $16.99, with a "This week's #1" badge.
- Decorative covers: *Dune* and *The Hobbit*, tilted behind the main cover.
- Background: library photo with a burgundy and brown gradient overlay.

### 4.2 Categories (10)

| Category | Description | Icon | Card color |
|---|---|---|---|
| Fiction | Novels that stay with you long after the last page. | 📖 | `#6B1F2E` |
| Mystery & Thriller | Locked rooms, unreliable narrators, late nights. | 🔍 | `#2B1A14` |
| Romance | Slow burns, second chances and happy endings. | 💌 | `#A8485A` |
| Science Fiction | Futures worth worrying about and worth wanting. | 🚀 | `#35506B` |
| Fantasy | Maps, magic systems and long, rich worlds. | 🐉 | `#4A5A2E` |
| Self-Help | Practical ideas for habits, focus and change. | 🌱 | `#B9772A` |
| Biography | Real lives, told by the people who lived them. | 🎙 | `#5A3A2A` |
| Technology | Code, design and the systems behind our screens. | 💻 | `#2F4A4A` |
| Academic Books | Textbooks and reference for every semester. | 🎓 | `#7A3B1D` |
| Children's Books | Picture books and first chapters for small readers. | 🧸 | `#C98A3E` |

Each card has an "Explore Category" label and links to `#featured`. The card color is set with an inline CSS variable, `style="--c:#hex"`.

### 4.3 Featured Books

| Title | Author | Original | Sale | Discount | Rating |
|---|---|---|---|---|---|
| The Silent Patient | Alex Michaelides | $17.99 | $14.39 | 20% OFF | 4.1 |
| Pride and Prejudice | Jane Austen | $9.99 | $8.49 | 15% OFF | 4.8 |
| Clean Code | Robert C. Martin | $47.99 | $35.99 | 25% OFF | 4.4 |
| The Alchemist | Paulo Coelho | $16.99 | $11.89 | 30% OFF | 4.2 |

Each card has a cover, discount badge, star rating, strikethrough original price, **Add to Cart** button (`#cart`) and **View Details** link.

### 4.4 Best Sellers

| Rank | Title | Author | Price | Rating | Blurb |
|---|---|---|---|---|---|
| #1 | Sapiens | Yuval Noah Harari | $22.99 | 4.6 | A sweeping history of our species, from campfire stories to global economies. |
| #2 | Educated | Tara Westover | $18.00 | 4.7 | A memoir of growing up off the grid and fighting her way into a classroom. |
| #3 | Where the Crawdads Sing | Delia Owens | $17.00 | 4.5 | A marsh-girl, a murder and a coastal town that never quite let her in. |

### 4.5 Author Spotlight (fictional sample profiles)

| Author | Bio | Known for |
|---|---|---|
| Maya Okafor | Lagos-born novelist writing about family, memory and migration. | *The Salt Road*, *Harbour Light* |
| Daniel Reyes | Former detective turned thriller writer with a taste for cold cases. | *Nine Quiet Doors*, *The Last Ledger* |
| Priya Raman | Fantasy author building monsoon-soaked worlds from Tamil folklore. | *The Ember Court*, *Rain Kings* |
| Tom Lindqvist | Software engineer explaining complex systems in plain language. | *Small Systems*, *Think in Layers* |

Each profile has an "Explore Books" link to `#featured`. Photos come from pravatar.cc placeholders.

### 4.6 Special Offers

| Offer | Detail |
|---|---|
| Winter Reading Sale | Up to 40% off, until 31 December, with a **Shop the Sale** button (`#shop`) |
| Buy 2, Get 1 Free | On all paperbacks; the cheapest book is free |
| Students save 15% | Valid student ID in store or at checkout |
| 48-hour flash deal | Children's picture books, 25% off, ends Friday midnight |

### 4.7 Shopping Section (visual demo only)

| Book | Author | Original | Sale | Discount | Qty shown |
|---|---|---|---|---|---|
| Gone Girl | Gillian Flynn | $16.00 | $12.80 | 20% OFF | 1 |
| Becoming | Michelle Obama | $32.50 | $24.38 | 25% OFF | 2 |

**Cart summary (static sample figures):**

| Line | Amount |
|---|---|
| Gone Girl × 1 | $12.80 |
| Becoming × 2 | $48.76 |
| Student discount | −$9.24 |
| Shipping | Free |
| **Total** | **$52.32** |

The quantity controls (−, +) and the Checkout button are not functional.

### 4.8 Why Choose Us (6)

| Icon | Title | Text |
|---|---|---|
| 📚 | Wide collection | 40,000+ titles across every genre. |
| 💰 | Affordable prices | Member pricing and weekly deals. |
| ✨ | Quality editions | Sewn bindings and honest paper. |
| 🔒 | Secure shopping | Encrypted, trusted payments. |
| 🚚 | Fast delivery | Dispatched within 24 hours. |
| 🧭 | Easy discovery | Staff picks and "if you liked" lists. |

### 4.9 Customer Reviews

| Customer | Rating | Book bought | Review |
|---|---|---|---|
| Anita Sharma | 5 stars | The Silent Patient | Packed like a gift and arrived in two days; the staff note led her to a new favorite author. |
| Rahul Verma | 5 stars | Clean Code | Best textbook prices, and the student discount applied with no hassle. |
| Sofia Marino | 4 stars | The Alchemist | Lovely editions, easy site, kids fight over the picture-book box. |

### 4.10 Newsletter

- Headline: "Get one great book recommendation every Friday"
- Description: "No spam. Just new arrivals, author events and subscriber-only discounts."
- Form: email input (`type="email"`, `required`) and a **Subscribe** button.

### 4.11 Contact (placeholder details)

| Field | Value |
|---|---|
| Address | 24 Quill Lane, Old Town, Vijayawada 520001 |
| Email | hello@marginaliabooks.example |
| Phone | +91 00000 00000 |
| Hours | Mon–Sat 10:00–20:00 · Sun 11:00–17:00 |
| Social links | Instagram, Facebook, X, YouTube (`href="#"` placeholders) |

**Contact form fields:** Name (`required`), Email (`type="email"`, `required`), Message (`textarea`, `required`, `minlength="10"`), and a **Send message** button.

### 4.12 Footer

- Logo and a one-line description: "An independent bookshop for curious readers, since 1987."
- **Quick links:** Home, Featured Books, Authors, Offers.
- **Categories:** Fiction, Fantasy, Biography, Children's Books.
- **Contact:** address, email, Instagram and Facebook.
- Copyright: © 2026 Marginalia Books. All rights reserved.

---

## 5. CSS Architecture (`style.css`)

The file is organized into commented blocks, in this order:

1. Tokens (`:root` variables)
2. Reset and base styles
3. Buttons and badges
4. Navigation
5. Hero
6. Generic section styles
7. Categories
8. Book cards
9. Best sellers
10. Authors
11. Offers
12. Shop and cart
13. Why Us
14. Reviews
15. Newsletter
16. Contact
17. Footer
18. Responsive media queries

### Reusable classes

| Class | Function |
|---|---|
| `.wrap` | Centered container |
| `.section`, `.section.alt`, `.dark` | Section spacing and background variants |
| `.section-title`, `.section-sub` | Section headings |
| `.grid` | Base grid with a gap |
| `.btn`, `.btn-small`, `.btn-ghost` | Button styles |
| `.badge`, `.badge-red`, `.badge-orange` | Pill badges |
| `.link` | Underlined text link |
| `.book`, `.cover` | Product card and its image box |
| `.rating`, `.price`, `.author` | Card text elements |
| `.sr` | Visually hidden label for accessibility |

### Layout techniques

| Area | Technique |
|---|---|
| Category grid | `repeat(auto-fill, minmax(210px, 1fr))` |
| Featured grid | `repeat(auto-fill, minmax(230px, 1fr))` |
| Best sellers | `repeat(auto-fit, minmax(320px, 1fr))`, with image and text in a 2-column grid |
| Authors, why, reviews | `auto-fit` with `minmax()` |
| Hero | 2-column grid, with absolutely positioned covers in the right column |
| Navigation | Flexbox, sticky with `position: sticky; top: 0` |
| Cart | `position: sticky` on desktop |
| Smooth scrolling | `html { scroll-behavior: smooth }` with `scroll-padding-top: 84px` for the sticky header |

### Hover and visual effects

| Element | Effect |
|---|---|
| Category cards | Lift, expanding circle, icon scale and tilt |
| Book cards | Lift of 8px, shadow, cover image zoom (1.07×) |
| Hero covers | Straighten and scale on hover |
| Best-seller cards | Slide right 6px, background lightens |
| Author cards | Lift and shadow (arched top via `border-radius`) |
| Offer boxes | Dashed border, background tint |
| Why icons | Circle turns orange and tilts |
| Review cards | Lift and shadow |
| Buttons | Lift 2px and color change |
| Bag icon | Scale 1.12 |

### Accessibility features

- Visible keyboard focus: `:focus-visible` with an orange outline.
- `alt` text on content images; empty `alt` on decorative avatars.
- ARIA labels on the search field, bag icon, rating stars and quantity controls.
- `prefers-reduced-motion` support disables transitions and smooth scroll.
- `loading="lazy"` on below-the-fold images.

---

## 6. Responsive Breakpoints

| Breakpoint | Changes |
|---|---|
| **≤ 1024px** (tablet and small laptop) | Narrower search box; footer becomes 2 columns; shop and cart stack; cart is no longer sticky |
| **≤ 860px** (tablet portrait) | Hamburger menu appears and links collapse; nav tools move to a full-width row; hero, newsletter and contact become 1 column; offers stack; hero cover stack is centered with a max width |
| **≤ 560px** (phones) | Smaller section padding; compact best-seller and shop rows; "Add to Cart" goes full width; footer is 1 column; smaller form padding |

---

## 7. Forms and Validation

| Form | Fields | Validation |
|---|---|---|
| Search (nav) | Search input | None (design only) |
| Newsletter | Email | `required`, `type="email"` |
| Contact | Name, Email, Message | `required`, `type="email"`, `minlength="10"` on message |

All forms use `action="#"` and do not send data anywhere, since no backend or JavaScript is included.

---

## 8. External Resources

| Resource | Source | Used for |
|---|---|---|
| Fonts | Google Fonts (Fraunces, Karla) | Typography |
| Book covers | covers.openlibrary.org (by ISBN) | All cover images |
| Hero background | images.unsplash.com | Library photo |
| Avatars | i.pravatar.cc | Author and reviewer portraits |

### ISBNs used for covers

| Book | ISBN |
|---|---|
| Atomic Habits | 9780735211292 |
| Dune | 9780441013593 |
| The Hobbit | 9780547928227 |
| The Silent Patient | 9781250301697 |
| Pride and Prejudice | 9780141439518 |
| Clean Code | 9780132350884 |
| The Alchemist | 9780062315007 |
| Sapiens | 9780062316110 |
| Educated | 9780399590504 |
| Where the Crawdads Sing | 9780735219090 |
| Gone Girl | 9780307588371 |
| Becoming | 9781524763138 |

---

## 9. Limitations and Notes

- **No real shopping cart.** Add to Cart, quantity controls, Checkout and the bag counter are visual demos.
- **No working search or sign-in.** The Sign in button scrolls to the contact section as a placeholder.
- **Forms do not submit.** They only show browser validation.
- **Needs internet** for fonts and images; the layout still works offline, but images and fonts will fall back.
- **Sample data.** The author profiles, reviews, contact details and prices are fictional demonstration content. The book titles and authors in the product cards are real books, but the prices and discounts are invented.
- **Category cards** use colored panels and emoji icons instead of photos.
- **Placeholder links.** Social links and "View Details" are placeholders.

---

## 10. Suggested Next Steps

1. Replace placeholder contact details and social links with real ones.
2. Add per-book detail pages for the **View Details** links.
3. Add a backend or e-commerce platform for a real cart and checkout.
4. Self-host images for reliability and speed.
5. Add JavaScript later if you want live search, a working cart or a mobile menu that closes after a click.
