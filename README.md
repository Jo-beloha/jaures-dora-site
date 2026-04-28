import { useState } from "react";
import { motion } from "framer-motion";

export default function App() {
  const [messageSent, setMessageSent] = useState(false);

  const projects = [
    {
      title: "Harmonea Brand",
      desc: "Branding & e-commerce concept for a modern lifestyle brand.",
    },
    {
      title: "Digital Design Pack",
      desc: "Creation of logos, social media kits and visual identity systems.",
    },
    {
      title: "Business Concepts",
      desc: "Development of product catalogs and international business ideas.",
    },
  ];

  return (
    <div className="bg-black text-white min-h-screen font-sans">
      
      {/* NAV */}
      <header className="fixed top-0 w-full flex justify-between items-center px-10 py-6 bg-black/60 backdrop-blur-md border-b border-white/10">
        <h1 className="tracking-[0.3em] font-light">JAURES DORA</h1>
        <nav className="space-x-6 text-sm text-white/70">
          <a href="#about" className="hover:text-white">About</a>
          <a href="#projects" className="hover:text-white">Projects</a>
          <a href="#contact" className="hover:text-white">Contact</a>
        </nav>
      </header>

      {/* HERO */}
      <section className="h-screen flex flex-col justify-center items-center text-center px-6">
        <motion.h2
          initial={{ opacity: 0, y: 20 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 1 }}
          className="text-5xl md:text-7xl font-light"
        >
          Jaures Dora
        </motion.h2>

        <p className="mt-6 text-white/60 max-w-xl">
          Entrepreneur • Designer • Creator of digital and business concepts
        </p>
      </section>

      {/* ABOUT */}
      <section id="about" className="px-10 py-24 border-t border-white/10">
        <h2 className="text-3xl font-light mb-6">About Me</h2>
        <p className="text-white/60 max-w-2xl leading-relaxed">
          I am focused on building modern brands, digital products, and business ideas with a global vision.
        </p>
      </section>

      {/* PROJECTS */}
      <section id="projects" className="px-10 py-24">
        <h2 className="text-3xl font-light mb-10">Projects</h2>

        <div className="grid md:grid-cols-3 gap-8">
          {projects.map((p, i) => (
            <motion.div
              key={i}
              whileHover={{ scale: 1.03 }}
              className="border border-white/10 rounded-2xl p-6 bg-white/5"
            >
              <h3 className="text-xl font-light mb-2">{p.title}</h3>
              <p className="text-white/60 text-sm">{p.desc}</p>
            </motion.div>
          ))}
        </div>
      </section>

      {/* CONTACT */}
      <section id="contact" className="px-10 py-24 border-t border-white/10">
        <h2 className="text-3xl font-light mb-6">Contact</h2>
        <p className="text-white/60">Let’s work together on your ideas.</p>

        {!messageSent ? (
          <button
            onClick={() => setMessageSent(true)}
            className="mt-6 px-6 py-3 border border-white/20 rounded-xl hover:bg-white hover:text-black transition"
          >
            Send Message
          </button>
        ) : (
          <p className="mt-6 text-green-400">Message sent successfully ✔</p>
        )}
      </section>

      {/* FOOTER */}
      <footer className="text-center py-10 border-t border-white/10 text-white/40 text-sm">
        © 2026 Jaures Dora. All rights reserved.
      </footer>
    </div>
  );
}
