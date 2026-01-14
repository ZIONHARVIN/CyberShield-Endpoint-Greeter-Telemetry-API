# CyberShield-Endpoint-Greeter-Telemetry-API
A lightweight Python FastAPI endpoint service for macOS that delivers audible system startup feedback and real-time system telemetry via a REST API. Designed to operate as a local endpoint agent within a security-focused home lab environment.
Features
 - Sci-Fi Startup Audio
 - Plays a non-blocking sci-fi system startup sound using native macOS tooling (afplay)
 - System Telemetry
 - CPU utilization
 - System uptime
 - Logged-in user context
 - Local time awareness
REST API
-Simple /greet endpoint for triggering telemetry and audio
OS-Native Execution
- Uses macOS-native subprocess handling
- No external audio libraries required
 Security-Aware Design
 - Built and tested within a segmented lab network
 - Designed to run only in authorized user sessions

Architecture Overview
   User Session
     │
     ├── FastAPI (Uvicorn)
     │     ├── System Telemetry (psutil)
     │     ├── Time Logic (datetime)
     │     └── Audio Trigger (afplay)
     │
     └── Local REST Endpoint (/greet)

 Project Structure
cybershield-greeter/
├── main.py
├── assets/
│   └── startup.mp3
├── venv/
└── README.md

Technologies Used
- Language: Python 3
- Framework: FastAPI
- Server: Uvicorn
- Libraries: psutil
- OS: macOS
- Audio: afplay (native macOS)

  Security Notes
- Designed for local execution only
- Intended to run within authorized user sessions
- Audio execution uses non-blocking subprocesses


Future Enhancements
- VLAN-aware audio modes (work vs pentest)
- Token-based API authentication
- Centralized logging
- LaunchAgent support for controlled startup execution
- Endpoint posture reporting

 Use Cases
- Endpoint automation demos
- Security lab tooling
- System awareness utilities
- Portfolio project demonstrating:
- API design
- OS integration
- Process control
- Security-conscious scripting
