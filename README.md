# seal.codes Hackathon Pitch Deck

A compelling 8-minute presentation showcasing seal.codes - Digital Seals for the Modern Age.

## 🎯 Presentation Overview

- **Duration**: 8 minutes (15 slides, ~30-40 seconds each)
- **Audience**: Hackathon judges
- **Goal**: Showcase innovation and incredible utility of seal.codes
- **Format**: Visual-heavy slides with comprehensive speaker notes

## 🚀 Quick Start

### Prerequisites
- Node.js (v16 or higher)
- npm, yarn, or pnpm

### Installation & Development

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Open http://localhost:3030
```

### Presenter Mode

```bash
# Start with presenter mode
npm run dev

# Navigate to http://localhost:3030/presenter
# Or press 'p' during presentation
```

## 📁 File Structure

The presentation is organized into multiple files for better maintainability:

```
slides.md                 # Main configuration and slide imports
pages/
├── 01-title.md          # Title slide
├── 02-foundation-trust.md # Trust foundation (video)
├── 03-ancient-wisdom.md  # Ancient seals (video)
├── 04-digital-chaos.md   # Digital trust crisis
├── 05-creator-dilemma.md # Sarah's story
├── 06-buyer-gamble.md    # Alex's story
├── 07-expert-curse.md    # Existing solutions
├── 08-return-clarity.md  # Our approach
├── 09-how-it-works.md    # 3-step process
├── 10-verification-result.md # QR verification
├── 11-sarah-success.md   # Creator empowerment
├── 12-alex-confidence.md # Buyer protection
├── 13-innovation-showcase.md # AI development
├── 14-vision.md         # Global trust network
└── 15-call-to-action.md # Final message
```

## 📋 Slide Structure

1. **Title/Cover** - Introduction with logo
2. **Foundation of Trust** - Human interaction basics (video background)
3. **Ancient Wisdom** - Historical seals concept (video background)
4. **Digital Chaos** - The trust crisis in digital space
5. **Creator's Dilemma** - Sarah's story (stolen content)
6. **Buyer's Gamble** - Alex's marketplace uncertainty
7. **Expert's Curse** - Why existing solutions failed
8. **Digital Seals Solution** - Our elegant approach
9. **How It Works** - Simple 3-step process
10. **Verification Result** - QR code scanning demo
11. **Sarah's Success** - Creator empowerment
12. **Alex's Confidence** - Buyer protection
13. **Innovation Showcase** - 88% AI-built highlight
14. **The Vision** - Global trust network
15. **Call to Action** - Final message

## 🎨 Assets

### Available Assets (in `/public`)
- Logo and branding
- Character portraits (Sarah, Alex)
- Product screenshots
- Conceptual visuals
- Video backgrounds

### Missing Assets
See `LLM_IMAGE_PROMPTS.md` for prompts to generate:
- Complex cryptographic visualization
- Seal transformation concept
- AI development dashboard
- Global trust network

## 🎤 Speaker Notes

Each slide includes comprehensive speaker notes accessible in presenter mode. Total speaking time: ~8 minutes.

### Key Talking Points
- **Problem**: Digital trust crisis affecting creators and buyers
- **Solution**: QR code attestations linked to social identities
- **Innovation**: 88% AI-built, genuine innovation vs. clones
- **Impact**: Restoring trust through visible digital seals

## 🛠 Technical Details

- **Framework**: Slidev (Vue-based presentation framework)
- **Styling**: UnoCSS with custom seal.codes theme
- **Layouts**: Cover, image-left, image-right
- **Features**: Video backgrounds, presenter mode, export options
- **Organization**: Modular file structure for easy maintenance

## 📝 Editing Individual Slides

To edit a specific slide:

1. Navigate to the appropriate file in the `pages/` directory
2. Edit the content while maintaining the frontmatter structure
3. Speaker notes are in HTML comments `<!-- -->`
4. The presentation will auto-reload during development

## 🔄 Adding New Slides

1. Create a new file in `pages/` (e.g., `16-new-slide.md`)
2. Add the slide import to `slides.md`:
   ```markdown
   ---
   src: ./pages/16-new-slide.md
   ---
   ```

## 📤 Export Options

```bash
# Export to PDF
npm run export

# Build static site
npm run build

# Preview built site
npm run preview
```

## 🎯 Presentation Tips

1. **Timing**: Practice to stay within 8-minute limit
2. **Visuals**: Let images tell the story, minimal text reading
3. **Energy**: Emphasize the innovation and problem-solving aspects
4. **Demo**: Consider having seal.codes website ready for questions
5. **Backup**: Export PDF as backup presentation format

## 🔧 Customization

### Styling
- Main styles in `style.css`
- Color scheme based on seal.codes branding
- Responsive design for different screen sizes

### Content
- Edit slide content directly in individual page files
- Speaker notes in HTML comments `<!-- -->`
- Asset references use `/filename.ext` format

## 📊 Success Metrics

This presentation is designed to:
- ✅ Clearly explain the trust problem in digital space
- ✅ Demonstrate seal.codes as an elegant solution
- ✅ Highlight genuine innovation (88% AI-built)
- ✅ Show real-world impact for creators and buyers
- ✅ Inspire judges with the vision of restored digital trust

---

**seal.codes** - Add a seal. Share with confidence.