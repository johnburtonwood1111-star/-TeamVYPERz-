import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { motion } from "framer-motion";
import { Users, Gamepad2, Trophy, Newspaper, Mail } from "lucide-react";
import Image from "next/image";

export default function Home() {
  const leaders = [
    { name: "Wololo", role: "Clan Leader", img: "/wololo.png" },
    { name: "Sloppy Looter", role: "Co-Leader" },
  ];

  const members = [
    { name: "Mafia-Princess", role: "Member" },
    { name: "Marieke", role: "Member" },
    { name: "ShrimpMaster", role: "Member" },
    { name: "skippy2020nl", role: "Member" },
  ].sort((a, b) => a.name.localeCompare(b.name));

  return (
    <div className="min-h-screen bg-black text-white font-sans">
      {/* Header */}
      <header className="p-6 flex justify-between items-center border-b border-gray-800">
        <div className="flex items-center gap-4">
          <Image
            src="/vyperz-logo.png"
            alt="VYPERz Logo"
            width={60}
            height={60}
            className="rounded-full border-2 border-green-500"
          />
          <h1 className="text-3xl font-extrabold text-green-500">VYPERz</h1>
        </div>
        <nav className="space-x-6">
          <a href="#team" className="hover:text-green-400">Team</a>
          <a href="#matches" className="hover:text-green-400">Matches</a>
          <a href="#news" className="hover:text-green-400">News</a>
          <a href="#join" className="hover:text-green-400">Join Us</a>
          <a href="#contact" className="hover:text-green-400">Contact</a>
        </nav>
      </header>

      {/* Hero Section */}
      <section className="text-center py-24 bg-gradient-to-b from-black to-gray-900">
        <motion.h2
          initial={{ opacity: 0, y: -30 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 1 }}
          className="text-6xl font-bold text-green-500 drop-shadow-lg"
        >
          UNLEASH THE VYPER
        </motion.h2>
        <p className="mt-6 text-lg text-gray-300">
          VYPERz is a competitive <span className="text-green-400 font-semibold">Call of Duty</span> Esports team striking fear in every arena.
        </p>
        <Button className="mt-8 bg-green-600 hover:bg-green-500 rounded-2xl px-6 py-3 text-lg">
          Join The Clan
        </Button>
      </section>

      {/* Team Section */}
      <section id="team" className="p-12">
        <h3 className="text-4xl font-bold mb-8 flex items-center gap-2">
          <Users className="text-green-500" /> Our Team
        </h3>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
          {[...leaders, ...members].map((player) => (
            <Card key={player.name} className="bg-gray-900 border border-gray-700">
              <CardContent className="p-6 text-center">
                {player.img && (
                  <div className="flex justify-center mb-4">
                    <Image
                      src={player.img}
                      alt={player.name}
                      width={100}
                      height={100}
                      className="rounded-full border-2 border-green-500"
                    />
                  </div>
                )}
                <div className="text-2xl font-semibold text-green-400">{player.name}</div>
                <p className="text-gray-400 mt-2">{player.role}</p>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>

      {/* Matches Section */}
      <section id="matches" className="p-12 bg-gray-950">
        <h3 className="text-4xl font-bold mb-8 flex items-center gap-2">
          <Gamepad2 className="text-green-500" /> Upcoming Matches
        </h3>
        <ul className="space-y-4">
          <li className="flex justify-between bg-gray-900 p-4 rounded-xl border border-gray-700">
            <span>VYPERz vs ShadowClan</span>
            <span className="text-green-400">Sept 15, 2025</span>
          </li>
          <li className="flex justify-between bg-gray-900 p-4 rounded-xl border border-gray-700">
            <span>VYPERz vs IronFist</span>
            <span className="text-green-400">Sept 28, 2025</span>
          </li>
        </ul>
      </section>

      {/* News Section */}
      <section id="news" className="p-12">
        <h3 className="text-4xl font-bold mb-8 flex items-center gap-2">
          <Newspaper className="text-green-500" /> Latest News
        </h3>
        <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
          <Card className="bg-gray-900 border border-gray-700">
            <CardContent className="p-6">
              <h4 className="text-xl font-bold text-green-400">VYPERz Enters Esports League</h4>
              <p className="mt-2 text-gray-400">We are officially competing in the 2025 Pro League.</p>
            </CardContent>
          </Card>
          <Card className="bg-gray-900 border border-gray-700">
            <CardContent className="p-6">
              <h4 className="text-xl font-bold text-green-400">New Roster Revealed</h4>
              <p className="mt-2 text-gray-400">Meet the new players joining the VYPERz family.</p>
            </CardContent>
          </Card>
        </div>
      </section>

      {/* Join Us Section */}
      <section id="join" className="p-12 bg-gray-950 text-center">
        <h3 className="text-4xl font-bold mb-6 flex items-center justify-center gap-2">
          <Trophy className="text-green-500" /> Join The VYPERz
        </h3>
        <p className="text-gray-400 mb-8">
          Think you have what it takes? Apply now to become part of the next big esports dynasty.
        </p>
        <Button className="bg-green-600 hover:bg-green-500 rounded-2xl px-6 py-3 text-lg">
          Apply Now
        </Button>
      </section>

      {/* Contact Section */}
      <section id="contact" className="p-12 text-center">
        <h3 className="text-4xl font-bold mb-6 flex items-center justify-center gap-2">
          <Mail className="text-green-500" /> Contact Us
        </h3>
        <form className="max-w-2xl mx-auto space-y-4">
          <input
            type="text"
            placeholder="Your Name"
            className="w-full p-3 rounded-xl bg-gray-900 border border-gray-700 text-white"
          />
          <input
            type="email"
            placeholder="Your Email"
            className="w-full p-3 rounded-xl bg-gray-900 border border-gray-700 text-white"
          />
          <textarea
            placeholder="Your Message"
            rows={4}
            className="w-full p-3 rounded-xl bg-gray-900 border border-gray-700 text-white"
          ></textarea>
          <Button className="bg-green-600 hover:bg-green-500 rounded-2xl px-6 py-3 text-lg w-full">
            Send Message
          </Button>
        </form>
      </section>

      {/* Footer */}
      <footer className="p-6 text-center border-t border-gray-800 text-gray-500">
        © 2025 VYPERz Clan. All rights reserved.
      </footer>
    </div>
  );
