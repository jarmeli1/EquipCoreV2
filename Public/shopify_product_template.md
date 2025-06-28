# 🛠️ Shopify Product YAML Template
# -------------------------------------------------
# Copy this entire block for each product you add, then replace the placeholder values.
# The structure is optimized for an LLM (or developer) to transform it directly into
# Shopify Product JSON, Liquid sections, or migration CSVs.
# -------------------------------------------------

product:
  # Basic identifiers
  name: "<Product Display Name>"            # e.g., "Knee Rehab Slide Board"
  short_handle: "<knee-slide-board>"        # lowercase, hyphenated handle
  sku: "<SKU123>"                           # base SKU; variant SKUs auto‑inherit if not set
  type: "simple"                            # simple | bundle | variant‑parent
  parent_sku: "<SKU-PARENT>"                # leave blank unless this item belongs to a bundle/kit

  # Pricing
  price:
    retail: 0.00                            # USD retail price
    compare_at: 0.00                        # Optional strikethrough price
    cost: 0.00                              # Optional landed cost for margin tracking

  # Variants & Options
  variants:
    # List each option and its possible values. Duplicate the whole product block if variants are complex.
    - option_name: "Size"
      values: ["S", "M", "L"]
    - option_name: "Color"
      values: ["Blue", "Black"]

  # Descriptions & Selling Points
  description_md: |
    ## Overview
    Replace **this markdown** with a persuasive overview. Aim for 2–3 short paragraphs.

  highlights:
    - "Key benefit #1 (max 80 chars)"
    - "Key benefit #2"
    - "Key benefit #3"

  # Specs & Materials
  specs:
    dimensions_in:
      length: 0    # inches
      width: 0
      height: 0
    weight_lb: 0.0
    materials: "<ABS Plastic, EVA Foam>"
    warranty_months: 12

  # Compliance & Safety
  compliance:
    regulated: false                     # true if FDA‑registered, Prop‑65, etc.
    hazard_classification: ""            # e.g., UN3481 for batteries
    disclaimers_md: ""                  # any medical/legal disclaimers

  # Shipping Details
  shipping:
    ships_from: "Chagrin Falls, OH, USA"
    packaged_dimensions_in:
      length: 0
      width: 0
      height: 0
    packaged_weight_lb: 0.0

  # Media Assets
  media:
    main_image: "<main.jpg>"              # file name or URL
    gallery:
      - "<alt1.jpg>"
      - "<alt2.jpg>"

  # SEO Metadata
  seo:
    title: "<SEO Title – ~60 chars>"
    meta_description: "<Meta description – ~155 chars>"
    keywords: ["keyword1", "keyword2"]

  # Merchandising
  tags: ["Knee Rehab", "Physical Therapy"]
  cross_sell_handles: ["yoga-strap"]
  upsell_handles: ["knee-rehab-kit"]

# -------------------------------------------------
# End of template – duplicate from "product:" downward for each SKU.


# 🧩 Example Product (filled)
product:
  name: "Knee Rehab Slide Board"
  short_handle: "knee-rehab-slide-board"
  sku: "KR-SB-001"
  type: "simple"
  parent_sku: ""

  price:
    retail: 39.99
    compare_at: 49.99
    cost: 12.50

  variants: []

  description_md: |
    ## Overview
    The Knee Rehab Slide Board is a low‑friction exercise platform designed to restore knee range of motion after surgery. Light, portable, and wide enough for tall patients, it replaces bulky clinic equipment at home.

  highlights:
    - "Restores knee flexion and extension safely at home"
    - "Non‑slip foam bottom protects floors"
    - "Weighs under 2 lb—travel‑friendly"

  specs:
    dimensions_in:
      length: 30
      width: 12
      height: 0.5
    weight_lb: 1.8
    materials: "ABS Plastic, EVA Foam"
    warranty_months: 12

  compliance:
    regulated: false
    hazard_classification: ""
    disclaimers_md: ""

  shipping:
    ships_from: "Chagrin Falls, OH, USA"
    packaged_dimensions_in:
      length: 32
      width: 13
      height: 2
    packaged_weight_lb: 2.4

  media:
    main_image: "knee-slide-board-main.jpg"
    gallery:
      - "knee-slide-board-angle.jpg"
      - "knee-slide-board-feet.jpg"

  seo:
    title: "Knee Rehab Slide Board for Post‑Op Home Exercise"
    meta_description: "Lightweight slide board engineered by PTs to restore knee ROM after surgery—durable ABS, EVA grip, 30‑inch length."
    keywords: ["knee rehab slide board", "home physical therapy"]

  tags: ["Knee Rehab", "Slide Board", "Home Exercise"]
  cross_sell_handles: ["yoga-strap"]
  upsell_handles: ["knee-rehab-kit"]

