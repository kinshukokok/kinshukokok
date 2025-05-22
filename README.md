Kinshuk Gupta, [22-05-2025 13:05]
import { useState } from "react";
import { motion } from "framer-motion";
import { Play } from "lucide-react";
import { Button } from "@/components/ui/button";

const slides = [
  {
    url: "/images/photo1.jpg",
    bg: "/images/ai-bg1.jpg",
    quote:
      "From the earliest days of my little feet’s race,\nYour love, Masi, was my warmest embrace.",
    bgColor: "bg-pink-100",
  },
  {
    url: "/images/photo2.jpg",
    bg: "/images/ai-bg2.jpg",
    quote:
      "You weren’t just family, you were my first best friend,\nWith you, every childhood memory had a magical blend.",
    bgColor: "bg-purple-100",
  },
  {
    url: "/images/photo3.jpg",
    bg: "/images/ai-bg3.jpg",
    quote:
      "Your stories, your laughter, your gentle care,\nMade every moment feel safe and rare.",
    bgColor: "bg-yellow-100",
  },
  {
    url: "/images/photo4.jpg",
    bg: "/images/ai-bg4.jpg",
    quote:
      "Even now, as I’m growing and finding my way,\nYour guidance still shapes every single day.",
    bgColor: "bg-blue-100",
  },
  {
    url: "/images/photo5.jpg",
    bg: "/images/ai-bg5.jpg",
    quote:
      "You’re not just my masi — you're my heart’s soft space,\nA hug in human form, a blessing full of grace.",
    bgColor: "bg-rose-100",
  },
  {
    url: "/images/photo6.jpg",
    bg: "/images/ai-bg6.jpg",
    quote:
      "In your smile I find strength, in your words I find peace,\nYour presence in my life is a lifelong masterpiece.",
    bgColor: "bg-green-100",
  },
  {
    url: "/images/photo7.jpg",
    bg: "/images/ai-bg7.jpg",
    quote:
      "You’ve always been the light in my growing years,\nWiping my worries, calming my fears.",
    bgColor: "bg-indigo-100",
  },
  {
    url: "/images/photo8.jpg",
    bg: "/images/ai-bg8.jpg",
    quote:
      "Happy Birthday, Masi, may your heart stay forever bright,\nWith endless love, laughter, and dreams in flight.",
    bgColor: "bg-orange-100",
  },
];

export default function BirthdayMemory() {
  const [index, setIndex] = useState(-1);

  const start = () => setIndex(0);
  const next = () => setIndex(index + 1);
  const restart = () => setIndex(0);

  const isStart = index === -1;
  const isEnd = index >= slides.length;

  return (
    <div className="w-full h-screen relative overflow-hidden flex items-center justify-center">
      {/* Background Audio */}
      <audio
        src="/music/when-i-was-a-boy.mp3"
        autoPlay
        loop
        className="hidden"
      />

      {/* Background Decorations */}
      <img
        src="/images/balloons.gif"
        alt="balloons"
        className="absolute w-full h-full object-cover opacity-30 z-0"
      />

      {/* Slide Background */}
      {!isStart && !isEnd && (
        <div
          className="absolute inset-0 z-0 bg-cover bg-center"
          style={{ backgroundImage: url(${slides[index].bg}) }}
        ></div>
      )}

Kinshuk Gupta, [22-05-2025 13:05]
{/* Foreground Content */}
      <div className="z-10 text-center px-4 max-w-xl w-full">
        {isStart ? (
          <motion.div initial={{ opacity: 0 }} animate={{ opacity: 1 }}>
            <h1 className="text-4xl font-bold text-white drop-shadow mb-6">
              A Journey Through Time – Happy Birthday 💖
            </h1>
            <Button
              onClick={start}
              className="bg-pink-500 text-white px-6 py-3 text-lg rounded-xl hover:bg-pink-600"
            >
              <Play className="mr-2" /> Tap to Begin 🎈
            </Button>
          </motion.div>
        ) : isEnd ? (
          <motion.div initial={{ opacity: 0 }} animate={{ opacity: 1 }}>
            <motion.img
              src="/images/gift-box.gif"
              alt="Gift"
              className="w-32 h-32 mx-auto mb-4"
              whileHover={{ scale: 1.1 }}
            />
            <h2 className="text-2xl font-bold mb-2">
              🎁 Your day is here – make a wish!
            </h2>
            <p className="italic mb-4">With all my love, Kinshuk</p>
            <Button
              onClick={restart}
              className="bg-purple-500 text-white px-5 py-2 rounded hover:bg-purple-600"
            >
              🔁 Restart Journey
            </Button>
          </motion.div>
        ) : (
          <motion.div
            key={index}
            initial={{ opacity: 0 }}
            animate={{ opacity: 1 }}
            className={p-6 rounded-xl shadow-xl backdrop-blur-md ${slides[index].bgColor}}
          >
            <img
              src={slides[index].url}
              alt={Slide ${index + 1}}
              className="rounded-lg mx-auto mb-4 max-h-96"
            />
            <p className="whitespace-pre-line italic text-lg">
              {slides[index].quote}
            </p>
            <Button
              onClick={next}
              className="mt-4 bg-blue-500 text-white hover:bg-blue-600"
            >
              Next ➡️
            </Button>
          </motion.div>
        )}
      </div>
    </div>
  );


<!---
kinshukokok/kinshukokok is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
