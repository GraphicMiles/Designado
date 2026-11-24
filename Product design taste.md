VISUAL DESIGN JUDGMENT

Strict Visual Standards, Design Philosophy, Prohibited Patterns and Implementation Protocol

Classification: Mandatory global design skill
Priority: Critical
Scope: Every website, web application, landing page, dashboard, mobile interface, form, navigation system, component and responsive layout created or modified by the agent.

Compliance requirement: This entire document must be read, understood and followed before any visual implementation begins.

---

0. THE NON-NEGOTIABLE DESIGN CONTRACT

You are responsible for producing deliberately designed interfaces, not generic AI-generated web pages.

Your job is not to produce something that merely looks acceptable, modern, polished or professional.

Your job is to create a visually coherent experience that demonstrates:

- Deliberate composition.
- Good visual judgment.
- Strong hierarchy.
- Purposeful imagery.
- Controlled typography.
- Excellent proportions.
- Restrained and intentional use of color.
- Appropriate visual density.
- Meaningful spacing.
- Consistent design decisions.
- A clear relationship between the product's purpose and its appearance.

You must not use your learned defaults, familiar website templates or commonly generated AI design patterns as substitutes for actual design thinking.

The user's established visual preferences are the default authority for all unspecified design decisions.

The following principles are mandatory:

1. Do not introduce visual elements merely because they are common in modern websites.
2. Do not interpret missing instructions as permission to improvise.
3. Do not introduce unnecessary design patterns to fill space.
4. Do not substitute generic components for actual composition.
5. Do not sacrifice visual quality for implementation convenience.
6. Do not make arbitrary decisions about color, spacing, typography, imagery or layout.
7. Do not declare a design complete simply because the code works.
8. Do not override these standards with your own aesthetic preferences.

When a design decision is unspecified, use the defaults and prohibitions in this document.

When a choice is unnecessary, do not make it.

When removing something improves the design, remove it.

---

1. MANDATORY SKILL READING AND COMPREHENSION

This skill must not be skimmed, partially read, or treated as optional inspiration.

Before starting any design-related task:

1. Read this entire document from beginning to end.
2. Do not stop after reading the first few sections.
3. If the file is too long for the available context, read it in sequential sections until the entire document has been consumed.
4. Do not assume familiarity with a previous version is sufficient.
5. Extract the applicable requirements and prohibitions into a task-specific compliance checklist.
6. Retain those requirements throughout implementation.
7. Verify the resulting interface against the checklist before completion.

If another skill, prompt or project instruction references visual design, that does not replace reading this document.

Do not claim compliance simply because the document was opened.

You must understand the rules and apply them.

1.1 Instruction precedence

Resolve conflicting instructions using this order:

1. Higher-priority system, platform and safety requirements.
2. The user's explicit instructions for the current task.
3. The user's established preferences in this skill.
4. The existing project's intentional design system and conventions, unless the user requests a redesign.
5. General design conventions, only where none of the above supplies a decision.

Generic AI design conventions are never a reason to override this skill.

An explicit task-specific request may override a normal aesthetic prohibition, but only to the extent of the requested exception.

For example, requesting a gradient for one particular hero does not authorize introducing gradients throughout the application.

1.2 Missing instructions are not permission

This rule is particularly important.

The user should not have to list every undesirable design decision on every task.

If the user says:

- Build a website, do not automatically generate a SaaS template.
- Make a dashboard, do not automatically generate a collection of cards.
- Create a landing page, do not automatically add eyebrow labels everywhere.
- Make it modern, do not automatically introduce gradients, glassmorphism or excessive animations.
- Make it beautiful, do not automatically use saturated colors, giant typography or arbitrary decoration.
- Make it professional, do not automatically turn it into an editorial template.

Use the established visual standards even when the user does not repeat them.

The burden of making a good decision belongs to the agent, not the user.

---

2. THE DESIGN PHILOSOPHY

2.1 Intention over decoration

Every element must have a functional, informational or compositional reason to exist.

There are three acceptable reasons for adding something:

- It helps users understand information.
- It helps users perform an action.
- It materially improves the visual composition.

If none applies, do not add it.

Do not create decorative elements simply because an area looks empty.

Do not add a background pattern because a background looks plain.

Do not add a border because two elements are close together.

Do not add an icon because a heading looks lonely.

Do not add a badge because a section looks incomplete.

Do not add a caption because a heading appears too simple.

Do not add a card because content needs somewhere to sit.

Think about what the interface actually needs.

2.2 Composition over component accumulation

A good website is not a collection of independently styled components.

It is a unified visual composition.

The entire viewport should be considered when making decisions.

Think about:

- Where the eye should go first.
- Which element deserves the most space.
- How much visual weight each section occupies.
- How images relate to text.
- How the sections transition into each other.
- Where negative space is necessary.
- Where content needs greater density.
- Whether the composition feels balanced.

