# Development Plan: seal.codes.pitchdeck (default branch)

*Generated on 2025-06-28 by Vibe Feature MCP*
*Workflow: epcc*

## Goal
Create a compelling Slidev-based pitch deck for a software product that effectively communicates value proposition, features, and business opportunity to the target audience.

## Explore
### Tasks
- [x] Understand the software product and its core value proposition
- [x] Identify target audience and pitch objectives
- [x] Gather existing branding and visual assets
- [x] Define presentation requirements (length, format, interactivity)
- [x] Research Slidev capabilities and best practices for pitch decks
- [x] Determine content structure and key messaging strategy
- [x] Establish design preferences and visual direction

### Completed
- [x] Created development plan file
- [x] Set up phase entrance criteria
- [x] Analyzed seal.codes repository and documentation
- [x] Reviewed existing slides.md draft
- [x] Studied STORYBOOK.md for video concept insights
- [x] Researched Slidev framework capabilities and features
- [x] Catalogued available visual assets in public folder
- [x] Finalized presentation requirements and constraints

## Plan

### Phase Entrance Criteria:
- [x] The software product and its key features have been thoroughly understood
- [x] Target audience and pitch objectives have been identified
- [x] Slidev framework capabilities and requirements have been explored
- [x] Content structure and key messaging have been defined
- [x] Design preferences and visual requirements have been gathered

### Tasks
- [x] Design slide-by-slide structure and narrative flow
- [x] Map existing assets to specific slides
- [x] Create detailed content outline with key messages
- [x] Define speaker notes framework for each slide
- [x] Identify additional visual assets needed (with LLM prompts)
- [x] Plan Slidev layouts and components for each slide
- [x] Design custom styling and theme approach
- [x] Create implementation timeline and dependencies
- [x] Finalize technical specifications and requirements

### Completed
- [x] Created 15-slide narrative structure following trust crisis → solution → impact arc
- [x] Mapped all existing assets from public folder to specific slides
- [x] Identified 4 additional images needed with LLM generation prompts
- [x] Designed slide timing for 8-minute presentation (30-40 seconds per slide)
- [x] Developed comprehensive speaker notes framework (total ~8 minutes)
- [x] Planned Slidev layout strategy (cover, image-right, image-left)
- [x] Designed custom styling approach with seal.codes branding
- [x] Created implementation timeline with dependencies and priorities
- [x] Defined technical specifications for Slidev configuration

## Code

### Phase Entrance Criteria:
- [x] Detailed slide structure and content outline has been created
- [x] Slidev setup and configuration approach has been planned
- [x] Visual design system and theme choices have been decided
- [x] Content for each slide has been prepared or sourced
- [x] Technical implementation approach has been documented

