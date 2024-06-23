# gemini-api

import { GoogleGenerativeAI } from "@google/generative-ai";

async function fetchGenerativeContent() {
  const genAi = new GoogleGenerativeAI(
    "AIzaSyC-AfQw2ZyVRhvXWjo3S41QKdZY_f-YCYM"
  );
  const model = genAi.getGenerativeModel({
    model: "gemini-1.5-pro",
  });

  try {
    const r = await model.generateContent("top 10 animes to watch");
    console.log(await r.response.text());
    
  } catch (error) {
    console.error("Error generating content:", error);
  }
}

fetchGenerativeContent();