# ----- End Example -----

# 🧩 TPE Resistance Loop Band Set (filled)
product:
  name: "TPE Resistance Loop Band Set – 5 Levels"
  short_handle: "tpe-resistance-loop-band-set"
  sku: "RB-TPE-SET-001"
  type: "simple"
  parent_sku: ""

  price:
    retail: 14.99
    compare_at: 19.99
    cost: 4.50

  variants: []

  description_md: |
    ## Overview
    This latex‑free TPE loop band set delivers five calibrated resistance levels (4‑30 lb) for rehab, yoga, and strength training. Each 24‑in (600 mm) band is color‑coded and odor‑free, offering smoother elasticity than traditional latex loops and lasting up to 10,000 stretch cycles without rolling or snapping.

  highlights:
    - "Latex‑free eco‑friendly TPE construction"
    - "Five color‑coded levels: 4‑30 lb"
    - "600 mm × 50 mm universal size"

  specs:
    dimensions_in:
      length: 23.6
      width: 2
      height: 0.04   # average thickness in inches (~1 mm)
    weight_lb: 0.25  # set of five bands
    materials: "Thermoplastic Elastomer (TPE)"
    warranty_months: 12

  compliance:
    regulated: false
    hazard_classification: ""
    disclaimers_md: "Latex‑free. Consult a healthcare professional before use if recovering from injury."

  shipping:
    ships_from: "Chagrin Falls, OH, USA"
    packaged_dimensions_in:
      length: 8
      width: 6
      height: 1
    packaged_weight_lb: 0.35

  media:
    main_image: "tpe-loop-band-main.jpg"
    gallery:
      - "tpe-loop-band-set.jpg"
      - "tpe-loop-band‑usage.jpg"

  seo:
    title: "Latex‑Free TPE Resistance Loop Bands – Set of 5 Levels"
    meta_description: "Eco‑friendly TPE resistance loop bands, color‑coded 4–30 lb. Ideal for rehab, yoga & strength workouts. Latex‑free and odorless."
    keywords: ["TPE resistance band", "loop exercise band", "latex free fitness band"]

  tags: ["Resistance Band", "TPE", "Latex Free", "Home Exercise"]
  cross_sell_handles: ["knee-rehab-slide-board"]
  upsell_handles: ["knee-rehab-kit"]

# ----- End TPE Band Set -----

# 🧩 Natural Latex Resistance Tube Set with Handles (filled)
product:
  name: "Natural Latex Resistance Tube Set – 5 Levels"
  short_handle: "latex-resistance-tube-set"
  sku: "RB-LATEX-TUBE-SET-001"
  type: "simple"
  parent_sku: ""

  price:
    retail: 21.99
    compare_at: 29.99
    cost: 7.00

  variants: []

  description_md: |
    ## Overview
    Crafted from **100 % natural latex tubing**, this compact resistance band set delivers five progressive tension levels—from 10 lb (yellow) up to 50 lb (red)—perfect for strength training, mobility work, and post‑injury rehab. Each 48‑inch tube clips to foam‑padded handles or the included door anchor so you can perform rows, presses, and leg exercises anywhere.

  highlights:
    - "Five color‑coded tubes: 10–50 lb"
    - "100 % natural latex for high resilience"
    - "Includes handles, door anchor & ankle straps"

  specs:
    dimensions_in:
      length: 48       # tube length (stretched ≈ 10 ft)
      width: 0.5       # tube outer diameter in inches
      height: 0.5
    weight_lb: 1.4     # full set with accessories
    materials: "Natural Latex Rubber, Nylon Straps, EVA Foam Handles"
    warranty_months: 12

  compliance:
    regulated: false
    hazard_classification: ""
    disclaimers_md: "Consult a healthcare professional before use if recovering from injury. Contains natural latex—may cause allergic reaction."

  shipping:
    ships_from: "Chagrin Falls, OH, USA"
    packaged_dimensions_in:
      length: 9
      width: 6
      height: 3
    packaged_weight_lb: 1.7

  media:
    main_image: "latex-tube-set-main.jpg"
    gallery:
      - "latex-tube-set-components.jpg"
      - "latex-tube-set-exercises.jpg"

  seo:
    title: "Natural Latex Resistance Tube Set with Handles – 5 Color Levels"
    meta_description: "Adjustable 10‑50 lb natural latex resistance tube set with handles, door anchor & ankle straps. Full‑body workouts and rehab."
    keywords: ["latex resistance tube", "exercise tube set", "fitness bands with handles"]

  tags: ["Resistance Band", "Latex", "Handles", "Home Exercise"]
  cross_sell_handles: ["tpe-resistance-loop-band-set"]
  upsell_handles: ["knee-rehab-kit"]

