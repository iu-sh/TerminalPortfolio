# Terminal Portfolio Template

A customizable terminal-themed portfolio website. All content is loaded dynamically from a configuration file — just update `config.js` to make it your own!

## Quick Start

1. Download this repository
2. Edit `config.js` with your personal information
3. Open `index.html` directly in a browser — no server needed!

## 📁 File Structure

```
├── index.html        # Main HTML file (no need to edit)
├── script.js         # JavaScript logic (no need to edit)
├── style.css         # Styling (customize as needed)
├── config.js         # ⭐ YOUR CONTENT GOES HERE
├── favicon.ico       # Favicon (replace with your own)
└── README.md         # This file
```

## 📋 Configuration Structure (`config.js`)

The `config.js` file contains three main exports:
- `CONFIG` - All your personal information and settings
- `INTRO_ASCII` - ASCII art displayed on page load
- `ERROR_ASCII` - ASCII art displayed on command errors

### Meta Information

```javascript
meta: {
  title: "Your Name | Your Title",
  description: "SEO meta description for your portfolio",
  keywords: "comma, separated, keywords, for, seo",
  author: "Your Name",
  ogTitle: "Open Graph title for social sharing",
  ogDescription: "Open Graph description for social sharing",
  themeColor: "#0d1117"
}
```

### Terminal Configuration

```javascript
terminal: {
  title: "user@hostname: ~",           
  prompt: {
    symbol: "➜",                       
    directory: "~"                     
  },
  welcomeMessage: 'Hello! Type "<strong class="text-yellow">help</strong>" to see available commands.'
}
```

**Note:** The `welcomeMessage` can contain HTML for styling. Use classes like `text-yellow`, `text-green`, `text-blue`, `text-red`, `bold`, and `italic` for styling.

### Resume Download URL

```javascript
resumeDownloadUrl: "https://link-to-your-resume.pdf"
```

### About Section

```javascript
about: {
  name: "Your Full Name",
  alias: "nickname or handle",
  role: "Your Job Title",
  team: "Team or Department",
  tagline: "A short tagline about yourself",
  externalPortfolio: {
    label: "yoursite.com",
    url: "https://yoursite.com"
  },
  currentStatus: {
    role: "Current Role",
    location: "Current Company/Location"
  },
  recentWork: [
    {
      status: "CURRENT",                
      description: "What you're working on",
      location: "Company/Location"
    },
    {
      status: "COMPLETED",
      description: "Previous project",
      location: "Company/Location"
    }
  ],
  bio: "A longer bio paragraph about yourself..."
}
```

### Education Section

```javascript
education: [
  {
    institution: "University Name",
    degree: "Degree Type - Major",
    year: "2022",
    grade: "GPA: X.XX/4.0"
  }
]
```

You can add multiple education entries to the array.

### Projects Section

```javascript
projects: [
  {
    name: "Project Name",
    url: "https://project-link.com",      // can be null
    secondaryUrl: "https://optional-link.com",  // optional
    tags: ["Language1", "Tech1", "Tool1"],
    description: [
      "First bullet point describing the project",
      "Second bullet point with more details",
      "Third bullet point about impact/achievements"
    ]
  }
]
```

**Notes:**
- `url` can be `null` if no link is available
- `secondaryUrl` is optional, useful for projects with multiple links (e.g., "Project1 / Project2")
- `tags` is an array of technologies/tools used
- `description` is an array of bullet points

### Experience Section

```javascript
experience: [
  {
    title: "Company - Role or Team",
    period: "Start Date - End Date",
    department: "Department Name",
    highlights: [
      { label: "Category", detail: "Description of work" },
      { label: null, detail: "Description without a label" }
    ]
  }
]
```

**Notes:**
- `label` can be `null` for bullet points without a category prefix
- Add entries in reverse chronological order (most recent first)

### Skills Section

```javascript
skills: [
  {
    category: "Category Name",
    items: "Comma-separated list of skills in this category."
  }
]
```

### Achievements Section

```javascript
achievements: {
  asciiArt: `Multi-line ASCII art string
with achievements listed
on the right side`
}
```

**Note:** Use template literals (backticks) for multi-line strings.

### Contact Section

```javascript
contact: {
  email: {
    address: "your@email.com",
    label: "your@email.com"
  },
  internal: {
    url: "https://internal-profile-link",
    label: "Display text for link"
  }
}
```

### Book a Time Section

```javascript
bookATime: {
  url: "https://calendly.com/yourname",
  label: "calendly.com/yourname",
  message: "Schedule some time with me:"
}
```

### Commands Configuration

```javascript
commands: [
  { name: "about", description: "About me" },
  { name: "education", description: "Educational background" },
  { name: "projects", description: "My projects" },
  { name: "experience", description: "Work experience" },
  { name: "skills", description: "Technical skills" },
  { name: "achievements", description: "Awards and recognition" },
  { name: "contact", description: "Contact information" },
  { name: "book-a-time", description: "Schedule a meeting" },
  { name: "download", description: "Download resume (PDF)" },
  { name: "clear", description: "Clear this window" }
]
```

