# 🎓 Deepfake Detection: The Ultimate Student Study Guide 🧠🔍

Welcome, student! This guide is designed to help anyone—even a 10th-grade student—understand exactly how this Deepfake Detection project works. We will break down every folder, every file, and every function into simple, easy-to-understand language.

---

## 📂 Part 1: The "House" (Folders)
Think of the project as a house. Each folder is a different room with a specific purpose.

1.  **`ml_app/`**: This is the **Brain** of the house. It contains the logic that makes the website work and the AI that detects deepfakes.
2.  **`project_settings/`**: This is the **Control Panel**. It tells the project how to connect to the database, where to find images, and what the security rules are.
3.  **`models/`**: This is the **Knowledge Library**. It contains pre-trained AI files (`.pt` files). The AI "studied" thousands of real and fake videos to create these files.
4.  **`static/`**: This is the **Decoration Box**. It holds things like images, CSS (styling), and JavaScript (animations) that make the website look professional.
5.  **`templates/`**: This is the **Blueprint Collection**. It contains HTML files, which are the skeletons of the web pages you see.
6.  **`uploaded_videos/`**: This is the **Incoming Mailbox**. When you upload a video, it sits here while the AI looks at it.
7.  **`uploaded_images/`**: This is the **Photo Album**. The AI takes "snapshots" (frames) of the video and saves them here to show you later.
8.  **`venv/`**: This is the **Toolbox**. It contains all the Python libraries (like PyTorch and Django) needed to run the project.

---

## 📄 Part 2: The "Instruction Manual" (Files)
Each file has a specific job to do.

### Root Files:
-   **`manage.py`**: The "Start Button." You run this to turn on the website.
-   **`requirements.txt`**: A "Shopping List" of all the Python tools needed.
-   **`db.sqlite3`**: A "Diary" where the project remembers small details (like your session).
-   **`PROJECT_STUDY_GUIDE.md`**: (This file!) Your map to the project.

---

## 🧠 Part 3: Deep Dive into `ml_app/` (The Brain)
This is where the magic happens. Let's look at the most important file: `views.py`.

### 1. `class Model(nn.Module)` (The AI Architect)
-   **What it is**: The design of the Artificial Intelligence.
-   **How it works**: 
    -   It uses **ResNext50**: A famous AI that is amazing at "seeing" details in images (like eyes, nose, skin texture).
    -   It uses **LSTM**: A "memory" AI. It doesn't just look at one frame; it looks at a *sequence* of frames to see if the movement looks natural or glitchy.
-   **Modify it**: If you want to change the "brain size," you would change `hidden_dim` or `lstm_layers`.

### 2. `class validation_dataset(Dataset)` (The Video Preparer)
-   **What it is**: It gets the video ready for the AI.
-   **Functions**:
    -   `frame_extract`: Chops the video into individual photos (frames).
    -   `__getitem__`: Finds the face in each photo using a "face detector" and crops it so the AI only sees the face, not the background.

### 3. `def predict_page(request)` (The Judge)
-   **What it is**: The main function that runs when you click "Analyze."
-   **Step-by-Step**:
    1.  It grabs the video you uploaded.
    2.  It asks the AI to look at the frames.
    3.  It calculates a **Confidence Score** (0% to 100%).
    4.  It tells the website to show the "REAL" (Green) or "FAKE" (Red) result.

---

## 🎨 Part 4: The "Face" (Frontend)
Located in `templates/` and `static/`.

-   **`base.html`**: The "Global Skeleton." It contains the Dark Mode colors and the background animations that appear on every page.
-   **`index.html`**: The "Welcome Mat." This is where the "Ingest Evidence" (Upload) box is located.
-   **`predict.html`**: The "Lab Report." It shows the final AI verdict, the probability bar, and the heatmaps.
-   **`face-api.js`**: A JavaScript tool that draws the green/red boxes around faces while the video plays in your browser.

---

## 🛠️ Part 5: How to Change Things (For Students)
Want to experiment? Here is how:

1.  **Change the Website Colors**:
    -   Open `templates/base.html`.
    -   Look for Tailwind classes like `bg-slate-950` or `from-brand-600`.
    -   Change `brand-600` (Blue) to `purple-600` or `emerald-600` to see the site change color!

2.  **Change the Title**:
    -   Open `templates/nav-bar.html` or `index.html`.
    -   Search for "DEEPFAKE DETECTION" and type your own name instead.

3.  **Change the AI Sensitivity**:
    -   In `ml_app/views.py`, look for the `predict` function.
    -   The AI gives a number. You can change how it decides what is "Fake" by adjusting the logic in the `predict_page`.

4.  **Change the Scanning Speed**:
    -   In `index.html`, look for the "Scan Depth" slider. You can change the `min`, `max`, and `step` values to allow more or fewer frames.

---

## 🚀 Part 6: Summary of the "AI Recipe"
If you want to explain this to a friend, just say:
1.  **Input**: We give the computer a video.
2.  **Cutting**: We cut the video into pictures.
3.  **Focusing**: We find the faces in those pictures and zoom in.
4.  **Thinking**: The AI (ResNext + LSTM) checks if the face looks like a real human or a computer-generated one.
5.  **Output**: We show a professional report saying "REAL" or "FAKE."

**Congratulations! You now understand one of the most advanced AI technologies in the world!** 🌟🧪
