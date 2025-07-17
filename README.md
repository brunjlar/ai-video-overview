# **AI Video Overview**

This project is a lightweight, single-page web application that allows users to upload a teaching video, process it through the Google Gemini API, and receive a cleaned-up transcript enriched with helpful visual context. The final result can be viewed in-browser and downloaded as a Markdown or PDF file.

---

## **Key Features**

* **Direct Video Upload:** Upload a local .mp4 file directly for AI-powered analysis.  
* **AI-Powered Analysis:** Uses the Gemini 1.5 Flash model to perform a multi-pass analysis of the video content.  
* **Structured Output:** Generates a comprehensive document including:  
  * An overall summary of the video.  
  * A bulleted list of key takeaways.  
  * Identification of chapters with individual summaries.  
  * A full, cleaned-up transcript.  
* **Visual Context:** Identifies key visual moments in the video, extracts screenshots, and uses a second AI pass to generate meaningful, context-aware captions for each image.  
* **Client-Side Privacy:** All processing, including API calls, happens entirely in the user's browser. Your video data and API key are never sent to any server other than Google's AI platform.  
* **Export Options:** Download the final, polished document as a .md (Markdown) or .pdf file.

---

## **How It Works**

The application employs a sophisticated two-pass, client-side architecture to ensure high-quality results while respecting user privacy.

1. **Pass 1: Document Structuring:** When you upload a video, the app first sends it to the Gemini 1.5 Flash model. The AI is instructed to analyze the entire video and return a single, well-structured Markdown document. This document includes an overall summary, a list of key takeaways, and the full transcript, correctly divided into chapters with individual summaries. It also identifies 10-15 of the most critical visual moments and inserts simple \[screenshot:...\] placeholder tags at the correct positions within the transcript.  
2. **Pass 2: Contextual Captioning:** The app then extracts the video frames for each placeholder. In a series of parallel requests, it sends each frame *along with the surrounding text from the transcript* back to the AI. This crucial step provides the necessary context for the AI to generate a meaningful, relevant caption for each image.  
3. **Final Assembly:** Finally, the app assembles the final document by replacing the placeholders in the text from Pass 1 with the high-quality captions and images from Pass 2, using proper Markdown syntax. This complete document is then rendered on the screen for you to read, review, and download.

---

## **Technology Stack**

* **Frontend:** Plain HTML, JavaScript, and CSS.  
* **Styling:** [Tailwind CSS](https://tailwindcss.com/) with the [Typography](https://tailwindcss.com/docs/typography-plugin) plugin.  
* **AI:** [Google Gemini 1.5 Flash API](https://ai.google.dev/).  
* **Markdown Rendering:** [marked.js](https://marked.js.org/).  
* **PDF Export:** [html2pdf.js](https://github.com/eKoopmans/html2pdf.js/).

---

## **Setup and Usage**

1. Clone the repository.  
2. Open the index.html file in your web browser.  
3. Obtain a Gemini API key from [Google AI Studio](https://aistudio.google.com/app/apikey).  
4. Enter your API key into the application.  
5. Upload a video file and click "Process Video".

---

## **Author**

Created by **Lars Brünjes**.

* **Email:** [brunjlar@gmail.com](mailto:brunjlar@gmail.com)  
* **GitHub:** [https://github.com/brunjlar](https://github.com/brunjlar)