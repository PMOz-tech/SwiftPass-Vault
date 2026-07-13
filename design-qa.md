# SwiftPass Vault Design QA

## Comparison target

- Source URL: `https://swiftpass.ng/vault`
- Source visual truth, desktop: `/Users/temixgold/Documents/Codex/2026-07-13/referenced-chatgpt-conversation-this-is-untrusted/work/source/swiftpass-vault-desktop-top.png`
- Implementation screenshot, desktop: `/Users/temixgold/Documents/Codex/2026-07-13/referenced-chatgpt-conversation-this-is-untrusted/work/swiftpass-vault-clone/local-desktop-top-final.png`
- Source visual truth, mobile: `/Users/temixgold/Documents/Codex/2026-07-13/referenced-chatgpt-conversation-this-is-untrusted/work/source/swiftpass-vault-mobile-top.png`
- Implementation screenshot, mobile: `/Users/temixgold/Documents/Codex/2026-07-13/referenced-chatgpt-conversation-this-is-untrusted/work/swiftpass-vault-clone/local-mobile-top-final.png`
- Viewports: desktop `1440 × 900`; mobile `390 × 844`
- State: public page, top of page, navigation closed, FAQ closed

## Full-view comparison evidence

- Desktop side-by-side: `/Users/temixgold/Documents/Codex/2026-07-13/referenced-chatgpt-conversation-this-is-untrusted/work/swiftpass-vault-clone/qa-desktop-side-by-side-final.png`
- Mobile side-by-side: `/Users/temixgold/Documents/Codex/2026-07-13/referenced-chatgpt-conversation-this-is-untrusted/work/swiftpass-vault-clone/qa-mobile-side-by-side-final.png`
- Desktop page height: source `4356px`; implementation `4356px`.
- Mobile page height: source `6726px`; implementation `6729px`.
- No horizontal overflow at either viewport.

## Focused region comparison evidence

- Source mobile menu: `/Users/temixgold/Documents/Codex/2026-07-13/referenced-chatgpt-conversation-this-is-untrusted/work/source/swiftpass-vault-mobile-menu-open.png`
- Implementation mobile menu: `/Users/temixgold/Documents/Codex/2026-07-13/referenced-chatgpt-conversation-this-is-untrusted/work/swiftpass-vault-clone/local-mobile-menu-open-final.png`
- Source FAQ open state: `/Users/temixgold/Documents/Codex/2026-07-13/referenced-chatgpt-conversation-this-is-untrusted/work/source/swiftpass-vault-mobile-faq-open.png`
- Implementation FAQ open state: `/Users/temixgold/Documents/Codex/2026-07-13/referenced-chatgpt-conversation-this-is-untrusted/work/swiftpass-vault-clone/local-mobile-faq-open-final.png`

Focused comparison was required because the hero artwork, mobile navigation geometry, and accordion expansion were not readable enough in a full-page view.

## Required fidelity surfaces

- Fonts and typography: local Archivo and Fira Mono packages replace the observed Google-hosted files with the same open-source families. Mobile heading sizes, card heading sizes, line heights, wrapping, text transform, and letter spacing were matched to observed computed styles. Desktop hierarchy and wrapping match the source screenshots.
- Spacing and layout rhythm: desktop and mobile section boundaries, card heights, gaps, padding, radii, and total document heights were measured and aligned. Remaining page-height variance is 3px on mobile and 0px on desktop.
- Colors and visual tokens: primary `#0C39ED`, pale section background `#F4F9FF`, white and near-white card fills, muted gray copy, and navy footer match the captured source.
- Image quality and asset fidelity: the public SwiftPass logo, three source folder vectors, document line artwork, all feature/category/security icons, FAQ plus, and social marks are local source assets. No visible source logo or illustration was replaced by a handmade SVG. The mobile menu and open-state minus use a close matching open-source icon because no standalone source file was exposed.
- Copy and content: headings, body copy, chips, feature content, security points, all four FAQ answers, footer labels, and destination links match the captured public page.

## Comparison history

1. Earlier finding: [P1] bundled source SVGs without XML namespaces rendered as broken images. Fix: added namespaces to local copies and rechecked every rendered image; post-fix evidence shows zero broken images.
2. Earlier finding: [P2] desktop hero copy and folder composition sat too low and the page was 8px too tall. Fix: aligned the hero grid to the source top rhythm, corrected document positions, and adjusted the value-section padding. Post-fix evidence: desktop side-by-side comparison and exact `4356px` page height.
3. Earlier finding: [P2] mobile cards and sections produced a page about 5% taller than the source. Fix: matched observed card heights, padding, typography, grid gaps, and section spacing. Post-fix evidence: mobile side-by-side comparison and `6729px` implementation height versus `6726px` source.
4. Earlier finding: [P2] the mobile menu switcher/button geometry and expanded FAQ row differed visibly. Fix: matched menu width, position, spacing, CTA height, and accordion open-row height. Post-fix evidence: focused menu and FAQ screenshots listed above.

## Findings

- No actionable P0, P1, or P2 differences remain.
- [P3] Browser focus rings vary slightly from the source Framer implementation after mouse clicks. Native focus indication was retained for accessibility.

## Primary interactions and runtime checks

- Mobile navigation opens and closes; its audience links and waitlist link are present and correctly targeted.
- Each FAQ item toggles independently and exposes the captured answer text.
- Desktop and mobile browser console checks returned no errors or warnings.
- Packaged production build rendered with zero broken images and no console errors.

## Implementation checklist

- [x] Desktop visual comparison
- [x] Mobile visual comparison
- [x] Mobile menu interaction
- [x] FAQ interaction
- [x] Responsive overflow check
- [x] Console error check
- [x] Production build check

final result: passed