### Tasks
- [x] Set up Slidev project structure and configuration
- [x] Create custom theme and styling system
- [x] Implement slides 1-5 (Problem setup: Title, Trust, Ancient, Chaos, Creator)
- [x] Implement slides 6-10 (Solution: Buyer, Expert's Curse, Digital Seals, How It Works, Verification)
- [x] Implement slides 11-15 (Impact: Sarah's Success, Alex's Confidence, Innovation, Vision, CTA)
- [x] Integrate existing assets and optimize images
- [x] Generate missing images using LLM prompts (documented in LLM_IMAGE_PROMPTS.md)
- [x] Configure presenter mode and speaker notes
- [x] Fix video background implementation for slides 2 and 3
- [x] Create custom character layout with polaroid-style portraits
- [x] Fix HTML rendering issues by removing blank lines within HTML code
- [x] Simplify complex HTML structures to use Markdown and UnoCSS
- [x] Standardize body text font sizes for consistency
- [x] Make text more prominent and readable
- [x] Replace emojis with Lucide icons throughout presentation
- [x] Create reusable VideoBackground component for video slides
- [x] Fix Vue template style block error by moving CSS to external files
- [ ] Test and refine styling and transitions
- [ ] Final quality assurance and optimization

### Completed
- [x] Created complete Slidev presentation with 15 slides
- [x] Implemented custom styling with seal.codes branding
- [x] Integrated all existing assets from public folder
- [x] Added comprehensive speaker notes for 8-minute presentation
- [x] Set up responsive layouts (cover, image-left, image-right)
- [x] Applied modern typography and color scheme
- [x] Created package.json with proper Slidev configuration
- [x] Generated LLM prompts for 4 missing images
- [x] Created comprehensive README with usage instructions
- [x] Installed and tested Slidev dependencies
- [x] Fixed video background syntax using Slidev background property
- [x] Implemented polaroid-style character portraits in bottom right corner
- [x] Researched Slidev syntax guide for proper HTML/Vue usage
- [x] CRITICAL FIX: Removed all blank lines within HTML code structures
- [x] Fixed HTML rendering issues across all slides by eliminating whitespace
- [x] Installed Lucide icons package (@iconify-json/lucide)
- [x] VISUAL IMPROVEMENTS: Standardized font sizes (text-xl, text-2xl, text-3xl)
- [x] Enhanced text prominence with larger, bolder typography
- [x] Replaced all emojis with professional Lucide icons
- [x] Improved spacing and visual hierarchy across all slides
- [x] VIDEO FIX: Created reusable VideoBackground.vue component
- [x] Fixed video background implementation using proper HTML video elements
- [x] Removed video looping as requested by user
- [x] STYLE FIX: Moved CSS from slides.md to external style.css file
- [x] Created setup/main.ts to properly import custom styles
- [x] Resolved Vue template style block error
- [x] VIDEO ENHANCEMENT: Added video restart functionality using Slidev onSlideEnter hook
- [x] Implemented proper Slidev slide lifecycle hooks instead of Vue lifecycle hooks
- [x] COMPONENT REFACTORING: Created reusable DilemmaStory component
- [x] Updated CreatorDilemmaStory to use the reusable component
- [x] Created BuyerDilemmaStory component with Alex's story
- [x] Implemented click-to-reveal functionality for both dilemma stories
- [x] Added proper image references (anonymous.png, alex-portrait-frustrated.png)

## Commit

### Phase Entrance Criteria:
- [ ] All slides have been implemented and are functional
- [ ] Content is complete and properly formatted
- [ ] Visual design is polished and professional
- [ ] Presentation flows smoothly and tells a compelling story
- [ ] Technical implementation is clean and maintainable

### Tasks
- [ ] *To be added when this phase becomes active*

### Completed
*None yet*

## Key Decisions
- **Target Audience**: Hackathon judges evaluating innovation and utility
- **Presentation Goal**: Showcase why seal.codes is incredibly useful and innovative
- **Duration**: Maximum 8 minutes (15 slides, 30-40 seconds each)
- **Design Direction**: Modern, adapted from seal.codes branding, full-page visuals with minimal text
- **Content Strategy**: Focus on visual storytelling with verbose speaker notes
- **Slidev Features**: Leverage layouts (cover, image-left, image-right), components, and presenter mode
- **Narrative Arc**: Trust crisis → Ancient wisdom → Modern solution → Transformative impact
- **Presentation Format**: Static slides with optional full-page video integration
- **Asset Strategy**: Use existing assets from public folder + 4 additional LLM-generated images
- **Layout Strategy**: Cover (11 slides), Image-right (4 slides), Image-left (1 slide)
- **Styling Approach**: Custom theme based on seal.codes branding with modern typography

## Notes
**DETAILED SLIDE STRUCTURE:**

**Slide 1: Title/Cover** - Layout: cover, Asset: logo.svg + generated background
**Slide 2: Foundation of Trust** - Layout: cover, Asset: people-shaking-hands.mp4
**Slide 3: Ancient Wisdom** - Layout: cover, Asset: King applying a seal.mp4
**Slide 4: Digital Chaos** - Layout: cover, Asset: digital-uncertainty.png
**Slide 5: Creator's Dilemma** - Layout: image-right, Assets: sarah-portrait.png + social-media-unauthorized-copy.png
**Slide 6: Buyer's Gamble** - Layout: image-right, Assets: alex-portrait.png + two-advertisements-with-and-without-seld-code.png
**Slide 7: Expert's Curse** - Layout: cover, Asset: [LLM PROMPT: Complex cryptographic network visualization]
**Slide 8: Digital Seals Solution** - Layout: cover, Asset: [LLM PROMPT: Seal transformation concept]
**Slide 9: How It Works** - Layout: image-left, Asset: screenshot-seal-document.png
**Slide 10: Verification Result** - Layout: image-right, Assets: screenshot-verified.png + screenshot-verified-details.png
**Slide 11: Sarah's Success** - Layout: image-right, Assets: sarah-portrait.png + screenshot-sealed-document.png
**Slide 12: Alex's Confidence** - Layout: image-right, Asset: alex-portrait.png + verification visual
**Slide 13: Innovation Showcase** - Layout: cover, Asset: [LLM PROMPT: AI development metrics visualization]
**Slide 14: The Vision** - Layout: cover, Asset: [LLM PROMPT: Global trust network visualization]
**Slide 15: Call to Action** - Layout: cover, Asset: logo.svg + clean background

**LLM PROMPTS FOR ADDITIONAL IMAGES:**
1. "Abstract visualization of complex cryptographic network with PKI certificates, keys, and technical diagrams, dark tech aesthetic, overwhelming complexity"
2. "Elegant transformation from ancient wax seal to modern QR code, morphing animation concept, clean modern design"
3. "Modern development dashboard showing AI collaboration metrics, code generation statistics, innovation visualization, tech aesthetic"
4. "Global network visualization showing connected trust relationships, digital seals spreading across the world, hopeful and expansive"

**Product Understanding:**
- seal.codes creates QR code attestations that serve as digital seals for documents
- Links documents to social identities (Google, GitHub) without complex PKI
- Solves the problem of digital content authenticity in an accessible way
- Built with 88% AI assistance using bolt.new - demonstrates innovation

**Technical Insights:**
- Hackathon project showcasing genuine innovation vs. typical clones
- Bridges ancient trust concepts (seals) with modern technology (QR codes, social auth)
- Privacy-first: documents never leave user's device, only hashes processed
- Multiple document types supported (PDF, images) with format-specific embedding

**Presentation Requirements:**
- Audience: Hackathon judges
- Goal: Demonstrate incredible utility and innovation
- Duration: Maximum 8 minutes
- Style: Modern, visual-heavy with minimal slide text
- Format: Static presentation with optional full-page video integration
- Assets: Available in public folder + additional images described as LLM prompts

**Available Assets Identified:**
- Logo and branding (logo.svg)
- Character portraits (sarah-portrait.png, alex-portrait.png)
- Product screenshots (screenshot-seal-document.png, screenshot-verified.png, etc.)
- Conceptual visuals (wax-seal.png, handshake.png, digital-uncertainty.png)
- Video assets (people-shaking-hands.mp4, King applying a seal.mp4)
- Use case illustrations (two-advertisements-with-and-without-seld-code.png)

**Slidev Capabilities Identified:**
- Rich layout system (cover, image-left, image-right, etc.)
- Built-in components and animations
- Presenter mode with speaker notes
- Custom styling and theming
- Interactive elements and Vue components
- Video integration support

---
*This plan is maintained by the LLM. Tool responses provide guidance on which section to focus on and what tasks to work on.*
