# 🎨 Animationsoversigt - Højskolendk

## Implementerede Animationstyper

### 1. **Bitmap-baseret Grafik** 🎮

- **Particle System**: Canvas-baseret particle effekt med orange farvetema
  - 50 partikler der bevæger sig langsomt
  - Pixel-perfect rendering (bitmap-stil)
  - Forbindelseslinjer mellem nære partikler
  - Transparens og blanding med baggrund
- **Gradient Orbs**: Animerede baggrundselementer
  - Floating orange orb i top højre
  - Pulserende orb i bund venstre
  - Blur effekt for blødt udtryk

### 2. **Entrance Animations** 🚪

Elementer kommer ind når siden loader eller scrolles i syne:

- **Fade Up**: Sektioner fader op fra bunden
- **Scale In**: GIF-sektionen skalerer ind
- **Stagger Effect**: Elementer kommer ind med forsinkelse
  - Price cards: 150ms delay mellem hver
  - Sustainability items: 200ms delay mellem hver
  - Stribes i TripIntro: 50ms stagger

### 3. **InView Animations** 👁️

Intersection Observer tracker når elementer kommer i viewport:

**DatesPrices Component:**

- Alle 4 kort animeres ind når sektionen bliver synlig
- Staggered timing (0ms, 150ms, 300ms, 450ms)
- Slide in + scale effekt

**Sustainability Component:**

- 3 organisationslogoer floater ind
- Hver med individuel delay
- Hover float animation på logoer

**TripIntro Component:**

- 19 orange stribes vokser fra top til bund
- Location items slide ind fra venstre
- Staggered med 100ms delay

### 4. **Timeline Animation** ⏱️

**Billedkarussel i TripIntro:**

- Automatisk skift hver 2. sekund
- Transition effekter:
  - Opacity flash overlay (#ff5900)
  - Scale + brightness boost under transition
  - Smooth fade mellem billeder

**Tab Navigation i TripProgram:**

- Animated tab indicator bevæger sig
- Smooth transition mellem tabs
- Content fade in/out med opacity
- 250ms delay mellem fade-out og fade-in

### 5. **InView & Return Animation** 🔄

**Scroll Progress Bar:**

- Fixed position bar i toppen
- Real-time progress under scroll
- Gradient farve (primary → orange-400)
- Glow effekt med box-shadow

**Parallax Effekt:**

- Alle sektioner bevæger sig langsomt under scroll
- Speed factor: 0.02 (meget subtil)
- Kun aktiv når sektionen er synlig

### 6. **Hover Micro-interactions** 🎯

**Buttons:**

- Scale up (1.05) ved hover
- Ripple effekt ved klik
- Shadow glow på primary buttons
- Smooth cubic-bezier transitions

**Price Cards:**

- Hover: Scale 1.02 + shadow
- Smooth 500ms transition
- Button pulse animation

**Sustainability Logos:**

- Lift up 5px + rotate 2deg
- Kontinuerlig float animation ved hover
- Grayscale transition

**Tab Buttons:**

- Ripple effekt ved hover/klik
- Smooth opacity transitions
- Active state indicator

### 7. **Specielle Effekter** ✨

**CTA Buttons i TripIntro:**

- Expanding circle effekt ved hover
- Pulse animation ved active
- Scale + shadow på hover

**Tab Content:**

- Fade in animation når tab aktiveres
- Image zoom ved hover over content
- Smooth opacity transitions

**Stribes:**

- Individual grow animation fra top
- ScaleY transform-origin
- Cascading stagger effekt

## 🎨 Kreative Greb

### 1. **Bitmap Æstetik**

- Pixel-perfect canvas rendering
- Scanline overlay effekt tilgængelig
- Crisp-edges på billeder (kan aktiveres)

### 2. **Orange Farvetema**

- Konsekvent brug af #ff5900
- Gradient variations (orange-400, orange-600)
- Transparente overlays med orange

### 3. **Smooth Performance**

- Hardware-accelerated transforms
- RequestAnimationFrame for canvas
- Intersection Observer for lazy animations
- Reduced motion support

### 4. **UI Feedback**

- Scroll progress giver visuelt feedback
- Hover states på alle interaktive elementer
- Loading states med smooth transitions
- Visual cues gennem animationer

## 📱 Responsive Considerations

- Complex animations deaktiveret på mobile
- Parallax slået fra på små skærme
- Reduced particle count muligt
- Prefers-reduced-motion respekteret

## 🎭 Animation Timing

- **Fast**: 300ms (hover effects)
- **Medium**: 500-600ms (cards, buttons)
- **Slow**: 800ms (sections, entrance)
- **Very Slow**: 2-3s (infinite loops)

## 🚀 Performance Features

- Canvas optimeret med clear/redraw
- Transforms i stedet for position
- Will-change hints hvor nødvendigt
- Debounced scroll handlers
- Lazy intersection observers

## 💡 Anvendelse

Alle animationer er nu aktive på `singleview.astro`:

- Åbn http://localhost:4321/singleview
- Scroll ned for at se InView animations
- Hover over elementer for micro-interactions
- Observer scroll progress bar i toppen
- Bemærk baggrunds particles og orbs

## 📝 Yderligere Animationsklasser

Se `src/styles/animations.css` for:

- 15+ keyframe animations
- Utility classes (.animate-\*)
- Hover effect classes (.hover-\*)
- Bitmap/pixel effects
- Text animations
- Loading spinners
