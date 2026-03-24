# 🛡️ CampusGuard AI

**An AI-Driven Real-Time Surveillance Framework for Proactive Campus Security**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-2.3.3-green.svg)](https://flask.palletsprojects.com)
[![YOLOv11](https://img.shields.io/badge/YOLOv11-8.0.186-red.svg)](https://github.com/ultralytics/ultralytics)
[![CUDA](https://img.shields.io/badge/CUDA-Supported-brightgreen.svg)](https://developer.nvidia.com/cuda-toolkit)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 📋 Table of Contents
- [Overview](#overview)
- [Key Features](#key-features)
- [System Architecture](#system-architecture)
- [Technology Stack](#technology-stack)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage Guide](#usage-guide)
- [API Endpoints](#api-endpoints)
- [Project Structure](#project-structure)
- [Database Schema](#database-schema)
- [Troubleshooting](#troubleshooting)
- [Performance Benchmarks](#performance-benchmarks)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

## 🎯 Overview

**CampusGuard AI** is an intelligent, real-time surveillance system designed specifically for campus security. Leveraging state-of-the-art YOLOv11 object detection models, it provides proactive monitoring, anomaly detection, and incident management to ensure campus safety.

Unlike traditional CCTV systems that only record footage, CampusGuard AI **understands** what it sees—detecting potential threats, unusual behaviors, and security incidents in real-time. The system can identify fights, sleeping individuals, suspicious loitering, and mobile phone usage, making it an invaluable tool for modern campus security.

### Why CampusGuard AI?
- **Proactive Security**: Detect incidents before they escalate
- **Multi-Model Intelligence**: Specialized models for different threat types
- **Real-Time Processing**: Instant alerts and notifications
- **Cost-Effective**: Runs on existing hardware with optional GPU acceleration
- **User-Friendly**: Intuitive web interface for security personnel

## ✨ Key Features

### 🤖 Multi-Model AI Detection

| Model | Detection Capability | Confidence Threshold | Use Case |
|-------|---------------------|---------------------|----------|
| **Fight Detection** | Physical altercations, aggressive movements | 70% | Crowded areas, parking lots, sports complexes |
| **Sleep Detection** | Inactive/lying persons, drowsiness | 25% | Classrooms, libraries, lecture halls |
| **Suspicious Behavior** | Loitering (4+ minutes), unusual patterns | 90% | Restricted areas, after-hours zones |
| **Normal Detection** | Standard person/object tracking | 50% | General surveillance across campus |
| **Phone Detection** | Mobile device usage | 75% | Exam halls, restricted zones |

### 🎥 Multi-Camera Support
- **Webcam** (built-in laptop cameras) - Perfect for testing and small-scale deployment
- **External USB cameras** - Automatic device detection and indexing
- **IP cameras** via RTSP/HTTP streams - Support for existing CCTV infrastructure
- **Live streaming** with real-time frame processing
- **Frame caching** for efficient display and reduced bandwidth

### 🚨 Intelligent Incident Management
- **Configurable confidence thresholds** per model and per camera
- **Delay-based incident creation** prevents false positives and notification spam
- **Automatic evidence capture** with bounding boxes and timestamps
- **Severity classification** (Low, Medium, High, Critical) for prioritization
- **Complete incident lifecycle tracking** from detection to resolution
- **Base64 encoded evidence storage** for easy display and sharing
- **Video evidence paths** for larger incident files

### 📊 Real-Time Dashboard
- **Multi-camera monitoring grid** with individual controls
- **Per-camera model toggles** - Enable/disable models on the fly
- **Live FPS and detection statistics** for performance monitoring
- **Anomaly alerts** with browser notifications and sound alerts
- **Incident timeline** with evidence preview and quick actions
- **System status indicators** (GPU availability, model health)

### 🔐 Role-Based Access Control
| Role | Permissions |
|------|-------------|
| **Admin** | Full system control, user management, camera management, database operations |
| **Security** | Incident management, monitoring controls, report viewing |
| **Faculty/Student** | Limited access, incident reporting, basic dashboard view |

### ⚡ Performance Optimizations
- **CUDA/GPU acceleration** for 5-10x faster inference
- **Multi-threaded stream processing** for concurrent camera handling
- **Queue-based frame management** prevents bottlenecks
- **JPEG compression with configurable quality** balances speed and clarity
- **Optimized OpenCV backends** (DSHOW, MSMF, VFW) for Windows compatibility
- **Lazy loading** of models to reduce startup time

## 🏗️ System Architecture
