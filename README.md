
<div align="center">
  
# ⚠️ Fork Notice

This is a fork of [oatear/cider](https://github.com/oatear/cider).

This version includes custom modifications and is intended for personal use and experimentation.

Please support the original project:
👉 https://github.com/oatear/cider


---

<img src="cider-app/src/assets/cider-logo-512.png" alt="Oatear Cider Logo" width="150">

# Froznar Cider

### The Data-Driven Card Design Studio for Game Developers

Design beautiful game cards with the power and familiarity of `HTML`, `CSS`, and `Handlebars`. Oatear Cider is a modern IDE for card game creation, bridging the gap between simple editors and complex professional software.

</div>

---

## About Froznar Cider

Cider was created for designers who want the ultimate creative freedom without a steep learning curve. Instead of a restrictive graphical editor, Cider uses the tools you already know:

- **Structure with HTML:** Define the layout of your cards with standard HTML.
- **Style with CSS:** Apply rich styling, from fonts and colors to complex layouts like CSS Grid.
- **Add Logic with Handlebars:** Use data from a spreadsheet to dynamically change names, stats, and abilities.


## Core Features

| Feature                         | Description                                                                                                                                                                       |
| :------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Powerful Templates**       | Create reusable card templates with HTML & CSS. The Template Wizard helps you quickly set up standard card sizes and layouts.                                                     |
| **2. Data-Driven Design**       | Separate your design from your content. Manage all card attributes in a simple, spreadsheet-like interface. Change data in one place, and update hundreds of cards instantly.     |
| **3. Live Preview**             | See your cards update in real-time as you edit your templates or data. No more guessing how your changes will look.                                                               |
| **4. Built-in Simulator**       | Instantly playtest your game in the **Game Simulator**—shuffle, draw, and discard without printing a thing. The **Asset Generator** helps you create placeholder art and symbols. |
| **5. Pro-Grade Exports**        | Export cards as PNGs or print-ready PDF sheets with crop marks and low-ink modes. You can also export for virtual tabletops like Tabletop Simulator.                              |
| **6. Your Project, Your Files** | The desktop app saves your project as a clean folder of `.html`, `.css`, and `.csv` files. Use Git, VS Code, or any other tool in your existing workflow.                         |


## Start the proyect

To start using the Web App, run it localy

  ```bash
  # Clone the repository
  git clone https://github.com/ParacelsoSIlphs/cider.git
  cd cider/cider-app

  # Install dependencies
  npm install

  # Run the app in development mode
  npm start
  ```

---

## Custom Helpers

This fork introduces additional helpers designed to support custom card systems and more flexible effect rendering.

---

> ## ⚙️ `parseText` — Icons, Numbers & Highlights
> 
> The `parseText` helper allows you to transform plain text into rich, styled content by automatically parsing:
>
> - Icons  
> - Numbers associated with icons  
> - Highlighted effects  
>
> ---
>
> ### Usage
>
>```handlebars
>{{{parseText card.description}}}
>```
>
>---
>
>### How it works
>
>#### Icons
>
>Icons are resolved automatically based on a naming convention:
>
>```
>codeword → damage  
>resource → icon-damage
>```
>
> The helper will look for the corresponding asset using the codeword.
>
>---
>
>#### Icon + Number
>
>To associate a number with an icon, use the `:` syntax:
>
>```
>damage:2
>```
>
>Output:
>```
>2 ⚔️
>```
>
>This is commonly used for effects like damage, draw, cost, etc.
>
>---
>
>#### Highlighted Elements
>
>Wrap a keyword in brackets to highlight it:
>
>```
>[cursed]
>```
>
>This will render the icon inside a highlight container.
>
>---
>
>### Styling (CSS Control)
>
>Each parsed element includes specific classes so you can fully customize the appearance:
>
>```css
>.parse-text       /* Container for number + icon */
>.parse-icon       /* All icons */
>.parse-num        /* Numbers */
>.parse-highlight  /* Highlighted elements */
>```
>
> You can override these classes in the CSS editor to match your game’s visual style.
>
>---
>
>### Example
>
>#### Input
>
>```text
>This card deals damage:2 to your opponent, then draw card:1. Your opponent is now [cursed]
>```
>
>---
>
>#### Output (HTML)
>
>```html
>This card deals
><span class="parse-text">
>  <span class="parse-num">2</span>
>  <img class="parse-icon" src=".../icon-damage" />
></span>
>to your opponent, then draw
><span class="parse-text">
>  <span class="parse-num">1</span>
>  <img class="parse-icon" src=".../icon-card" />
></span>.
>Your opponent is now
><span class="parse-highlight">
>  <img class="parse-icon" src=".../icon-cursed" />
></span>
>```
>
>---
>
>### Notes
>
>- The system is fully driven by naming conventions (no dictionary required)
>- Supports both inline icons (`life`) and structured effects (`damage:2`)
>- Designed for extensibility in card-based systems
---

## Creative Ownership & Licensing

Anything you create with Froznar Cider is your intellectual property. The app collects no data and all your work remains on your local device.

The application source code is protected by the **[AGPL-3.0 License]** to ensure it remains open-source forever.
