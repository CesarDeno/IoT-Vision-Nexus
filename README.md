# IoT-Vision-Nexus: Cyber-Physical System & Node-RED integration

A comprehensive IoT solution fusing real-time ESP32 telemetry, local Computer Vision (DeepStack), orchestrated via Node-RED with GenAI reporting.

## 🏗️ Tech Stack

-  **Edge:** ESP32 (ESP-IDF + Digital Filtering)
-  **Vision:** DeepStack (Local Face/Object Detection)
-  **Logic:** Node-RED & MQTT flow orchestration
-  **GenAI:** ChatGPT (Incident Reporting)

## 🚀 Installation & Execution

### 1. Python Environment

```bash
python -m venv .venv
.venv\\Scripts\\activate
pip install -r requirements.txt
```

### 2. Infrastructure (Docker)

Starts MQTT, MongoDB, Node-RED, and DeepStack.

```bash
docker-compose up -d
```

## 3. Dependency Setup (Node-RED)

The project requires additional nodes. Once the containers are up:

1. Install dependencies:

   ```bash
   docker exec -it nodered_core npm install
   ```

2. Restart Node-RED:
   ```bash
   docker restart nodered_core
   ```

## 🔌 Services & Credentials

| Service        | URL/Host                | Port  | User        | Password |
| :------------- | :---------------------- | :---- | :---------- | :------- |
| **Node-RED**   | `http://localhost:1880` | 1880  | -           | -        |
| **DeepStack**  | `http://localhost:5000` | 5000  | -           | -        |
| **MQTT (TCP)** | `localhost`             | 1883  | (Anonymous) | -        |
| **MQTT (WS)**  | `localhost`             | 9001  | (Anonymous) | -        |
| **API REST**   | `http://localhost:8000` | 8000  | -           | -        |
| **MongoDB**    | `localhost`             | 27017 | `iot_admin` | `940194` |
