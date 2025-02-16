import { useState } from "react";
import { Button } from "@/components/ui/button";

export default function SimpleGame() {
  const [position, setPosition] = useState({ x: 50, y: 50 });
  const [score, setScore] = useState(0);

  const moveButton = () => {
    const newX = Math.floor(Math.random() * 80) + 10;
    const newY = Math.floor(Math.random() * 80) + 10;
    setPosition({ x: newX, y: newY });
    setScore(score + 1);
  };

  return (
    <div className="flex flex-col items-center justify-center h-screen bg-gray-100 relative">
      <h1 className="text-3xl font-bold mb-4">Catch the Button!</h1>
      <p className="text-xl mb-4">Score: {score}</p>
      <Button
        onClick={moveButton}
        className="absolute"
        style={{ top: `${position.y}%`, left: `${position.x}%`, position: "absolute" }}
      >
        Catch Me!
      </Button>
    </div>
  );
}