Do not build every section independently and expect the page to become coherent automatically.

2.3 Restraint is a design requirement

Do not maximize the number of elements.

Do not maximize the number of colors.

Do not maximize visual effects.

Do not maximize typography variation.

Do not maximize whitespace.

Do not maximize card usage.

Do not maximize decoration.

A successful interface can be visually rich while using very few elements.

Restraint means choosing the right elements, not removing everything.

---

3. ESTABLISHED VISUAL IDENTITY AND DEFAULTS

Unless the project already has a deliberate design system or the user explicitly requests another direction, apply these defaults.

Design dimension| Mandatory default
Overall aesthetic| Clean, deliberate, restrained, purposeful
Foundation| Black-on-white
Accent color| None by default; introduce deliberately
Typography| Maximum two font families
CTAs| Squared or modestly rounded
Shadows| None
Gradients| None
Glassmorphism| None
Layout| Flexbox-first; no CSS Grid
Borders| No decorative borders
Cards| Only when functionally justified
Imagery| Meaningful, prominent where appropriate
Hero| The visual centerpiece
Icons| Lucide or Font Awesome
Animation| No decorative hover animations
Spacing| Proportional and controlled
Components| Reusable and consistent
Responsiveness| Intentionally designed, not merely resized

These are defaults, not optional suggestions.

Do not replace them with arbitrary alternatives.

---

4. COLOR SYSTEM: STRICT CONTROL

Color is one of the most important aspects of the visual identity.

Bad color choices can make an otherwise functional interface uncomfortable to look at.

4.1 Default palette

When no specific brand palette exists, begin with a monochromatic foundation:

- White backgrounds.
- Black or near-black primary text.
- Restrained neutral secondary text.
- Subtle neutral surface differentiation where required.

Do not introduce an accent color automatically.

An accent is a deliberate decision, not a mandatory ingredient.

4.2 Color limits

Use no more than two primary chromatic colors.

The broader palette must never exceed four distinct color families unless the functionality genuinely demands additional semantic categories.

Different lightness levels of the same color are not separate accent choices.

Do not create a palette containing numerous unrelated colors.

Do not use different colors for every section.

Do not give every component its own color identity.

4.3 Color selection requirements

Before introducing an accent color, establish:

- What the color communicates.
- Why the product needs it.
- Where it will appear.
- Whether it competes with the primary content.
- Whether it remains comfortable across large and small surfaces.
- Whether the entire page remains visually coherent.

Do not choose colors randomly.

Do not select an accent solely because it is fashionable.

Do not select an accent because it makes a screenshot look more colorful.

Do not use fluorescent, excessively saturated, eye-straining combinations.

Do not use muddy, lifeless or inconsistent palettes.

4.4 Prohibited color behavior

Never introduce:

- Random red accents.
- Random purple or blue gradients.
- Different accent colors for unrelated buttons.
- Colored icons without semantic purpose.
- Random colored section backgrounds.
- Decorative colored pills.
- Excessive multicolored text.
- Unnecessary colored borders.
- Arbitrary color combinations.

Red must not become a general attention-grabbing accent.

Use destructive semantic coloring only where the action genuinely warrants it, and keep its application consistent.

4.5 Semantic color

Color must communicate consistently.

- Success uses a recognizable success treatment.
- Errors use a recognizable error treatment.
- Warnings use a recognizable warning treatment.
- Destructive actions use a recognizable destructive treatment.
- Ordinary interface elements remain neutral.

Do not assign arbitrary meanings to colors.

Do not use semantic colors as decorative accents.

---

5. TYPOGRAPHY: CONTROL, CLARITY AND RESTRAINT

Typography should make the interface easier to understand and visually stronger.

It must never become a collection of decorative text treatments.

5.1 Font families

Use a maximum of two font families.

Preferred options:

- Manrope.
- Poppins.
- Space Grotesk.
- Inter.

Choose one primary family.

Introduce a second family only when it provides a genuine visual benefit.

The default should be a single coherent family rather than unnecessary font pairing.

Do not introduce additional typefaces because one section needs to look different.

5.2 Typography hierarchy

Establish a clear, limited typographic hierarchy.

The interface should distinguish:

- Primary page headings.
- Section headings.
- Subheadings.
- Body text.
- Supporting information.
- Functional labels.

Do not create a separate typography style for every component.

Do not make every heading oversized.

Do not make body text unnecessarily small.

Do not use exaggerated weight differences to manufacture hierarchy.

Typography must remain readable at actual display sizes.

5.3 Eyebrow text: prohibited by default

Do not automatically place small uppercase text above headings.

Examples of unwanted patterns:

- ABOUT US above About Us.
- OUR SERVICES above Services.
- DISCOVER MORE above Discover More.
- WHY CHOOSE US above Why Choose Us.
- FEATURES above Features.

These labels frequently add no useful information.

Do not repeat them throughout a page.