**Note:** The `clear` and `download` commands are handled specially by the JavaScript. Other commands will display content sections.

### Error Messages

```javascript
error: {
  title: "ERROR",
  message: "Command not found!",
  helpHint: 'Type "<strong class="text-yellow">help</strong>" to see available commands.'
}
```

### 🆕 Custom Commands (Adding Your Own Commands!)

You can add **completely custom commands** with your own content! This is perfect for adding sections like `hobbies`, `certifications`, `publications`, `fun-facts`, or anything else you want.

```javascript
customCommands: [
  {
    name: "hobbies",           // The command name users will type
    description: "Things I do for fun",  // Shown in help menu
    content: `                 // The HTML content to display
      <ul>
        <li><strong class="text-green">Gaming:</strong> Strategy and RPG games</li>
        <li><strong class="text-green">Reading:</strong> Sci-fi and fantasy novels</li>
        <li><strong class="text-green">Music:</strong> Playing guitar</li>
      </ul>
    `
  },
  {
    name: "certifications",
    description: "Professional certifications",
    content: `
      <ul>
        <li><strong class="text-green">AWS Solutions Architect</strong> - 2023</li>
        <li><strong class="text-green">Google Cloud Professional</strong> - 2022</li>
      </ul>
    `
  }
]
```

**How to add a custom command:**

1. Open `config.js`
2. Find the `customCommands` array (near the bottom of CONFIG)
3. Add a new object with:
   - `name`: The command name (what users type)
   - `description`: Short description (shown in `help` command)
   - `content`: HTML content to display (can use styling classes)

**Notes:**
- Custom commands automatically appear in `help` and `ls` output
- Use the same CSS classes (`text-green`, `text-blue`, etc.) for consistent styling
- Use template literals (backticks) for multi-line content

## 📜 ASCII Art Configuration

At the bottom of `config.js`, you'll find two ASCII art constants:

### INTRO_ASCII
The ASCII art displayed when the page loads. Create your own using:
- [Text to ASCII Art Generator](https://patorjk.com/software/taag/)
- [ASCII Art Archive](https://www.asciiart.eu/)

```javascript
const INTRO_ASCII = `Your ASCII art here
spanning multiple lines
using template literals`;
```

### ERROR_ASCII
The ASCII art displayed when an invalid command is entered.

```javascript
const ERROR_ASCII = `Error ASCII art
displayed on invalid commands`;
```

## 🎨 Available CSS Classes for Styling

Use these classes in HTML strings within `config.js`:

| Class | Effect |
|-------|--------|
| `text-green` | Green text |
| `text-blue` | Blue text |
| `text-yellow` | Yellow/Gold text |
| `text-red` | Red text |
| `text-dim` | Dimmed/gray text |
| `bold` | Bold text |
| `italic` | Italic text |

Example usage:
```javascript
welcomeMessage: 'Hello! I am <span class="text-green">Your Name</span>'
```

## 🔧 Customization Tips

1. **Colors:** Edit `style.css` to change the color scheme
2. **Fonts:** Modify the font-family in `style.css`
3. **New Commands:** Add new entries to the `commands` array and corresponding content in your configuration
4. **ASCII Art:** Use a monospace font generator for best results

## 📝 Example: Minimal Configuration

Here's a minimal `config.js` to get started:

```javascript
const CONFIG = {
  meta: {
    title: "John Doe | Developer",
    description: "John Doe's portfolio",
    keywords: "developer, portfolio",
    author: "John Doe",
    ogTitle: "John Doe | Developer",
    ogDescription: "John Doe's developer portfolio",
    themeColor: "#0d1117"
  },
  terminal: {
    title: "john@portfolio: ~",
    prompt: { symbol: "➜", directory: "~" },
    welcomeMessage: 'Welcome! Type "help" for commands.'
  },
  resumeDownloadUrl: "resume.pdf",
  about: {
    name: "John Doe",
    alias: "johnd",
    role: "Software Developer",
    team: "Engineering",
    tagline: "Building cool stuff.",
    externalPortfolio: { label: "john.dev", url: "https://john.dev" },
    currentStatus: { role: "Developer", location: "Tech Corp" },
    recentWork: [],
    bio: "I love coding!"
  },
  education: [],
  projects: [],
  experience: [],
  skills: [],
  achievements: { asciiArt: "" },
  contact: {
    email: { address: "john@email.com", label: "john@email.com" },
    internal: { url: "", label: "" }
  },
  bookATime: { url: "", label: "", message: "" },
  commands: [
    { name: "about", description: "About me" },
    { name: "contact", description: "Contact info" },
    { name: "clear", description: "Clear terminal" }
  ],
  error: {
    title: "ERROR",
    message: "Command not found!",
    helpHint: 'Type "help" for available commands.'
  },
  customCommands: []  // Add your custom commands here!
};

const INTRO_ASCII = `Welcome to my portfolio!`;
const ERROR_ASCII = `Command not found :(`;
```

## 🌐 Deployment

This is a static site and can be deployed to:
- x20
- GitHub Pages
- **Or just open `index.html` directly in your browser!**

---

Made with ❤️ by @ayushsinghxyz 
