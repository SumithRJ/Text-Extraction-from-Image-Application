# Text Extraction Flask App

A Flask-based web application for extracting and visualizing text from images. Users can upload images, perform OCR to extract text content, and view results within a responsive, Materialize CSS-powered interface.

---

## 🚀 Project Overview

This app enables:

- **Image Upload**: Securely upload image files (e.g., PNG, JPG) via a drag-and-drop or select interface.
- **Text Extraction**: Perform Optical Character Recognition (OCR) on the uploaded image to retrieve textual content.
- **Result Display**: Show extracted text on the same page styled with Materialize CSS.
- **Sample Data**: Includes a sample image to test the extraction workflow.
- **Deployment Ready**: Configured for Heroku deployment with `Procfile` and `runtime.txt`.

---

## 🧩 Repository Structure

```
Text Extraction Flask App/
├── app.py                  # Main Flask application setup and route definitions
├── config.py               # Configuration settings (e.g., secret keys, upload folder)
├── requirements.txt        # Python dependencies
├── Procfile                # Defines web process for Heroku deployment
├── readme.md               # (Old) project notes
├── sample_data/            # Sample images for quick testing
│   └── img.png
└── app/                    # Flask application package
    ├── __init__.py         # Initializes Flask app and registers blueprints
    ├── views.py            # View functions handling image uploads and OCR
    ├── static/             # Front-end assets
    │   ├── css/            # Materialize CSS files
    │   │   ├── materialize.css
    │   │   └── materialize.min.css
    │   ├── js/             # JavaScript libraries
    │   │   ├── materialize.js
    │   │   ├── materialize.min.js
    │   │   └── chart.js
    │   ├── images/         # UI background and icons
    │   │   └── white_bg.jpg
    │   └── uploads/        # Directory where user-uploaded images are stored
    └── templates/          # Jinja2 HTML templates
        └── index.html      # Main page template with upload form and result display
```

---

## 🔧 Technologies & Dependencies

- **Python 3.7+**  
- **Flask**: Web framework  
- **Werkzeug**: Secure filename handling  
- **pytesseract**: OCR engine wrapper  
- **OpenCV** (`cv2`): Image preprocessing  
- **Materialize CSS**: Responsive UI framework  
- **Chart.js**: Dynamic data visualization (if used for analytics)  
- **Gunicorn**: WSGI HTTP server (for production)  

Install all dependencies:

```bash
pip install -r requirements.txt
```

---

## 🛠️ Setup & Installation

1. **Clone the repository**  
   ```bash
   git clone https://github.com/your-username/text-extraction-flask.git
   cd "Text Extraction Flask App"
   ```

2. **Install dependencies**  
   ```bash
   python3 -m venv venv
   source venv/bin/activate    # Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Configure Tesseract Path**  
   - Ensure [Tesseract OCR](https://github.com/tesseract-ocr/tesseract) is installed on your system.  
   - If not in PATH, set `TESSERACT_CMD` in `config.py` to its executable location.

4. **Run the application (development)**  
   ```bash
   flask run
   ```
   Open <http://127.0.0.1:5000/> in your browser.

5. **Deployment (Heroku)**  
   ```bash
   heroku create
   git push heroku main
   heroku ps:scale web=1
   ```

---

## 📈 Usage

1. **Home Page**  
   - Use the upload button to select an image from your local machine.  
   - Click **Extract Text** to start OCR.

2. **Results**  
   - View the extracted text below the form.  
   - If enabled, view data visualizations (e.g., word frequency charts).

3. **Sample Run**  
   - Use `sample_data/img.png` to test the extraction pipeline immediately.

---

## 🔍 How It Works

- **app.py**  
  - Sets up Flask app, config, and routes.  
  - Defines `index` route for GET and POST methods.

- **views.py**  
  - `upload_image()`: Handles file storage, invokes OCR, and passes results to template.  
  - Implements error handling for non-image uploads.

- **config.py**  
  - Centralizes configuration variables like `UPLOAD_FOLDER`, `ALLOWED_EXTENSIONS`, and Tesseract command path.

- **Template (`index.html`)**  
  - Uses Materialize CSS components for a responsive upload form.  
  - Displays extracted text and optionally charts using Chart.js.

---

## 🚀 Next Steps & Enhancements

- Support for multiple language OCR.  
- Add preprocessing steps (thresholding, denoising) for better accuracy.  
- Store and manage upload history with a database (SQLite).  
- Implement user authentication for private data handling.  
- Extend API endpoints for programmatic access.

---

## 📬 Contact & Contributions

Contributions, issues, and feature requests are welcome!  
Please open an issue or submit a pull request.  
For questions or feedback, contact **sumithrjala@gmail.com**.
