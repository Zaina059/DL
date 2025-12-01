# 🔐 CEN455 – IoT Security Project  
### *Secure vs Insecure MQTT Smart Door System*

This project implements two versions of a smart-door IoT system:  
1. **Insecure system** (plaintext messages, no protection)  
2. **Secure system** (AES encryption, RSA key exchange, DSA signatures, replay protection, ACLs)

We demonstrate several attacks on both systems:
- Replay Attack  
- Tampering Attack  
- Injection Attack  
- Eavesdropping  
- Timing comparison (secure vs insecure)


## 🚀 How to Run the Systems

### ▶️ Start Mosquitto Broker

## 🟦 Run the Insecure System
Open **three separate terminals**:
python insecure/controller.py
python insecure/actuator.py
python insecure/sensor.py

Then you can run any attack:
python insecure/attacks/replay.py
python insecure/attacks/tamper.py
python insecure/attacks/injection.py
python insecure/attacks/eavesdrop.py
python insecure/attacks/timing.py

All attacks **succeed** because the insecure system has:
- No encryption  
- No authentication  
- No replay protection

## 🟩 Run the Secure System
Open **three terminals**:
python secure/controller.py
python secure/actuator.py
python secure/sensor.py

Then run secure attacks:
python secure/attacks/replay.py
python secure/attacks/tamper.py
python secure/attacks/injection.py
python secure/attacks/eavesdrop.py
python secure/attacks/timing.py

All attacks are **blocked** because the secure system uses:
- AES-GCM encryption  
- RSA-encrypted AES session key  
- DSA digital signatures  
- Anti-replay counters  
- Constant-time sender verification  
- MQTT ACL access control  

The controller prints **“Secure packet rejected”** for invalid packets.

## ✔ Summary
- Insecure system = all attacks succeed  
- Secure system = all attacks are blocked  
- The project demonstrates IoT cryptography, message integrity, replay protection, and ACL-based access control.



