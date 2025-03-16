# 🚑 Enhanced BATCS for Ambulances 🚑
### **AI-Powered Traffic Management for Emergency Response**

Welcome to the **Enhanced BATCS (Basic Adaptive Traffic Control System)** project, a cutting-edge solution designed to optimize ambulance routes using advanced AI and real-time traffic insights. Built with Python and integrated with powerful tools like Google Routes API, this project tackles traffic challenges to ensure ambulances reach their destinations faster.

---

## 🛠️ Project Overview
The Enhanced BATCS system leverages machine learning, computer vision, and real-time APIs to address key limitations in traditional traffic control systems. This prototype empowers emergency vehicles by predicting congestion, detecting accidents, and recommending optimal routes for commuters—freeing up critical pathways for ambulances.

---

## ✨ Key Features
- **Accident Detection**  
  - **What:** Real-time accident detection from video feeds.  
  - **How:** Uses a ResNet50 + LSTM deep learning model to analyze video sequences, outputting accident probabilities and annotated videos.  
  - **Why:** Alerts authorities instantly, enabling rapid response and route prioritization.

- **Future Congestion Prediction**  
  - **What:** Predicts traffic congestion before it happens.  
  - **How:** Employs a LightGBM model with inputs like historical traffic data, weather, and events, delivering congestion rates in percentage.  
  - **Why:** Preemptively adjusts traffic signals to clear paths for ambulances.

- **Traffic Recommendations for Commuters**  
  - **What:** Provides personalized, traffic-aware route suggestions.  
  - **How:** Integrates Google Routes API to compute optimal routes based on live traffic, outputting distance, time, and traffic status.  
  - **Why:** Diverts commuter traffic, reducing congestion around emergency routes.

- **Frontend Dashboard:** A sleek, 3D-animated interface built with Three.js for an immersive user experience.  
- **Backend Integration:** Flask-powered API connects all components seamlessly.

---

## 🚀 Getting Started

### 1. Prerequisites
- Python 3.x installed on your system.
- Dependencies: `torch`, `joblib`, `opencv-python`, `requests`, `flask`, `numpy`, `pydantic`, `three.js`.
- A valid Google Routes API key.
- A network connection for API calls.

### 2. Setting Up
#### Backend
- Clone the repository:
  ```bash
  git clone <repository-url>
  cd enhanced-batcs
  ```
- Install dependencies:
  ```bash
  pip install -r requirements.txt
  ```
- Run the server:
  ```bash
  python server.py
  ```

#### Frontend
- Open `enhanced_batcs_frontend/index.html` in a browser.
- Ensure the server is running at `http://localhost:5000`.

### 3. Using the System
- **Accident Detection:** Upload a video to detect accidents and view results in real-time.  
- **Congestion Prediction:** Input traffic parameters to get congestion forecasts.  
- **Route Recommendations:** Enter source and destination coordinates for optimal routes.  

### 4. Viewing Results
- Outputs are displayed on the dashboard and optionally saved (e.g., annotated accident videos).

---

## 💾 File Structure
```bash
enhanced-batcs/
├── server.py                   # Flask API server
├── enhanced_batcs_frontend/    # Frontend files
│   ├── index.html             # Main HTML
│   ├── style.css              # Styling
│   └── script.js              # 3D animations & API calls
├── future_prediction/         # Congestion prediction
│   └── models/
│       └── lgbm_model.pkl     # LightGBM model
└── accident_detection/        # Accident detection
    └── accident_detection_model.pt  # PyTorch model
```

---

## 📝 Code Explanation
- **server.py:** Hosts the Flask API, integrating all ML models and API calls.  
- **Accident Detection (Solution 4):** Processes video frames with a deep learning model to detect accidents.  
- **Future Congestion Prediction (Solution 1):** Uses LightGBM to predict congestion based on manual inputs.  
- **Traffic Recommendations (Solution 3):** Queries Google Routes API for real-time route optimization.  
- **Frontend:** A Three.js-powered 3D dashboard with dynamic panels for user interaction.

---

## 🌐 System Configuration
- **Model Paths:** Ensure model files (`lgbm_model.pkl`, `accident_detection_model.pt`) are in the correct directories.  
- **API Key:** Replace `YOUR_GOOGLE_API_KEY` in `server.py` with your Google Routes API key.  
- **Network:** Runs locally on `localhost:5000`—modify for network deployment if needed.

---

## 🛠️ How It Works
1. **Accident Detection:** Upload a video, and the system processes it frame-by-frame to identify accidents.  
2. **Congestion Prediction:** Enter traffic data, and receive a congestion forecast to adjust signals.  
3. **Route Recommendations:** Input coordinates, and get the best routes to ease traffic flow.  
4. **Real-Time Dashboard:** Interact with all features via a futuristic 3D interface.

---

## 🎯 Project Intent
This project demonstrates the power of AI in transforming traffic management for emergency services. It showcases skills in machine learning, computer vision, API integration, and frontend design—perfect for academic projects or professional portfolios.

---

## 🔧 Customization
Enhance the project with:  
- **GUI Expansion:** Add interactive maps or live video feeds.  
- **Vehicle Prioritization:** Integrate RFID or CV for emergency vehicle detection (Solution 2 placeholder).  
- **Scalability:** Deploy on a cloud server for real-world use.
