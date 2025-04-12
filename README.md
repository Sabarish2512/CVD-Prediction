# CVD-Prediction
# 🫀 CVD Prediction IoT System using AWS & ESP32

An AI-based wearable health monitoring system that detects cardiovascular disease (CVD) risk using real-time sensor data from ESP32 and cloud intelligence via AWS.

## 🔧 Hardware Components
- ESP32 (NodeMCU)
- MAX30102 – Heart Rate & SpO2
- AD8232 – ECG Signal
- MPU6050 – Gait Analysis (Fall Detection)

## ☁️ AWS Integration
- **AWS IoT Core** – Secure sensor data ingestion
- **AWS Lambda** – Preprocessing and ML model trigger
- **AWS SageMaker** – CNN/LSTM-based CVD prediction
- **AWS SNS** – Emergency alert (SMS/Email)
- **DynamoDB** – Store time-series health records

## 📊 Data Flow

1. ESP32 reads sensor values
2. Publishes data to AWS IoT Core (MQTT)
3. AWS Lambda processes incoming JSON payload
4. Triggers SageMaker ML endpoint for CVD prediction
5. High-risk alerts sent via AWS SNS
6. Historical data stored in DynamoDB

## 🧠 Model
Trained CNN on labeled ECG images (PTB-XL dataset) for real-time disease prediction. Integrated LSTM for sequence analysis in fall detection.

## 🔒 Security
- X.509 certificates for device authentication
- Encrypted TLS connections

## 📎 Sample Payload
```json
{
  "heartRate": 82.0,
  "spo2": 96.3,
  "ecg_signal": [0.82, 0.78, 0.80],
  "fall_detected": false
}
