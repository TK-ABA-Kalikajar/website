# TK ABA Kalikajar Website

Official website for **TK ABA Kalikajar** - a kindergarten school under Aisyiyah organization located in Kalikajar, Wonosobo, Central Java, Indonesia.

**Live Site:** https://tkabakalikajar.sch.id

---

## About

TK ABA Kalikajar (Taman Kanak-Kanak Aisyiyah Bustanul Athfal Kalikajar) is an Islamic kindergarten committed to nurturing the Qur'anic generation with noble character (Generasi Qur'ani yang Berakhlaqul Karimah).

### Vision
Terwujudnya Generasi Qur'ani yang Berakhlaqul Karimah (Realizing the Qur'anic Generation with Noble Character)

---

## Tech Stack

- **Framework:** [Astro](https://astro.build/) v4.15
- **Styling:** [Tailwind CSS](https://tailwindcss.com/) v3.4
- **Language:** TypeScript
- **Deployment:** [Vercel](https://vercel.com/)

---

## Project Structure

```
aba-kalikajar/
├── website/                    # Main website source code
│   ├── src/
│   │   ├── layouts/           # Page layouts (BaseLayout.astro)
│   │   └── pages/             # Website pages
│   │       ├── index.astro    # Homepage (Beranda)
│   │       ├── tentang.astro  # About Us (Tentang Kami)
│   │       ├── profil.astro   # School Profile (Profil)
│   │       ├── guru-staff.astro # Teachers & Staff
│   │       ├── siswa.astro    # Students (Siswa)
│   │       ├── galeri.astro   # Photo Gallery
│   │       └── kontak.astro   # Contact Page
│   ├── public/
│   │   ├── images/            # Static images
│   │   └── favicon.png        # Site favicon
│   ├── astro.config.mjs       # Astro configuration
│   ├── tailwind.config.mjs    # Tailwind CSS configuration
│   ├── package.json           # Dependencies
│   └── VERCEL_DEPLOYMENT.md   # Deployment guide
├── extracted_images/          # Source images from school document
└── README.md                  # This file
```

---

## Getting Started

### Prerequisites

- Node.js 18 or higher
- npm or yarn

### Installation

```bash
# Clone the repository
git clone git@github.com:TK-ABA-Kalikajar/website.git
cd website

# Navigate to website folder
cd website

# Install dependencies
npm install

# Start development server
npm run dev
```

The site will be available at `http://localhost:4321`

### Available Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server |
| `npm run build` | Build for production |
| `npm run preview` | Preview production build locally |
| `npm run astro` | Run Astro CLI commands |

---

## Pages

| Page | Route | Description |
|------|-------|-------------|
| Beranda | `/` | Homepage with hero, features, and highlights |
| Tentang Kami | `/tentang` | About the school, history, vision & mission |
| Profil | `/profil` | School profile and institutional information |
| Guru & Staff | `/guru-staff` | Teachers and staff directory |
| Siswa | `/siswa` | Student information and activities |
| Galeri | `/galeri` | Photo gallery of school activities |
| Kontak | `/kontak` | Contact form and school location |

---

## Deployment

The website is deployed on **Vercel** with automatic deployments on push to `main` branch.

### Custom Domain Setup

Domain `tkabakalikajar.sch.id` is configured with:
- **Registrar:** Domainesia
- **DNS:** A record pointing to Vercel (`216.198.79.1`)
- **SSL:** Automatic via Vercel (Let's Encrypt)

See [VERCEL_DEPLOYMENT.md](website/VERCEL_DEPLOYMENT.md) for detailed deployment instructions.

---

## Development

### Adding New Pages

1. Create a new `.astro` file in `src/pages/`
2. Use the `BaseLayout` component for consistent styling
3. Add navigation link in `BaseLayout.astro`

### Updating Content

- **Images:** Add to `public/images/`
- **Text content:** Edit the respective `.astro` page file
- **Styling:** Uses Tailwind CSS classes

### Color Scheme

| Color | Tailwind Class | Usage |
|-------|----------------|-------|
| Green | `green-600/700` | Primary color, headers, buttons |
| Yellow | `yellow-400/500` | Secondary color, accents |
| Gray | `gray-50/600/800` | Backgrounds, text |

---

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit changes (`git commit -m 'Add new feature'`)
4. Push to branch (`git push origin feature/new-feature`)
5. Open a Pull Request

---

## License

This project is for TK ABA Kalikajar. All rights reserved.

---

## Contact

**TK ABA Kalikajar**
- Address: Kalikajar, Wonosobo, Jawa Tengah
- Website: https://tkabakalikajar.sch.id