Use a section label only when it conveys genuinely necessary information, such as a category, status or meaningful classification.

When there is no clear informational purpose, omit it.

5.4 Tiny decorative text

Do not use tiny text as decoration.

Avoid:

- Unnecessary micro-labels.
- Arbitrary uppercase captions.
- Decorative metadata.
- Tiny supporting paragraphs.
- Random letter-spaced words.
- Small text scattered around large headings.
- Numbers used purely as visual decoration.
- Text that is too small to comfortably read.

All displayed text must serve a purpose.

5.5 Headline treatment

Headlines should be clear and natural.

Avoid:

- Unnecessary line breaks.
- Artificially narrow text containers.
- Arbitrary individual word highlighting.
- Excessive italic treatment.
- Multiple font weights in one sentence without reason.
- Huge headings that overwhelm the page.
- Generic marketing language.
- Headlines that occupy space without communicating anything.

Use deliberate line lengths and proportions.

Do not break text into multiple lines simply to imitate an editorial design.

5.6 Copy quality

Never use placeholder marketing copy as a substitute for understanding the product.

Avoid generic phrases such as:

- Experience the future.
- Redefining possibilities.
- Innovation without limits.
- Your journey starts here.
- Elevate your experience.

Use specific language that communicates what the product actually does.

Do not invent statistics, customer claims or product capabilities.

Do not add paragraphs merely to fill space.

---

6. IMAGERY AND VISUAL ASSETS

Imagery must be treated as a genuine part of the design, not an optional decoration.

This is especially important for hero sections.

6.1 No image-shaped placeholders

The following are unacceptable in a finished interface:

- Empty rectangular image containers.
- Gray boxes pretending to be photographs.
- Random colored rectangles occupying image positions.
- Empty image frames.
- Collections of boxes used to simulate screenshots.
- Abstract grids used as substitutes for actual product imagery.
- Unrelated stock illustrations inserted to fill space.

A blank box is not an image.

A collection of empty boxes is not a visual composition.

Do not present unfinished image placeholders as completed design.

6.2 Image selection

When imagery is appropriate:

1. Determine what the image needs to communicate.
2. Understand the visual character of the product.
3. Look for existing project assets and genuine product screenshots.
4. Reuse relevant, available assets.
5. Generate or source appropriate imagery when supported.
6. Select images with meaningful composition.
7. Establish their aspect ratio and cropping intentionally.
8. Integrate them into the layout as part of the composition.

Do not insert unrelated imagery simply to make the page look less empty.

6.3 Hero imagery

The hero should usually contain the most significant visual moment on the page.

Give meaningful imagery enough space and prominence.

Depending on the product, use:

- Photography.
- Real product screenshots.
- Product mockups.
- Purposeful illustrations.
- Carefully generated visual assets.
- Strong graphical compositions.

The image must represent or reinforce the website's actual purpose.

Dithered imagery is a welcome visual direction when it suits the product, particularly where a distinctive, expressive image treatment improves the result.

However, do not apply dithering indiscriminately.

Do not turn every image into a decorative pattern.

6.4 Image quality

Avoid:

- Blurry images.
- Low-resolution images displayed excessively large.
- Unrelated stock photography.
- Poorly cropped faces or subjects.
- Images with incompatible visual styles.
- Random image ratios.
- Excessive rounded image containers.
- Repeated images used to fill multiple sections.
- Images with no connection to the accompanying content.

Do not use fake product screenshots or fabricate genuine customer imagery.

6.5 Missing assets

When suitable imagery is unavailable:

1. Search the project for reusable assets.
2. Use available image-generation capabilities when appropriate.
3. Use an honest typographic or graphic composition when imagery is not essential.
4. Do not fabricate a screenshot or imply that a nonexistent product asset is real.
5. Do not leave a permanent empty image box.

If a particular genuine asset is essential and cannot be obtained, report the blocker rather than disguising it.

---

7. HERO SECTION: THE VISUAL CENTERPIECE

The hero must receive deliberate attention.

It should establish the identity, purpose and visual direction of the website immediately.

Do not treat it as a standard collection of components.

7.1 Do not automatically use this template

Never default to:

- Tiny uppercase eyebrow label.
- Oversized generic heading.
- Generic paragraph.
- Two large pill-shaped buttons.
- Three floating badges.
- A collection of decorative statistic cards.
- Random gradient background.
- Generic three-column features preview.
- Arbitrary floating circles and dots.

This is a particularly common AI-generated design cliché.

7.2 Hero composition

Establish:

- The main focal point.
- The headline's visual weight.
- Supporting text hierarchy.
- The relationship between text and imagery.
- The position of the primary action.
- The use of negative space.
- The relationship with the navigation above it.
- The transition into the next section.

The hero should feel like a deliberate visual statement.

7.3 Strong imagery

Where appropriate, use a substantial visual asset rather than a token image.

Do not make the image so small that it becomes incidental.

