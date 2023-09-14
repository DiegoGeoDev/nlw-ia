- yarn create vite => react + ts

- shadcn/ui

yarn add -D tailwindcss postcss autoprefixer
npx tailwindcss init -p

tsconfig.json

```
   "baseUrl": ".",
   "paths": {
   "@/*": ["./src/*"]
   }
```

yarn add -D @types/node

vite.config.ts

```
import path from "path";
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react";

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
});
```

npx shadcn-ui@latest init
√ Would you like to use TypeScript (recommended)? ... no / yes
√ Which style would you like to use? » New York
√ Which color would you like to use as base color? » Zinc
√ Where is your global CSS file? ... src/index.css
√ Would you like to use CSS variables for colors? ... no / yes
√ Where is your tailwind.config.js located? ... tailwind.config.js
√ Configure the import alias for components: ... @/components
√ Configure the import alias for utils: ... @/lib/utils
√ Are you using React Server Components? ... no / yes
√ Write configuration to components.json. Proceed? ... yes

- theme

https://ui.shadcn.com/themes

```

@layer base {
  :root {
    --background: 0 0% 100%;
    --foreground: 222.2 84% 4.9%;
    --card: 0 0% 100%;
    --card-foreground: 222.2 84% 4.9%;
    --popover: 0 0% 100%;
    --popover-foreground: 222.2 84% 4.9%;
    --primary: 221.2 83.2% 53.3%;
    --primary-foreground: 210 40% 98%;
    --secondary: 210 40% 96.1%;
    --secondary-foreground: 222.2 47.4% 11.2%;
    --muted: 210 40% 96.1%;
    --muted-foreground: 215.4 16.3% 46.9%;
    --accent: 210 40% 96.1%;
    --accent-foreground: 222.2 47.4% 11.2%;
    --destructive: 0 84.2% 60.2%;
    --destructive-foreground: 210 40% 98%;
    --border: 214.3 31.8% 91.4%;
    --input: 214.3 31.8% 91.4%;
    --ring: 221.2 83.2% 53.3%;
    --radius: 0.5rem;
  }

  .dark {
    --background: 222.2 84% 4.9%;
    --foreground: 210 40% 98%;
    --card: 222.2 84% 4.9%;
    --card-foreground: 210 40% 98%;
    --popover: 222.2 84% 4.9%;
    --popover-foreground: 210 40% 98%;
    --primary: 217.2 91.2% 59.8%;
    --primary-foreground: 222.2 47.4% 11.2%;
    --secondary: 217.2 32.6% 17.5%;
    --secondary-foreground: 210 40% 98%;
    --muted: 217.2 32.6% 17.5%;
    --muted-foreground: 215 20.2% 65.1%;
    --accent: 217.2 32.6% 17.5%;
    --accent-foreground: 210 40% 98%;
    --destructive: 0 62.8% 30.6%;
    --destructive-foreground: 210 40% 98%;
    --border: 217.2 32.6% 17.5%;
    --input: 217.2 32.6% 17.5%;
    --ring: 224.3 76.3% 48%;
  }
}
```

- yarn add lucide-react

- https://ffmpegwasm.netlify.app/
- https://unpkg.com/browse/@ffmpeg/core@0.12.2/
- npm install @ffmpeg/ffmpeg @ffmpeg/util
- ffmpeg command to convert a mp4 in mp3 with 20k bitrate
- chatgpt explain that code

```
await ffmpeg.exec([
  "-i",
  "input.mp4",
  "-map",
  "0:a", // faixa 0 = audio
  "-b:a", // bitrate
  "20k",
  "-acodec",
  "libmp3lame", // codec
  "output.mp3",
]);

"-i", "input.mp4",

-i is an FFmpeg command-line option used to specify the input file.
"input.mp4" is the name of the input video file that you want to convert. It assumes there is a file named "input.mp4" in the same directory as the script.
"-map", "0:a",

-map is another FFmpeg command-line option that allows you to specify the streams or channels to include in the output.
"0:a" is used to indicate that you want to include the audio stream (audio channel) from the input file. "0" refers to the first input stream, and ":a" specifies the audio stream within that input.
"-b:a", "20k",

-b:a is an FFmpeg option used to set the audio bitrate.
"20k" specifies a target audio bitrate of 20 kilobits per second (20kbit/s). This will affect the audio quality and file size of the output MP3.
"-acodec", "libmp3lame",

-acodec is used to specify the audio codec to be used for encoding the audio in the output file.
"libmp3lame" is the codec being used here, which is the LAME MP3 codec. LAME is a popular and widely used codec for encoding MP3 audio.
"output.mp3",

"output.mp3" is the name of the output audio file where the converted audio will be saved. It assumes that the output will be saved with the ".mp3" file extension.
```

- atualizar vite.config.ts

```
  optimizeDeps: {
    exclude: ["@ffmpeg/ffmpeg", "@ffmpeg/util"],
  },
```

- npm i axios

- npm i ai
