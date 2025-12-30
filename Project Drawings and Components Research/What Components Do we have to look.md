## A. Power Switching & Electrical Safety

1. **EV-rated AC Contactor (40–63 A, 2-pole or 4-pole)**  
    **Purpose:**  
    Safely switches power to the EV charger or connected load.  
    **Reason:**  
    EV chargers draw high inrush current; normal relays can weld shut and are unsafe.
    
2. **RCBO / MCB (Type A, suitably rated)**  
    **Purpose:**  
    Over-current and earth-leakage protection.  
    **Reason:**  
    EV chargers can introduce DC leakage; Type A is mandatory for safety.
    
3. **Surge Protection Device (SPD – Type 2)**  
    **Purpose:**  
    Protects electronics from voltage spikes and lightning-induced surges.  
    **Reason:**  
    Grid disturbances can permanently damage controllers and sensors.
    
4. **Earthing Terminal and Ground Bus**  
    **Purpose:**  
    Proper protective earthing for enclosure and charger.  
    **Reason:**  
    Essential for EV safety and regulatory compliance.
    

---

## B. NILM Load Detection (Only for Car Charger)

5. **Split-Core Current Transformer (CT Clamp, 60A / 100A)**  
    **Purpose:**  
    Non-intrusive sensing of current drawn by the car charger.  
    **Reason:**  
    Enables NILM-based detection without cutting or modifying power lines.
    
6. **Precision Burden Resistor (Low temperature coefficient)**  
    **Purpose:**  
    Converts CT output current into a measurable voltage.  
    **Reason:**  
    Ensures stable and repeatable NILM measurements.
    
7. **RC Anti-aliasing Filter**  
    **Purpose:**  
    Filters high-frequency noise before ADC sampling.  
    **Reason:**  
    Improves waveform quality and NILM pattern accuracy.
    
8. **ADC Biasing Network (Mid-supply reference)**  
    **Purpose:**  
    Shifts AC waveform into ADC input range.  
    **Reason:**  
    Microcontroller ADCs cannot read negative voltages directly.
    

> Note: NILM is used only for **usage detection and pattern analysis**, not for billing-grade energy measurement.

---

## C. Control and Processing

9. **Microcontroller – ESP32**  
    **Purpose:**  
    Central controller for NILM processing, RFID logic, door detection, and mobile app communication.  
    **Reason:**  
    Adequate ADC performance, built-in Wi-Fi/Bluetooth, and sufficient processing power.
    
10. **Optocoupler (Logic to Contactor Isolation)**  
    **Purpose:**  
    Electrically isolates MCU from high-voltage switching circuitry.  
    **Reason:**  
    Protects low-voltage electronics from transients and faults.
    
11. **Contactor Driver Circuit (Transistor + Flyback Diode)**  
    **Purpose:**  
    Drives the contactor coil safely.  
    **Reason:**  
    MCU GPIO pins cannot directly handle coil current or voltage spikes.
    

---

## D. RFID-Based Charger Identification

12. **HF RFID Reader (13.56 MHz)**  
    **Purpose:**  
    Identifies authorized charger or vehicle tag.  
    **Reason:**  
    Provides access control and charger identification.
    
13. **RFID Tag (Mounted on Charger Plug or Handle)**  
    **Purpose:**  
    Acts as a unique identifier for the charger.  
    **Reason:**  
    Prevents unauthorized or incorrect charger usage.
    

---

## E. Physical Presence & Door Detection (Tamper Safety)

14. **Reed Switch + Magnet (Door Closed Detection)**  
    **Purpose:**  
    Detects whether the enclosure door is open or closed.  
    **Reason:**
    
    - Prevents operation when the enclosure is open
        
    - Detects tampering
        
    - Improves user and service safety
        
15. **Reed Switch / Hall Sensor (Charger Dock Presence Detection)**  
    **Purpose:**  
    Detects whether the charger is physically placed in its holder or removed.  
    **Reason:**  
    RFID confirms identity, but this sensor confirms **physical presence**.  
    Prevents spoofing and enables theft or misuse detection.
    

---

## F. Power Supply Architecture

16. **Isolated AC-DC SMPS (12 V or 24 V)**  
    **Purpose:**  
    Supplies power to control electronics.  
    **Reason:**  
    Electrical isolation from mains improves safety and noise immunity.
    
17. **DC-DC Buck Converter (to 5 V)**  
    **Purpose:**  
    Efficient step-down for logic supply rails.  
    **Reason:**  
    Reduces heat and improves efficiency.
    
18. **LDO Regulator (5 V → 3.3 V)**  
    **Purpose:**  
    Provides clean power to MCU ADC and RF sections.  
    **Reason:**  
    Reduces noise that can corrupt NILM signals and RFID communication.
    

---

## G. Optional but Recommended Safety Add-Ons

19. **Temperature Sensor (NTC or Digital)**  
    **Purpose:**  
    Monitors contactor or enclosure temperature.  
    **Reason:**  
    Enables thermal fault detection and preventive shutdown.
    
20. **Status LEDs / Buzzer**  
    **Purpose:**  
    Local indication of system state and fault conditions.  
    **Reason:**  
    Improves usability and diagnostics during maintenance.