Do not fill the hero with meaningless floating cards or decorative UI fragments.

7.4 Hero actions

Use a clear primary action.

A secondary action is allowed only when it provides a meaningful alternative.

Do not add multiple competing buttons simply to make the hero look complete.

Buttons must describe real actions.

---

8. LAYOUT: ABSOLUTE CONTROL OVER GENERIC GRIDS

This is a strict implementation requirement.

8.1 Flexbox-first, no CSS Grid

Do not use CSS Grid for authored page layouts.

Use Flexbox for:

- Navigation.
- Horizontal and vertical alignment.
- Two-column compositions.
- Image-and-text sections.
- Feature arrangements.
- Responsive wrapping.
- Content groups.
- Component positioning.

Do not use "display: grid", "grid-template-columns", "grid-template-rows" or framework grid utilities for layout.

Do not automatically split content into equal columns.

Flexibility and natural content proportions are preferred over rigid arrangements.

8.2 No automatic card grids

Do not turn every section into:

- Three equal feature boxes.
- Four equal service cards.
- Repeated two-column card arrangements.
- Uniform dashboard-style boxes.
- Identical collections of icon-and-text components.

Equal sizing must have a reason.

Different content can have different visual importance.

Do not force every element into the same size and shape.

8.3 Layout proportions

Consider the actual available viewport and content.

Avoid:

- Arbitrarily narrow content columns.
- Excessively wide paragraphs.
- Tiny images beside enormous text.
- Unbalanced two-column sections.
- Oversized empty regions.
- Uneven alignment.
- Unnecessary fixed-height containers.
- Rigid layouts that break on mobile.

Use content-appropriate widths.

Do not impose identical widths on elements that serve different purposes.

8.4 Alignment

Alignment must be intentional.

Avoid:

- Randomly centered elements.
- Inconsistent left edges.
- Headings aligned differently without a reason.
- Misaligned images and text.
- Arbitrary offsets.
- Uneven navigation spacing.
- Components that appear to float independently.

Establish a consistent alignment system and maintain it throughout the page.

---

9. BORDERS, DIVIDERS AND VISUAL CONTAINERS

One of the most common design failures is excessive use of borders.

A page must not look like a spreadsheet or a collection of outlined boxes.

9.1 Decorative borders are prohibited

Do not add borders merely to:

- Separate every section.
- Outline every card.
- Outline text blocks.
- Outline image containers.
- Decorate navigation.
- Separate adjacent paragraphs.
- Create visual interest.
- Make an otherwise empty component visible.

Do not use thin lines as a substitute for visual hierarchy.

Do not add multiple nested outlines.

Do not add horizontal rules between every block.

Do not add vertical divider lines throughout the page.

9.2 When borders are permitted

Borders may be used when they have a necessary functional purpose.

Examples:

- Form field boundaries where needed for clarity.
- Table boundaries where necessary for data comprehension.
- Clear focus indicators.
- A genuine structural boundary.
- A functional separation that cannot be communicated more effectively otherwise.

Keep these treatments restrained and consistent.

9.3 Alternatives to borders

Prefer:

- Intentional spacing.
- Alignment.
- Typography.
- Natural grouping.
- Controlled background differentiation.
- Image placement.
- Scale and proportion.

Do not automatically place content inside a box.

---

10. CARDS: FUNCTION BEFORE APPEARANCE

Cards are not a universal container.

Do not use a card for every piece of information.

10.1 Valid reasons for a card

Use cards when content is genuinely:

- Independently selectable.
- Interactive.
- Comparable with other items.
- A distinct object or entity.
- A grouped unit of information.
- A functional dashboard module.

10.2 Invalid reasons for a card

Never introduce cards merely because:

- A section contains text.
- A paragraph needs visual separation.
- You want a three-column layout.
- The page looks too empty.
- You want a modern SaaS appearance.
- Every other section already contains cards.

10.3 Card restrictions

Avoid:

- Cards nested inside cards.
- Excessive rounded corners.
- Large padding that wastes space.
- Unnecessary shadows.
- Decorative borders.
- Identical cards repeated without a reason.
- Cards that contain only an icon, heading and generic sentence.
- Floating cards used as random hero decoration.

If content can be presented directly and more clearly without a card, do that.

---

11. SPACING AND PADDING

Spacing must create relationships between elements.

It must not make an interface feel inflated or disconnected.

11.1 Proportional spacing

Use a consistent spacing scale.

Spacing should reflect:

- The importance of the element.
- The relationship between neighboring elements.
- The density of the content.
- The dimensions of the viewport.
- The hierarchy of the page.

Use larger spacing to distinguish major sections.

Use smaller spacing for related elements.

Do not assign arbitrary large margins to everything.

11.2 Prohibited spacing behavior

Avoid:

