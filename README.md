# Proof of Concept: Running Gemini Nano on Browser Locally

## Overview

This project serves as a proof of concept (PoC) for exploring how to run **Gemini Nano** in a web browser using the experimental **Prompt API** in Google Chrome. The goal is to demonstrate how web developers can access browser-provided language models and perform on-device inference of powerful AI models, ensuring privacy-preserving use cases.

## Objective

The objective of this PoC is to showcase the capabilities of the new Built-in AI feature in Google Chrome, allowing for seamless integration of AI functionalities directly within web applications.

## Prerequisites

Before you begin, ensure you have the following:

- A computer with Google Chrome installed (version 115 or later).
- Basic knowledge of HTML and JavaScript.
- Familiarity with AI concepts and language models.

## Steps to Enable Built-in AI Feature

1. **Update Google Chrome**: Ensure you are using the latest version of Google Chrome. Check for updates at `chrome://settings/help`.

2. **Enable Experimental Features**:
   - Open a new tab in Chrome and navigate to `chrome://flags`.
   - Search for "Built-in AI" or "Prompt API".
   - Enable the relevant flags by selecting "Enabled" from the dropdown menu.
   - Restart your browser to apply the changes.

## Implementation

1. **Create a Simple HTML File**:
   - Create a new HTML file (e.g., `index.html`) in your project directory.
   - Add the following code to set up a basic interface for interacting with Gemini Nano:

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Gemini Nano PoC</title>
   </head>
   <body>
       <h1>Gemini Nano Proof of Concept</h1>
       <textarea id="input" rows="4" cols="50" placeholder="Type your prompt here..."></textarea>
       <button id="run">Run Gemini Nano</button>
       <h2>Output:</h2>
       <pre id="output"></pre>

       <script>
           document.getElementById('run').addEventListener('click', async () => {
               const input = document.getElementById('input').value;
               const outputElement = document.getElementById('output');

               // Call the Prompt API to run Gemini Nano
               const response = await window.promptAPI.run({
                   prompt: input,
                   model: 'gemini-nano'
               });

               outputElement.textContent = response.output;
           });
       </script>
   </body>
   </html>
