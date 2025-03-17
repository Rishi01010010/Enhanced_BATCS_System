# 🚑 Enhanced BATCS for Ambulances 🚑  
**Real-Time Traffic Management for Emergency Response**  

Welcome to the Enhanced BATCS project, a cutting-edge traffic management system designed to optimize ambulance routes using AI and real-time data. Built with Python, this project integrates accident detection, congestion prediction, and route optimization into a sleek Tkinter-based GUI, ensuring emergency vehicles reach their destinations faster.

---

## 🛠️ Project Overview  
Enhanced BATCS leverages machine learning, deep learning, and the Google Routes API to tackle three critical traffic challenges: accident detection, future congestion prediction, and commuter route recommendations. With a user-friendly interface, this system empowers traffic authorities and commuters alike to make informed decisions in real-time.

---

## ✨ Key Features  
- **Accident Detection**  
  - **What:** Identifies accidents from video feeds instantly.  
  - **How:** Uses a ResNet50 + LSTM deep learning model to analyze video sequences.  
  - **Output:** Detects accidents with confidence scores and saves annotated videos.  

- **Future Congestion Prediction**  
  - **What:** Forecasts traffic congestion to preemptively adjust signals.  
  - **How:** Employs a LightGBM model with historical data, weather, and road events.  
  - **Output:** Predicts congestion levels as a percentage (e.g., 45.3%).  

- **Traffic Recommendations for Commuters**  
  - **What:** Suggests optimal routes to reduce congestion around emergency paths.  
  - **How:** Integrates Google Routes API for traffic-aware routing.  
  - **Output:** Provides distance, travel time, and traffic status for up to three routes.  

- **Interactive GUI**  
  - Built with Tkinter, offering a tabbed interface for seamless interaction with all features.  
  - Real-time results displayed with progress updates and error handling.  

---

## 🚀 Getting Started  

### 1. Prerequisites  
- Python 3.x installed.  
- Dependencies: `torch`, `joblib`, `pydantic`, `tkinter`, `requests`, `numpy`, `opencv-python` (see `future_prediction/requirements.txt`).  
- A valid Google Routes API key.  
- Network access for route recommendations.  

### 2. Setting Up  
Clone the repository and navigate to the project directory:  
```bash  
git clone <repository-url>  
cd Enhanced-BATCS  
```  

- **Install Dependencies:**  
  ```bash  
  pip install -r future_prediction/requirements.txt  
  ```  

- **Run the GUI:**  
  ```bash  
  python interface.py  
  ```  

### 3. Using the System  
- **Traffic Prediction:** Enter parameters (e.g., Traffic Density, Hour) and click "Predict Traffic."  
- **Accident Detection:** Upload a video, specify the model path, and click "Detect Accidents."  
- **Optimal Route:** Input source/destination coordinates and click "Find Optimal Route."  

### 4. Viewing Results  
- Results appear in the GUI’s text boxes with detailed outputs (e.g., congestion levels, accident timestamps, route details).  
- Annotated videos from accident detection are saved to your specified output path.  

---

## 💾 File Structure  
```bash  
Enhanced-BATCS/  
│  
├── interface.py               # Main GUI application  
├── optimal_route.py           # Google Routes API integration for route recommendations  
├── server.py                  # Flask server (optional frontend)  
│  
├── accident_detection/  
│   ├── main.py                # Accident detection logic  
│   ├── accident_detection_model.pt  # Pre-trained ResNet50 + LSTM model  
│   └── [video files]          # Sample/test videos (e.g., poori.mp4)  
│  
├── enhanced_batcs_frontend/  
│   ├── index.html             # Optional web frontend  
│   ├── script.js              # Frontend JavaScript  
│   ├── style.css              # Frontend CSS  
│   └── three.min.js           # Three.js for 3D effects  
│  
├── future_prediction/  
│   ├── api/main.py            # Congestion prediction API  
│   ├── models/lgbm_model.pkl  # Pre-trained LightGBM model  
│   ├── data/                  # Processed traffic data  
│   └── scripts/               # Preprocessing and training scripts  
```  

---

## 📝 Code Explanation  
- **interface.py:**  
  - Launches a Tkinter GUI with three tabs for each feature.  
  - Dynamically imports and runs prediction/detection/routing logic.  
  - Handles user inputs and displays results with real-time feedback.  

- **accident_detection/main.py:**  
  - Processes video frames using a pre-trained ResNet50 + LSTM model.  
  - Outputs accident detection results and annotated videos.  

- **future_prediction/api/main.py:**  
  - Validates inputs with Pydantic and predicts congestion using LightGBM.  
  - Returns congestion levels based on traffic, weather, and event data.  

- **optimal_route.py:**  
  - Queries the Google Routes API for real-time route options.  
  - Scores routes based on distance and delay, recommending the best one.  

---

## 🌐 Configuration Tips  
- **Model Paths:** Ensure `accident_detection_model.pt` and `lgbm_model.pkl` are in their respective directories or update paths in the code.  
- **API Key:** Replace the placeholder in `optimal_route.py` with your Google Routes API key.  
- **GPU Support:** Accident detection auto-detects CUDA if available; otherwise, it defaults to CPU.  

---

## 🛠️ How It Works  
- **Flow:**  
  1. Launch `interface.py` to access the GUI.  
  2. Input data for predictions, upload videos for detection, or specify coordinates for routes.  
  3. Results are processed in real-time and displayed in the GUI.  

- **Data Handling:**  
  - Predictions use validated inputs; detection saves video outputs; routes are fetched live from Google.  

---

## 🎯 Project Intent  
This project demonstrates advanced AI applications in traffic management, focusing on emergency response optimization. It’s ideal for showcasing skills in machine learning, deep learning, API integration, and GUI development—perfect for academic projects or professional portfolios.

---

## 🔧 Customization Ideas  
- **Enhanced GUI:** Add visualizations (e.g., maps for routes, graphs for congestion).  
- **Real-Time Feeds:** Integrate live traffic camera streams for accident detection.  
- **Mobile App:** Port the system to a mobile-friendly interface using Flask or Kivy.  
