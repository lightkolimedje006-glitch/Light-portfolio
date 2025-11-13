# Light-portfolio
import React from "react"; import { motion } from "framer-motion"; import { Mail, Github, Linkedin } from "lucide-react";

// Simple, single-file portfolio built with TailwindCSS + Framer Motion // Instructions: drop this file into a React + Tailwind project (e.g. Vite, Next.js). // Customize the PROFILE and PROJECTS constants below with your info.

const PROFILE = { name: "Light KOLIMEDJE", role: "Étudiant en génie civil • Créateur de contenu", bio: Je construis, j'apprends et je partage. Portfolio de projets, textes et services., location: "Cotonou, Bénin", email: "Lightkolimedje006@gmail.com", socials: { github: "#", linkedin: "https://www.instagram.com/______vegeta?igsh=YnB1Z2lrbnNrZGdv", }, };

const PROJECTS = [ { id: 1, title: "Projet de structure — Pont piéton", tags: ["Génie civil", "Calculs", "Dessin"], description: "Analyse et dimensionnement d'un pont piéton en acier. Plans et notes de calcul.", image: "/your-photos/projet1.jpg", link: "#", }, { id: 2, title: "Boutique en ligne — Bracelets en corail", tags: ["E‑commerce", "Branding", "Photoshop"], description: "Conception du store, fiches produit et stratégie réseaux sociaux.", image: "/your-photos/projet2.jpg", link: "#", }, { id: 3, title: "Punchlines & Textes — @LKPunchlines", tags: ["Écriture", "Copywriting"], description: "Collection de textes percutants pour posts et bios Instagram.", image: "/your-photos/projet3.jpg", link: "#", }, ];

export default function PortfolioSite() { return ( <div className="min-h-screen bg-gray-50 text-gray-900 antialiased"> <header className="bg-white border-b"> <div className="container mx-auto px-6 py-4 flex items-center justify-between"> <div> <h1 className="text-xl font-bold">{PROFILE.name}</h1> <p className="text-sm text-gray-600">{PROFILE.role}</p> </div> <nav className="flex gap-4 items-center"> <a href="#projects" className="text-sm hover:underline"> Projets </a> <a href="#about" className="text-sm hover:underline"> À propos </a> <a href="#contact" className="text-sm hover:underline"> Contact </a> </nav> </div> </header>

<main className="container mx-auto px-6 py-10">
    {/* HERO */}
    <section className="grid lg:grid-cols-2 gap-8 items-center">
      <motion.div
        initial={{ opacity: 0, x: -20 }}
        animate={{ opacity: 1, x: 0 }}
        transition={{ duration: 0.6 }}
      >
        <h2 className="text-4xl font-extrabold mb-4">Salut — je suis {PROFILE.name}.</h2>
        <p className="text-lg text-gray-700 mb-6">{PROFILE.bio}</p>

        <div className="flex items-center gap-4">
          <a
            href={PROFILE.socials.github}
            target="_blank"
            rel="noreferrer"
            className="inline-flex items-center gap-2 px-4 py-2 border rounded-lg text-sm"
          >
            <Github size={16} /> GitHub
          </a>

          <a
            href={PROFILE.socials.linkedin}
            target="_blank"
            rel="noreferrer"
            className="inline-flex items-center gap-2 px-4 py-2 bg-slate-900 text-white rounded-lg text-sm"
          >
            <Linkedin size={16} /> LinkedIn
          </a>
        </div>
      </motion.div>

      <motion.div
        className="rounded-2xl overflow-hidden shadow-lg"
        initial={{ opacity: 0, scale: 0.98 }}
        animate={{ opacity: 1, scale: 1 }}
        transition={{ duration: 0.6 }}
      >
        <img
          src="/your-photos/profile.jpg"
          alt="Profil"
          className="w-full h-auto object-cover"
        />
      </motion.div>
    </section>

    {/* PROJECTS */}
    <section id="projects" className="mt-14">
      <h3 className="text-2xl font-bold mb-6">Projets récents</h3>
      <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        {PROJECTS.map((p) => (
          <motion.article
            key={p.id}
            whileHover={{ y: -6 }}
            className="bg-white rounded-2xl overflow-hidden shadow"
          >
            <img src={p.image} alt={p.title} className="w-full h-40 object-cover" />
            <div className="p-4">
              <h4 className="font-semibold">{p.title}</h4>
              <p className="text-sm text-gray-600 mt-2">{p.description}</p>
              <div className="flex gap-2 mt-3 flex-wrap">
                {p.tags.map((t) => (
                  <span
                    key={t}
                    className="text-xs px-2 py-1 bg-gray-100 rounded-full"
                  >
                    {t}
                  </span>
                ))}
              </div>

              <div className="mt-4 flex items-center justify-between">
                <a
                  href={p.link}
                  className="text-sm underline"
                  target="_blank"
                  rel="noreferrer"
                >
                  Voir
                </a>
                <a href={`mailto:${PROFILE.email}?subject=Projet%20:${encodeURIComponent(
                  p.title
                )}`} className="text-sm inline-flex items-center gap-2">
                  <Mail size={14} /> Contacter
                </a>
              </div>
            </div>
          </motion.article>
        ))}
      </div>
    </section>

    {/* ABOUT */}
    <section id="about" className="mt-14 bg-white rounded-2xl p-6 shadow">
      <h3 className="text-2xl font-bold mb-4">À propos de moi</h3>
      <p className="text-gray-700">{PROFILE.role} basé à {PROFILE.location}.</p>

      <div className="mt-4 grid md:grid-cols-2 gap-4">
        <div>
          <h4 className="font-semibold mb-2">Compétences</h4>
          <ul className="list-disc ml-5 text-gray-700">
            <li>Dimensionnement & notes de calcul</li>
            <li>Modélisation (AutoCAD, Revit)</li>
            <li>E‑commerce & marketing</li>
            <li>Copywriting & création de contenu</li>
          </ul>
        </div>
        <div>
          <h4 className="font-semibold mb-2">Services</h4>
          <ul className="list-disc ml-5 text-gray-700">
            <li>Études & notes de calcul</li>
            <li>Conception de boutiques en ligne</li>
            <li>Rédaction & punchlines percutantes</li>
          </ul>
        </div>
      </div>
    </section>

    {/* CONTACT */}
    <section id="contact" className="mt-14">
      <h3 className="text-2xl font-bold mb-4">Contact</h3>
      <div className="grid md:grid-cols-2 gap-6">
        <form
          className="bg-white p-6 rounded-2xl shadow"
          onSubmit={(e) => {
            e.preventDefault();
            const form = e.target as HTMLFormElement;
            const data = new FormData(form);
            const name = data.get("name") || ""
            const message = data.get("message") || "";
            window.location.href = `mailto:${PROFILE.email}?subject=${encodeURIComponent(
              `Message de ${name}`
            )}&body=${encodeURIComponent(String(message))}`;
          }}
        >
          <div className="mb-3">
            <label className="text-sm">Nom</label>
            <input name="name" className="w-full mt-1 border rounded px-3 py-2" required />
          </div>
          <div className="mb-3">
            <label className="text-sm">Message</label>
            <textarea name="message" rows={5} className="w-full mt-1 border rounded px-3 py-2" required />
          </div>
          <button className="px-4 py-2 rounded bg-slate-900 text-white">Envoyer</button>
        </form>

        <aside className="bg-white p-6 rounded-2xl shadow flex flex-col justify-between">
          <div>
            <h4 className="font-semibold">Coordonnées</h4>
            <p className="text-sm text-gray-700 mt-2">{PROFILE.location}</p>
            <p className="text-sm text-gray-700">{PROFILE.email}</p>
          </div>

          <div className="mt-6 flex gap-3">
            <a href={PROFILE.socials.github} target="_blank" rel="noreferrer" aria-label="GitHub">
              <Github />
            </a>
            <a href={PROFILE.socials.linkedin} target="_blank" rel="noreferrer" aria-label="LinkedIn">
              <Linkedin />
            </a>
          </div>
        </aside>
      </div>
    </section>
  </main>

  <footer className="border-t py-6 mt-12">
    <div className="container mx-auto px-6 text-center text-sm text-gray-600">
      © {new Date().getFullYear()} {PROFILE.name} — Fait pour la gloire de Dieu.
    </div>
  </footer>
</div>

); }
