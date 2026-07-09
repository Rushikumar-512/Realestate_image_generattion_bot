# 🏠 AI Real Estate Image Enhancement Agent

  <b>🤖 Upload Property Image → 🧠 AI Analysis → ✨ Image Processing → 📲 Telegram Delivery</b>
</p>

---

## 🚀 About the Project

**AI Real Estate Image Enhancement Agent** is an automated AI workflow built using **n8n**.

The workflow allows a real estate agent or user to send a raw property image through a Telegram bot.

The AI automatically:

📸 Receives the property image

🧠 Analyzes the image using Gemini 2.5 Flash

✍️ Generates a professional image-enhancement prompt

🔀 Combines the original image and AI-generated prompt

☁️ Sends them to Cloudflare Workers AI

🎨 Processes the property image using FLUX.2 Klein 4B

🔄 Converts the Base64 API response into an image file

📲 Sends the final image back to the Telegram user

> No manual prompt entry is required.

---

# ⚡ Workflow Architecture

```mermaid
flowchart TD

    A["📲 User Sends Property Image"] --> B["🤖 Telegram Trigger"]

    B --> C["📥 Get File"]

    C --> D["🧠 Gemini 2.5 Flash AI Agent"]

    D --> E["✍️ Generate Enhancement Prompt"]

    C --> F["🔀 Merge Node"]
    E --> F

    F --> G["🌐 HTTP Request"]

    G --> H["☁️ Cloudflare Workers AI"]

    H --> I["🎨 FLUX.2 Klein 4B"]

    I --> J["🔢 Base64 Image Response"]

    J --> K["📁 Convert to File"]

    K --> L["📲 Telegram Send Photo"]

    L --> M["✅ Enhanced Image Delivered"]