- Excessive section padding.
- Huge empty vertical gaps.
- Oversized card padding.
- Excessive gaps between headings and paragraphs.
- Unnecessarily tall navigation.
- Large margins around tiny elements.
- Empty containers with fixed heights.
- Inflated hero sections with little content.
- Interfaces that require excessive scrolling because of unnecessary spacing.

11.3 Negative space

Whitespace is valuable when it improves composition.

Do not interpret whitespace as an instruction to leave enormous empty areas.

Do not distribute everything evenly just to fill the viewport.

Use negative space to emphasize important content.

An interface should feel composed, not abandoned.

---

12. DECORATION AND BACKGROUND TREATMENT

Decoration must never become the primary content.

12.1 Prohibited decorative patterns

Avoid by default:

- Random dots.
- Dot matrices.
- Decorative circles.
- Floating geometric shapes.
- Random plus signs.
- Decorative crosses.
- Arbitrary background grids.
- Abstract line patterns.
- Random numbers.
- Decorative coordinate markings.
- Unnecessary background textures.
- Random geometric shapes behind text.
- Excessive abstract illustrations.

Do not add these to make an empty background appear designed.

12.2 Backgrounds

Default to clean, controlled surfaces.

Do not use:

- Random gradient backgrounds.
- Several competing background colors.
- Excessively textured backgrounds.
- Patterned backgrounds without purpose.
- Decorative background shapes on every section.
- Multiple competing layers.

Background treatments must support content and composition.

12.3 Effects

The following are prohibited by default:

- Box shadows.
- Glassmorphism.
- Excessive blur.
- Glowing borders.
- Artificial elevation.
- Decorative gradients.
- Neon effects.
- Unnecessary transparency layers.
- Excessive backdrop filters.

Do not imitate visual depth merely to make the interface look expensive.

---

13. BUTTONS, CTA AND INTERACTIVE ELEMENTS

13.1 Button shapes

Prefer squared or modestly rounded buttons.

Do not automatically use pill-shaped buttons.

Avoid unnecessarily large corner radii.

Do not give unrelated components completely different corner treatments.

Maintain a consistent shape language.

13.2 Button hierarchy

Distinguish between:

- Primary actions.
- Secondary actions.
- Tertiary actions.
- Destructive actions.

Do not style every action as a primary button.

Do not use multiple competing high-contrast buttons within the same component without a genuine reason.

13.3 Button content

Buttons must have clear, meaningful labels.

Avoid:

- Generic labels where a specific action is possible.
- Decorative icons without meaning.
- Unnecessary arrow symbols.
- Excessive button text.
- Multiple redundant actions.

13.4 Interactive states

Provide functional states:

- Default.
- Hover.
- Focus.
- Active.
- Disabled.
- Loading.
- Success or error feedback where appropriate.

These are functional requirements, not an excuse for decorative animation.

---

14. ICONOGRAPHY

Use icons only when they improve comprehension or interaction.

Preferred libraries:

- Lucide.
- Font Awesome.

Do not invent a random icon style for every section.

Do not mix unrelated icon families.

Avoid:

- Arbitrary colorful icons.
- Emoji as interface icons.
- Large collections of decorative icons.
- Icons next to every heading.
- Icons used to fill empty space.
- Generic icon illustrations replacing actual imagery.
- Inconsistent stroke weights.
- Inconsistent icon sizing.

An icon should have a recognizable meaning.

If text communicates the information more clearly, use text.

Do not add both an icon and a label when one is unnecessarily repetitive.

---

15. SECTION DESIGN AND PAGE STRUCTURE

A website must have a coherent beginning, middle and ending.

Do not build sections as unrelated visual experiments.

Before implementation, establish the purpose of each section.

15.1 Required planning sequence

Work through the website in this order:

1. Navigation.
2. Hero.
3. First supporting section.
4. Remaining content sections in their intended order.
5. Calls to action where appropriate.
6. Footer.

For each section, establish:

- Its purpose.
- Its essential content.
- Its relationship to the preceding section.
- Its visual composition.
- Its primary hierarchy.
- Its relationship to the overall design.

15.2 Section variation

Sections may have different compositions.

Do not make every section identical.

Do not repeat the same left-text/right-image arrangement throughout the page.

Do not turn every section into a three-column grid.

Do not repeat the same heading, paragraph and card pattern.

Variation must come from the content and the visual direction, not arbitrary styling.

15.3 Section necessity

Do not add sections just because a typical website template contains them.

For example, do not automatically add:

- Statistics.
- Testimonials.
- Newsletter signups.
- Logo clouds.
- Pricing sections.
- Feature grids.
- FAQ sections.
- Blog previews.
- Decorative quote sections.

Only include a section when it serves the product, audience or requested user journey.

Never invent testimonials, company logos, customer counts, performance figures or claims.

15.4 Footer

The footer should conclude the experience.

Avoid turning it into another oversized promotional section.

Do not add numerous unrelated columns, unnecessary descriptions or random decorative labels.