# ----- End Latex Tube Set -----

# 🧩 Heavy Duty Nylon Webbing Door Anchor (filled)
product:
  name: "Heavy Duty Nylon Webbing Door Anchor"
  short_handle: "heavy-duty-door-anchor"
  sku: "RB-DOOR-ANCHOR-001"
  type: "simple"
  parent_sku: ""

  price:
    retail: 6.99
    compare_at: 9.99
    cost: 2.00

  variants: []

  description_md: |
    ## Overview
    Secure any resistance band to a closed door without scuffs or dents. This heavy‑duty anchor uses **1000 D nylon webbing** and an oversized foam stopper (3 in Ø × 1.5 in thick) to spread force evenly—rated to withstand band tensions up to **300 lb**.

  highlights:
    - "3‑inch soft foam stopper protects door paint"
    - "1000 D nylon strap rated 300 lb"
    - "Universal fit for tubes, loops & TRX straps"

  specs:
    dimensions_in:
      length: 10      # total length per Wavar spec (7" strap + 3" stopper)
      width: 2        # approximate strap width
      height: 1.5     # stopper thickness
    weight_lb: 0.15   # ≈ 68 g
    materials: "Nylon Webbing, EVA Foam"
    warranty_months: 12

  compliance:
    regulated: false
    hazard_classification: ""
    disclaimers_md: "Ensure door is fully closed and locked before each use. Not for overhead suspension of persons."

  shipping:
    ships_from: "Chagrin Falls, OH, USA"
    packaged_dimensions_in:
      length: 5
      width: 4
      height: 2
    packaged_weight_lb: 0.2

  media:
    main_image: "door-anchor-main.jpg"
    gallery:
      - "door-anchor-side.jpg"
      - "door-anchor-usage.jpg"

  seo:
    title: "Heavy Duty Door Anchor for Resistance Bands – Nylon & Foam Stopper"
    meta_description: "Protect your doors while anchoring resistance bands up to 300 lb with this 1000 D nylon strap and 3‑inch foam stopper."
    keywords: ["door anchor resistance bands", "nylon webbing band anchor", "home gym accessory"]

  tags: ["Door Anchor", "Resistance Band", "Accessory", "Home Exercise"]
  cross_sell_handles: ["latex-resistance-tube-set"]
  upsell_handles: ["knee-rehab-kit"]

# ----- End Door Anchor -----

