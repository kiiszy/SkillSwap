# SkillSwap — Professional UI/UX Design Prompt

Copy the brief below into your preferred design or coding assistant. Apply it to the existing SkillSwap project and preserve its working features.

---

Act as a senior product designer, art director, and front-end engineer specializing in premium consumer marketplaces. Redesign SkillSwap into a confident, contemporary skill-sharing platform that feels credible, human, and professionally art-directed.

## Product and user goal

SkillSwap is a paid peer-to-peer skill-sharing marketplace. Its promise is **“Learn a Skill. Share a Skill.”** A single account can buy classes in Learn Mode and create paid classes in Teach Mode. Switching modes must remain clear, reversible, and available throughout the experience.

The audience is Indonesian students, young professionals, and independent creatives. Communicate practical learning, personal connection, and the opportunity to earn by teaching. Keep prices in Indonesian rupiah. Treat existing demo names, reviews, transactions, and photographs as illustrative prototype content; do not invent verified business traction.

## Creative direction: SkillSwap Studio

Create a warm creative-studio identity with confident editorial typography, genuine-looking learning moments, and purposeful color. The experience should feel like a mature startup, with its own recognizable character.

Use a coherent palette:

- Cobalt blue `#2459E8`: primary actions, links, selected states, and brand emphasis.
- Deep navy `#10244D`: hero, sidebar, footer, and high-contrast brand surfaces.
- Mint `#C4F5DD`: selected hero CTA and supportive learning accents, with dark text.
- Amber `#F8CE73`: small decorative accents, ratings, and photography/business categories.
- Lavender `#E9E3FF`: music/language category accents.
- Canvas `#F4F7FC`, white cards `#FFFFFF`, text `#132449`, secondary text `#5D6D89`.

Reserve strong color for focal surfaces and actions. Keep dense reading areas calm. Avoid a uniformly blue page, excessive gradients, unmotivated glass effects, or decorative shapes that compete with content.

## Typography, spacing, and components

Use Manrope for expressive headings and DM Sans or Inter for interface text, with local system fallbacks. Build a deliberate hierarchy: desktop hero 56–64 px, page title 32–40 px, section title 28–32 px, card title 17–20 px, body 14–16 px. Use an 8 px spacing rhythm, a centered 1220 px content area, generous section spacing, and consistent 12–20 px corner radii.

Use thin cool borders, restrained shadows, clear input labels, visible keyboard focus, and accessible contrast. Touch targets should be at least 44 px where practical. Hover effects should clarify interactivity and respect reduced-motion preferences.

## Photography and visual storytelling

Replace flat placeholder illustrations with relevant, premium editorial photography. Show young Indonesian adults actively learning or teaching design, photography, guitar, programming, communication, and cooking. Favor candid interaction, natural window lighting, warm materials, realistic anatomy, and a consistent visual treatment.

Photographs must support the exact class subject. Compose hero imagery as a controlled editorial arrangement with one dominant photo and smaller supporting frames. Use consistent landscape crops for class cards. Preserve faces, hands, and tools when cropping. Keep titles and UI text in HTML, outside photographs. Do not place invented credentials or testimonial claims inside images. Clearly identify generated photographs as illustrative prototype imagery where appropriate.

## Page requirements

1. **Landing:** navy-to-cobalt hero, exact product tagline, mint primary Explore Classes CTA, secondary Start Teaching CTA, editorial learning photographs, category discovery, popular classes, clear three-step explanation, and teaching CTA.
2. **Explore:** tinted page introduction, prominent search, pill category filters, calm white filter sidebar, and aligned three-column desktop class cards. Emphasize class title, relevant photography, instructor, rating, schedule, and price. Include clear results and empty states.
3. **Class detail:** generous photographic cover, structured learning outcomes, instructor information, reviews, and a purchase summary with clear price and seat availability.
4. **Login/register:** photographic brand panel beside an uncluttered form. Keep simulation labels concise and visible. Show validation and recovery guidance clearly.
5. **Choose mode:** two equally considered photographic cards. Differentiate Learn and Teach with blue and mint accents while explicitly stating that users can switch anytime.
6. **Learner pages:** visible class status, schedule, next action, payment history, and review entry. Distinguish information from actions without relying only on color.
7. **Instructor pages:** navy navigation, subtly tinted statistic cards, clear action hierarchy, readable tables, functional class management, and earnings charts derived from saved data.
8. **Create class:** retain all seven steps. Make progress clear, validate fields, emphasize instructor-controlled pricing, explain fee/net earnings, and provide a faithful preview.
9. Apply the same design system to checkout, success, profile, notifications, and informational pages.

## Engineering constraints

Keep a genuine multi-page website: each major feature remains its own HTML file with normal page navigation. Use HTML5, CSS3, vanilla JavaScript, and localStorage. Do not convert it into a single-page application or introduce React, npm, a database, or a backend requirement.

Preserve every existing flow: registration, login, mode switching, search, combined filters, sorting, bookmarks, checkout simulation, enrollment, reviews, class draft/edit/publish, participant management, cancellation, and earnings. Preserve existing user data. Upgrade default image references safely while keeping custom uploaded thumbnails.

Use relative links and local image assets so the project remains GitHub Pages compatible. Design desktop first at 1440 px, then adapt for 1024 px, 768 px, and 390 px without horizontal page overflow. Ensure tables scroll within their own containers on small screens.

## Deliverables and acceptance criteria

Implement the redesigned pages and shared components, rather than returning only advice or a static mockup. Provide the updated runnable project, reusable design tokens, image assets, and a concise explanation of changes. Verify local links, JavaScript syntax, image resolution, data preservation, and the key learner/instructor flows. Inspect desktop and mobile rendering when a browser is available, and state any verification limitations honestly.

The finished product should communicate both ideas immediately: **“I can learn from someone here”** and **“I can teach what I know and earn.”**
