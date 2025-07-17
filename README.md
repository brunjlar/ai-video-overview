# **AI Video Overview**

This project is a lightweight, single-page web application that allows users to upload a teaching video, process it through the Google Gemini API, and receive a cleaned-up transcript enriched with helpful visual context. The final result can be viewed in-browser and downloaded as a Markdown or PDF file.

## **Key Features**

* **YouTube Link & Direct Upload:** Provide a video via a public YouTube URL or by uploading a local .mp4 file.  
* **AI-Powered Analysis:** Uses the Gemini 1.5 Flash model to perform a multi-pass analysis of the video content.  
* **Structured Output:** Generates a comprehensive document including:  
  * An overall summary of the video.  
  * A bulleted list of key takeaways.  
  * Identification of chapters with individual summaries.  
  * A full, cleaned-up transcript.  
* **Visual Context:** Identifies key visual moments in the video, extracts screenshots, and uses a second AI pass to generate meaningful, context-aware captions for each image.  
* **Client-Side Privacy:** All processing, including API calls, happens entirely in the user's browser. Your video data and API key are never sent to any server other than Google's AI platform.  
* **Export Options:** Download the final, polished document as a .md (Markdown) or .pdf file.

## **How It Works**

The application employs a sophisticated multi-pass, client-side architecture to ensure high-quality results while respecting user privacy.

1. **Initial Analysis (Pass 1):** When a video is uploaded, the app sends it to the Gemini API. The AI performs an initial pass to generate a clean, full transcript and identify potential "key moments" where the visuals are important for understanding. It inserts a simple placeholder tag at each of these moments.  
2. **Summarization (Pass 2):** The app then sends the clean transcript from the first pass back to the AI to generate a high-level summary, a list of key takeaways, and to identify the main chapters of the video.  
3. **Frame Extraction & Contextual Captioning (Pass 3):** The app uses the placeholders to extract the specific video frames. Then, in a series of parallel requests, it sends each frame *along with the surrounding text from the transcript* back to the AI. This crucial step allows the AI to generate a meaningful, context-aware caption for each image, explaining its relevance.  
4. **Final Assembly:** Finally, the app assembles all these pieces—the summaries, the chaptered transcript, and the context-aware image captions—into a single, well-structured Markdown document, which is then rendered on the screen.

## **Technology Stack**

* **Frontend:** Plain HTML, JavaScript, and CSS.  
* **Styling:** [Tailwind CSS](https://tailwindcss.com/) with the [Typography](https://tailwindcss.com/docs/typography-plugin) plugin.  
* **AI:** [Google Gemini 1.5 Flash API](https://ai.google.dev/).  
* **Markdown Rendering:** [marked.js](https://marked.js.org/).  
* **PDF Export:** [html2pdf.js](https://github.com/eKoopmans/html2pdf.js/).

## **Setup and Usage**

1. Clone the repository.  
2. Open the index.html file in your web browser.  
3. Obtain a Gemini API key from [Google AI Studio](https://aistudio.google.com/app/apikey).  
4. Enter your API key into the application.  
5. Upload a video file and click "Process Video".

## **Author**

Created by **Lars Brünjes**.

* **Email:** [brunjlar@gmail.com](mailto:brunjlar@gmail.com)  
* **GitHub:** [https://github.com/brunjlar](https://github.com/brunjlar)