# 🧩 Mini Pilates Ball 25 cm (filled)
product:
  name: "Mini Pilates Ball 25 cm – Anti‑Burst PVC"
  short_handle: "mini-pilates-ball-25cm"
  sku: "YB-PILATES-25CM-001"
  type: "simple"
  parent_sku: ""

  price:
    retail: 8.99
    compare_at: 12.99
    cost: 3.00

  variants:
    - option_name: "Color"
      values: ["Blue", "Pink", "Purple"]

  description_md: |
    ## Overview
    Elevate core workouts, barre routines, and physical‑therapy drills with this **25 cm (9‑inch) mini Pilates ball**. Crafted from gym‑grade anti‑burst PVC, it supports up to **330 lb (150 kg)** while maintaining a soft, grippy surface that won’t slide on mats. Deflates flat for travel and reinflates in seconds with the included straw and plug.

  highlights:
    - "25 cm (9 in) anti‑burst PVC design"
    - "Supports users up to 330 lb"
    - "Includes straw & plug for quick inflation"

  specs:
    dimensions_in:
      length: 9.8
      width: 9.8
      height: 9.8
    weight_lb: 0.5   # ~0.23 kg
    materials: "Soft Anti‑Burst PVC"
    warranty_months: 12

  compliance:
    regulated: false
    hazard_classification: ""
    disclaimers_md: "Contains PVC. Keep away from sharp objects and direct heat sources."

  shipping:
    ships_from: "Chagrin Falls, OH, USA"
    packaged_dimensions_in:
      length: 6
      width: 5
      height: 2
    packaged_weight_lb: 0.6

  media:
    main_image: "mini-pilates-ball-main.jpg"
    gallery:
      - "mini-pilates-ball-blue.jpg"
      - "mini-pilates-ball-in-use.jpg"

  seo:
    title: "25 cm Mini Pilates Ball – Soft Anti‑Burst Core Trainer"
    meta_description: "9‑inch pilates ball supports 330 lb; non‑slip PVC for yoga, barre & rehab core work. Includes straw for easy inflation."
    keywords: ["pilates ball 25cm", "mini yoga ball", "core exercise ball"]

  tags: ["Pilates Ball", "Yoga", "Core", "Home Exercise"]
  cross_sell_handles: ["tpe-resistance-loop-band-set"]
  upsell_handles: ["knee-rehab-kit"]

# ----- End Pilates Ball -----

# 🧩 Yoga Stretch Strap with 10 Loops (filled)
product:
  name: "Yoga Stretch Strap with 10 Loops – Non‑Elastic Nylon"
  short_handle: "yoga-stretch-strap-10-loops"
  sku: "YS-10LOOP-001"
  type: "simple"
  parent_sku: ""

  price:
    retail: 7.99
    compare_at: 9.99
    cost: 2.50

  variants:
    - option_name: "Color"
      values: ["Black", "Green", "Purple"]

  description_md: |
    ## Overview
    Deepen stretches safely and track progress with this **non‑elastic yoga strap** featuring **10 numbered loops**. The tightly‑woven nylon webbing resists fraying and supports assisted stretching for hamstrings, quads, shoulders, and hips. At **75 in × 1 in** (190 cm × 2.5 cm), it suits practitioners of all heights and folds down flat in any gym bag.

  highlights:
    - "75‑inch strap with 10 numbered loops"
    - "Durable, washable nylon—no elastic snap risk"
    - "Improves flexibility for yoga, PT & dance"

  specs:
    dimensions_in:
      length: 75
      width: 1
      height: 0.04
    weight_lb: 0.25   # ≈ 0.11–0.2 kg range
    materials: "Woven Nylon"
    warranty_months: 12

  compliance:
    regulated: false
    hazard_classification: ""
    disclaimers_md: "Consult a healthcare professional before beginning a new stretching program."

  shipping:
    ships_from: "Chagrin Falls, OH, USA"
    packaged_dimensions_in:
      length: 10.7
      width: 10.2
      height: 0.6
    packaged_weight_lb: 0.44

  media:
    main_image: "yoga-strap-main.jpg"
    gallery:
      - "yoga-strap-loops.jpg"
      - "yoga-strap-in-use.jpg"

  seo:
    title: "Non‑Elastic Yoga Stretch Strap – 10 Loop Flexibility Trainer"
    meta_description: "75″ nylon yoga strap with 10 numbered loops for assisted stretching & physical therapy. Durable, washable, non‑elastic design."
    keywords: ["yoga stretch strap", "10 loop stretching band", "non elastic flexibility strap"]

  tags: ["Yoga Strap", "Stretching", "Physical Therapy", "Accessory"]
  cross_sell_handles: ["mini-pilates-ball-25cm"]
  upsell_handles: ["knee-rehab-kit"]

# ----- End Yoga Strap -----