Include only useful navigation, contact information, legal links and relevant brand information.

---

16. PREVENT EDITORIAL DESIGN SLOP

An editorial appearance must never be the default solution to a design task.

The following patterns are prohibited unless the product genuinely calls for editorial presentation or the user explicitly requests it:

- Huge oversized display typography dominating every section.
- Tiny uppercase labels above nearly every heading.
- Arbitrary giant numbers.
- Excessive italic text.
- Unnatural headline line breaks.
- Large quotation marks used as decoration.
- Randomly offset text blocks.
- Asymmetry without compositional justification.
- Tiny captions scattered around photographs.
- Newspaper-like columns for ordinary product content.
- Excessive typography-driven decoration.
- Repeated image-and-caption compositions.
- Huge empty spaces surrounding very small amounts of content.

Do not mistake editorial design for sophisticated design.

Do not force ordinary businesses, products or applications into a magazine aesthetic.

Choose the visual language that best communicates the actual product.

---

17. CONTENT AND VISUAL HIERARCHY

The presentation must reflect the importance of the information.

Do not give insignificant content more visual prominence than essential information.

Do not make every section equally loud.

Do not place decorative content above important information.

Do not use visual hierarchy to disguise missing substance.

Use meaningful distinctions between:

- Primary information.
- Supporting information.
- Actions.
- Navigation.
- Status and feedback.
- Secondary details.

Avoid repeating the same information in headings, descriptions, badges and captions.

The interface must be understandable without requiring users to interpret unnecessary decoration.

---

18. RESPONSIVE DESIGN

Responsiveness is a design requirement, not a final CSS patch.

Do not simply shrink the desktop layout.

A mobile interface must have its own deliberate composition.

18.1 Mobile priorities

Consider:

- Content priority.
- Natural reading order.
- Navigation accessibility.
- Touch-target dimensions.
- Text legibility.
- Image cropping.
- Available space.
- Component density.
- Scrolling behaviour.
- Fixed and sticky elements.
- Keyboard interaction.
- Form usability.

18.2 Prohibited mobile behavior

Avoid:

- Desktop layouts squeezed into narrow screens.
- Tiny typography.
- Overflowing navigation.
- Clipped content.
- Horizontal scrolling without a genuine reason.
- Unnecessarily tall cards.
- Images with incorrect cropping.
- Excessive vertical padding.
- Elements becoming visually disconnected.
- Hiding important functionality without an alternative.

18.3 Responsive composition

Recompose elements when necessary.

Change their arrangement according to the viewport rather than forcing identical proportions everywhere.

Ensure that visual hierarchy survives the transition.

The mobile version must feel designed, not merely compressed.

---

19. MOTION AND ANIMATION

Motion must serve interaction or provide meaningful feedback.

19.1 Default prohibition

Do not introduce decorative hover animations.

Do not automatically add:

- Scale transformations.
- Floating animations.
- Bouncing elements.
- Spinning decorations.
- Excessive entrance animations.
- Scroll-triggered animations.
- Animated gradients.
- Moving backgrounds.
- Parallax effects.
- Animated borders.
- Unnecessary page transitions.

19.2 Permitted motion

Functional motion is allowed when it helps users understand an action.

Examples:

- Opening and closing a menu.
- Expanding an accordion.
- Showing a dialog.
- Confirming a successful action.
- Indicating loading.
- Transitioning between meaningful interface states.

Keep motion restrained and predictable.

Respect reduced-motion accessibility preferences.

---

20. FUNCTIONAL DESIGN AND ACCESSIBILITY

Visual quality must not come at the expense of usability.

Maintain:

- Adequate text contrast.
- Readable text sizes.
- Visible focus states.
- Accessible controls.
- Semantic HTML.
- Appropriate labels.
- Clear error messages.
- Keyboard navigation.
- Touch-friendly interactions.
- Appropriate alternative text.
- Correct heading hierarchy.

Do not remove functional boundaries merely because they are visually unattractive.

Improve them while preserving usability.

Do not sacrifice accessibility to achieve a minimalist appearance.

Do not make important information depend entirely on color.

---

21. COMPONENT AND CSS IMPLEMENTATION STANDARDS

Good visual judgment must be reflected in the implementation.

21.1 Reusable components

Use reusable components where repeated functionality or design patterns genuinely exist.

Avoid both extremes:

- Repeating the same implementation unnecessarily.
- Creating excessive abstractions for simple elements.

Reusable components should preserve visual consistency.

21.2 Semantic naming

Use meaningful names for:

- Components.
- CSS classes.
- IDs.
- Variables.
- Design tokens.
- Sections.

Avoid meaningless names and arbitrary abbreviations.

Class names should communicate their purpose.

21.3 CSS discipline

Avoid:

- Unnecessary absolute positioning.
- Arbitrary hardcoded spacing everywhere.
- Repeated conflicting CSS declarations.
- Excessive specificity.
- Uncontrolled global selectors.
- Random inline styles.
- Duplicate component styles.
- Excessive "!important".
- Unnecessary animation libraries.
- Unnecessary UI libraries.
- CSS overrides layered on top of previous mistakes.

Use consistent design tokens for recurring colors, spacing, typography and dimensions.

Do not introduce new design tokens for values that already exist.

21.4 Existing project investigation

Before modifying an existing interface:

1. Inspect the project's current structure.
2. Identify existing components and styles.
3. Understand the current design system.
4. Find the actual page entry point.
5. Identify existing assets.
6. Understand reusable patterns.
7. Identify responsive behavior.
8. Preserve correct functionality.

Do not replace an existing design system simply because a fresh template is easier to generate.

Do not introduce conflicting CSS or duplicate components.

---

22. THE MANDATORY DESIGN WORKFLOW

Follow this workflow for every substantial visual task.

PHASE 1: INVESTIGATION

Understand the project before designing.

Determine:

- What the product does.
- Who uses it.
- What the user needs to accomplish.
- What information matters most.
- What functionality must remain intact.
- What content and assets already exist.
- What design conventions already exist.
- What constraints apply.

Do not invent a product identity from a few keywords.

PHASE 2: VISUAL DIRECTION

Establish a coherent design direction.

Define:

- Overall visual personality.
- Background treatment.
- Primary text color.
- Accent color, if justified.
- Typography.
- Component shapes.
- Image direction.
- Layout approach.
- Spacing system.
- Navigation treatment.

Do not choose these independently.

They must work together.

PHASE 3: PAGE COMPOSITION

Plan the complete page before implementation.

Establish the order and purpose of the sections.

Determine:

- The primary focal point.
- Hero composition.
- Image placement.
- Text hierarchy.
- Section transitions.
- Visual rhythm.
- Footer structure.

Do not fill the page with unnecessary sections.

PHASE 4: IMPLEMENTATION

Implement in a deliberate sequence.

Start with navigation.

Then implement the hero as the main visual composition.

Continue through each section in order.

Finish with the footer.

Do not randomly jump between sections and introduce inconsistent visual decisions.

Do not ask the user to approve every minor implementation decision. Use this skill to make decisions independently, except where a genuinely blocking requirement is unclear.

PHASE 5: VISUAL INSPECTION

Inspect the actual rendered interface.

Do not assume the interface looks correct because the source code appears correct.

Look at the page at realistic viewport dimensions.

Inspect the complete page, not just the hero.

Look specifically for:

- Generic AI-generated patterns.
- Unnecessary labels.
- Poor color combinations.
- Weak hierarchy.
- Excessive borders.
- Excessive card usage.
- Empty image boxes.
- Poor image cropping.
- Excessive padding.
- Poor proportions.
- Unnatural typography.
- Inconsistent alignment.
- Visual clutter.
- Repeated section layouts.
- Mobile layout failures.

PHASE 6: REFINEMENT

Fix visual problems rather than explaining them away.

Remove unnecessary elements.

Correct spacing.

Improve proportions.

Fix image treatment.

Correct typography.

Improve alignment.

Ensure the color system is consistent.

Inspect the result again.

---

23. MANDATORY VISUAL QUALITY GATE

A design cannot be declared complete until it passes this checklist.

Product understanding

- [ ] The interface reflects the actual product.
- [ ] The design suits the intended audience.
- [ ] The primary user action is clear.
- [ ] No unnecessary sections were invented.
- [ ] Existing intentional functionality has been preserved.

Composition

- [ ] There is a clear visual focal point.
- [ ] The hero has a deliberate composition.
- [ ] The page has a coherent visual rhythm.
- [ ] The sections relate to one another.
- [ ] Alignment and proportions are intentional.
- [ ] Negative space is controlled.

Typography

- [ ] No unnecessary eyebrow labels.
- [ ] No decorative micro-text.
- [ ] No excessive uppercase text.
- [ ] No unnecessary font families.
- [ ] No exaggerated typography.
- [ ] Text remains legible.
- [ ] Headings communicate meaningful information.

Color

- [ ] The palette follows the established color limits.
- [ ] Colors are intentional.
- [ ] No arbitrary accent colors.
- [ ] No uncomfortable combinations.
- [ ] Semantic colors have consistent meanings.
- [ ] No unwanted gradients.

Imagery

- [ ] Images serve a purpose.
- [ ] Important visual assets are prominent where appropriate.
- [ ] No empty image placeholders in the finished interface.
- [ ] Images are appropriately cropped.
- [ ] Image styles are consistent.
- [ ] No fabricated product assets.

Layout

- [ ] No CSS Grid was used for authored layouts.
- [ ] Flexbox is used appropriately.
- [ ] No generic card grids.
- [ ] No unnecessary containers.
- [ ] No excessive padding.
- [ ] No unexplained empty spaces.

Visual cleanliness

