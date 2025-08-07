Tactical Assistant for Coaches
<p align="center">
<img src="https://storage.googleapis.com/maker-suite-gallery/images/brand-guidelines/google-ai-logo.svg" alt="Google AI Logo" width="150" />
</p>
<p align="center">

A strategic AI sidekick for <strong>rugby and basketball coaches</strong>, designed for match preparation, player development, and performance analysis.

</p>
➡️ View Live Demo
(Replace the link above with your actual deployment URL after deploying)
![alt text](https://raw.githubusercontent.com/google/framer-prototyping-ai-tactical-assistant/main/screenshots/tactical-assistant-screenshot.png)


(Feel free to replace this with your own screenshot!)
✨ Key Features
This tool helps coaches streamline their workflow with AI-powered insights:
📊 Interactive Dashboard: Visualize key team and player performance metrics at a glance.
🎥 AI Footage Analysis: Simulates analysis of game footage summaries to automatically extract key tactical moments and insights.
🧠 Tactical Search: Ask complex tactical questions (e.g., "effective strategies against a 2-3 zone defense") and get up-to-date answers grounded with Google Search results and sources.
📋 Custom Drill Generator: Describe a team's weakness (e.g., "poor at securing defensive rebounds") and get tailored, creative training drills in seconds.
🗓️ Visual Training Planner: A calendar to visualize training schedules, recovery days, and match days.
💬 AI Feedback Summarizer: Anonymously collect player feedback and use AI to instantly identify positive and constructive themes, saving hours of manual review.


🛠️ Tech Stack
This project is a modern, serverless single-page application built with:
Frontend: React 19 & TypeScript
Styling: Tailwind CSS
AI: Google Gemini API (@google/genai) for all generative AI features.
Charts: Recharts for data visualization.
Build: No build step! The app uses modern ES Modules loaded directly in the browser via an importmap.


🚀 Deployment
The easiest way to deploy this application is with a platform like Vercel or Netlify. This project is optimized for a fast, simple deployment.
Deploying with Vercel
Fork/Clone this Repository: Push the code to your own GitHub account.
Create a Vercel Project: Sign up for a free Vercel account and import your GitHub repository.
Configure Project Settings:
Framework Preset: Vercel should detect that this is not a standard framework. Select Other.
Build & Output Settings: You can leave the build command and output directory empty. Vercel will correctly serve the index.html file by default.
Add Environment Variable (Crucial Step):
Go to your project's Settings > Environment Variables.
Add a new variable:
Name: API_KEY
Value: Paste your Google Gemini API key here.
This keeps your key secure and allows the deployed application to access the Gemini API.
Deploy: Click the "Deploy" button. Your Tactical Assistant will be live on a public URL in minutes!


⚙️ How It Works
The application makes direct calls to the Google Gemini API from the client-side. The geminiService.ts file contains all the logic for communicating with the AI model, including:
Structured Output: Using responseSchema to ensure the AI returns valid JSON for features like the drill generator and feedback analysis.
Search Grounding: Using tools: [{ googleSearch: {} }] to power the Tactical Search feature with real-time web data.
Error Handling: Robust try...catch blocks to gracefully handle potential API errors.
The process.env.API_KEY is a placeholder that is safely substituted by the deployment platform (like Vercel) at runtime. It is not exposed to the browser.