# BCA188-# Laboratory Activity 9: ESP32 Wi-Fi Manager

**Name:** Aiza Kate D. Buale
**Assigned Number:** 2064  
**ESP32 AP Name:** BCA188-ESP32-TEST  

---

## 1. Practice Tasks & Results
| Task | What to do | What you observe |
| :--- | :--- | :--- |
| **1. Wrong password** | Enter a wrong password on the setup page. | The Serial Monitor displayed `[ERROR] Connect to new AP Failed`, showing that the ESP32 rejected the invalid password and returned to setup mode. |
| **2. Reset settings** | Hold the BOOT button for 3 seconds while the board is running. | Holding the BOOT button executed `wm.resetSettings()`, clearing the saved network credentials from non-volatile memory (NVS) and restarting the board into Access Point mode. |
| **3. Change the name** | Change the network name, upload, and check your phone’s Wi-Fi list. | After changing the SSID parameter in code to `BCA188-ESP32-TEST`, the updated AP name immediately appeared in the phone's available Wi-Fi list. |
| **4. Different network** | Reset the board, then connect to your phone hotspot. | The captive portal successfully accepted the phone hotspot credentials (`dughan gahuot`) and connected with a new assigned IP address (`10.202.94.167`). |

---

## 2. Screenshots & Evidence

### Portal Setup Page (Phone)
<img width="1080" height="1506" alt="image" src="https://github.com/user-attachments/assets/6fef6bea-e247-4051-9fb8-6e3c67a06f06" />


### Serial Monitor (Connected State with IP Address)
<img width="1918" height="1020" alt="image" src="https://github.com/user-attachments/assets/e6bf16d6-d80a-45c5-b137-692f58b5e9a2" />

---

## 3. Key Explanation

The ESP32 connected to a different network without changing the code because the `WiFiManager` library saves the updated Wi-Fi credentials directly into the board's non-volatile storage (NVS), allowing it to dynamically retrieve new settings across reboots.