- [ ] No unnecessary borders.
- [ ] No excessive divider lines.
- [ ] No unnecessary shadows.
- [ ] No glassmorphism.
- [ ] No random background patterns.
- [ ] No decorative dots or geometric noise.
- [ ] No excessive icons.
- [ ] No editorial design clichés without justification.

Functionality and responsiveness

- [ ] Buttons perform their intended actions.
- [ ] Forms remain usable.
- [ ] Interactive states are present.
- [ ] Keyboard access is preserved.
- [ ] Mobile composition has been inspected.
- [ ] No unwanted overflow or clipping.
- [ ] Accessibility has not been compromised.

Final visual judgment

- [ ] The interface feels deliberately designed.
- [ ] The product has a coherent visual identity.
- [ ] The design does not resemble a generic AI template.
- [ ] Every significant element has a reason to exist.
- [ ] Removing unnecessary elements would not improve the result.

Any failed item must be investigated and corrected before the work is reported as complete.

A checklist must not be marked complete without actual verification.

---

24. FAILURE CONDITIONS

The following are considered design failures, even when the application technically works:

1. A website that looks like a generic AI-generated landing page.
2. A hero composed of generic text and empty image boxes.
3. A page filled with repetitive card collections.
4. Excessive eyebrow labels and micro-text.
5. Unnecessary borders and divider lines.
6. Random or unpleasant color choices.
7. Excessively inflated padding.
8. Decorative elements with no purpose.
9. An editorial aesthetic imposed on an unrelated product.
10. An inconsistent visual language.
11. Incorrect or meaningless imagery.
12. A design that ignores the user's established preferences.
13. A mobile layout that merely squeezes the desktop version.
14. A finished page that has not been visually inspected.
15. A design that satisfies individual component requirements but fails as a complete composition.

Do not defend a failed design by saying that it is modern, trendy, minimal, professional or consistent with common web conventions.

Those descriptions do not establish quality.

---

25. HOW TO HANDLE UNCERTAINTY

When an instruction does not specify a visual detail, do not make arbitrary decisions.

Use this decision protocol:

Case A: The user's existing preferences already determine the decision.

Follow those preferences.

Example: No background color specified.

Default to white or an appropriate neutral surface, not an arbitrary gradient.

Case B: The project already has an intentional design system.

Follow its established conventions unless the user asks for a redesign.

Case C: Several choices are possible and all satisfy the requirements.

Choose the simplest option that preserves visual quality and introduces the fewest unnecessary elements.

Do not add another visual treatment merely to demonstrate creativity.

Case D: The proposed addition is decorative and unnecessary.

Do not add it.

Case E: A required asset is unavailable.

Do not fake it. Find an honest alternative or report the actual blocker.

Case F: A genuine functional or technical conflict exists.

Preserve functionality and accessibility. Find the least visually disruptive solution.

Case G: An important decision genuinely cannot be resolved from the available information.

Do not invent a brand identity, fabricate content or make an irreversible assumption. Ask one focused question about the blocking decision.

Do not ask questions about details that this skill has already resolved.

Conservative decision rule

When two solutions satisfy the task, prefer the one that:

1. Follows the user's established taste.
2. Has fewer unnecessary elements.
3. Communicates more clearly.
4. Uses more purposeful imagery.
5. Has cleaner composition.
6. Introduces fewer new visual patterns.
7. Is easier to maintain consistently.

Do not automatically prefer the simpler implementation if it produces a visually inferior result. Simplicity must not become an excuse for poor design.

---

26. FINAL RESPONSE AND HONEST VERIFICATION

When reporting a completed design task:

Briefly state:

- What was implemented.
- What major visual decisions were made.
- Which responsive states were inspected.
- Whether actual visual inspection was performed.
- Any outstanding asset or verification limitations.

Never claim that:

- A layout was visually inspected when it was not.
- A mobile design was tested when it was not.
- An image asset is genuine when it was fabricated.
- All quality checks passed when some were skipped.

Be transparent about limitations.

Do not bury incomplete design work beneath a long completion report.

---

27. THE FINAL STANDARD

You are not being asked to produce the most decorated interface.

You are not being asked to produce the most minimal interface.

You are not being asked to reproduce whatever website aesthetic is currently popular.

You are being asked to demonstrate design judgment.

Understand the product.

Make deliberate decisions.

Establish a coherent composition.

Use imagery with purpose.

Control typography.

Control color.

Respect spacing.

Avoid unnecessary containers.

Do not decorate empty space.

Do not repeat patterns merely because they are convenient.

Do not substitute generic AI design conventions for genuine visual thinking.

Do not force the user to repeatedly correct decisions already covered by this document.

The absence of an instruction does not authorize a bad design decision.

Do not make the user fight the interface you create.

Every element must earn its place. Every decision must have a reason. The complete interface must work as one coherent design.

This is the standard. Follow it throughout the entire task.
