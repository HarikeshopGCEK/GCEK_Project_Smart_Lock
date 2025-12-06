## **1. Introduction**

Smart Locker is an IoT-based, keyless locker system that allows users to securely lock and unlock lockers using a mobile application. The system integrates ESP32, solenoid lock, sensors, a smart plug, and cloud services to provide secure, automated, and convenient storage.

---

## **2. Problem Statement**

- Students and staff carry expensive devices with no secure storage.
    
- Traditional lockers require keys → risk of loss, misuse, no logging.
    
- No real-time monitoring, no payment system, no digital management.
    

---

## **3. Proposed Solution**

A fully app-controlled smart locker with:

- Keyless access (unlock using mobile app)
    
- Secure electronic locking using solenoid + relay
    
- Real-time status via reed and limit switches
    
- Smart charging control using smart plug
    
- Integrated payment and authentication
    
- Cloud-based data sync and activity logs
    

---

## **4. Key Features**

- **Mobile App (Flutter)** for lock/unlock, status, payments
    
- **Real-time locker status** (door open/closed, lock engaged)
    
- **Secure communication** (AES encryption)
    
- **Usage history & notifications**
    
- **Battery backup** for power outages
    
- **Cost-effective** design (< ₹800–₹1000 per unit)
    

---

## **5. System Components**

### **Hardware**

- ESP32 (NodeMCU)
    
- Solenoid Lock (12V)
    
- Relay Module
    
- Magnetic Reed Switch
    
- Limit Switch
    
- Smart Plug
    
- Power Supply + Battery Backup
    

### **Software**

- Flutter Mobile Application
    
- Supabase / Firebase Authentication
    
- Blynk Cloud (for IoT control)
    
- ESP32 Firmware (Wi-Fi/Bluetooth communication)
    

---

## **6. System Architecture (Text Summary)**

1. User opens the mobile app.
    
2. Authenticates through Firebase/Supabase.
    
3. Selects locker → app checks availability.
    
4. App sends lock/unlock command to ESP32.
    
5. ESP32 activates relay → solenoid lock opens/closes.
    
6. Reed & limit switches provide real-time status feedback.
    
7. Smart plug manages charging power inside locker.
    
8. All events logged to the cloud.
    

---

## **7. Functional Requirements**

- App must send lock/unlock commands.
    
- Solenoid lock must operate only after successful authentication.
    
- Reed switch must detect door open/closed state.
    
- Limit switch must verify lock engagement.
    
- Payment must be completed before unlocking.
    
- App must show real-time locker status.
    

---

## **8. Non-Functional Requirements**

- Status updates must reach the app within 2 seconds.
    
- Communication must be encrypted.
    
- System must remain operational for 1 hour during power outage.
    
- Application must load within 2 seconds.
    

---

## **9. Project Timeline (Short Summary)**

- **Database restructuring**
    
- **Authentication testing**
    
- **ESP32–App data linking**
    
- **Real-time data integration**
    
- **UI updates & optimization**
    
- **Final testing and debugging**
    
- **Documentation & deployment**
    

---

## **10. Expected Outcome**

A working smart locker prototype with:

- Fully digital access
    
- Secure storage
    
- Charging support
    
- Real-time monitoring
    
- Cloud logging
    
- Payment integration
    

This prototype will be deployable within campus and scalable to a full commercial product.