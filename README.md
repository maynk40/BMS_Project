# Dynamic Cell Balancing System Using Arduino and PCA9685

This project demonstrates an **active cell balancing mechanism** using **Arduino Nano** and **dual PCA9685 modules**. It explores different approaches to balance the discharge cycles of two cells effectively, ensuring optimal performance and longevity. The system alternates a servo motor load between two cells using time-based and voltage-based switching techniques.

---

## **Project Title**
Dynamic Cell Balancing System Using Arduino and PCA9685

---

## **Features**
1. **Time-Based Switching**: Alternates between cells every 30 seconds, ensuring equal discharge over time.
2. **Voltage-Based Switching**: Selects the cell with the higher voltage to prevent over-discharge of the weaker cell.
3. **Hybrid Approach**: Combines voltage and time-based techniques for better balancing and efficiency.

---

## **Components Used**
| **Component**              | **Quantity** | **Purpose/Use**                                                                 |
|-----------------------------|--------------|---------------------------------------------------------------------------------|
| Arduino Nano               | 1            | To control the switching logic and communicate with PCA9685 modules.           |
| PCA9685 PWM Module         | 2            | To generate PWM signals to control the servo motor.                             |
| Futaba S3003 Servo Motor   | 1            | To demonstrate the operation controlled alternately by the cells.              |
| Resistors                  | 2            | Used to limit current or for pull-up logic in the circuit.                      |
| Jumper Wires               | As Required  | To establish connections between components on the breadboard.                 |
| Breadboard                 | 1            | To prototype and connect components without soldering.                         |
| Multimeter                 | 1            | To measure cell voltages during the experiment.                                |
| USB Cable                  | 1            | To upload the code to the Arduino Nano and power the microcontroller.          |

---

## **Experiment Summary**

### **Experiment 1: Time-Based Switching**
- **Objective**: Demonstrate cell balancing using fixed time intervals for switching without considering voltage levels.
- **Setup**: 
  - Two cells (e.g., Ultra Alkaline) alternately power a servo motor for 30 seconds each.
  - Process is repeated for 30 cycles.
- **Observations**: 
  - Initial voltages: Cell 1 = 3.83V, Cell 2 = 3.82V.
  - Final voltages: Cell 1 = 1.68V, Cell 2 = 2.81V.
- **Conclusion**: Time-based switching alone fails to balance cells effectively, as SOC levels and load sharing are not accounted for.

### **Experiment 2: Time-Based Switching with Lithium-Ion Cells**
- **Objective**: Repeat Experiment 1 with identical, fully charged lithium-ion cells.
- **Setup**: Both cells start at 100% SOC and 3.99V potential.
- **Observations**: 
  - Final voltages: Cell 1 = 3.93V, Cell 2 = 3.91V.
- **Conclusion**: While more effective due to matched SOC, slight voltage differences arise due to load sharing, aging, and capacity variations.

### **Experiment 3: Hybrid Approach (Theoretical)**
- **Objective**: Combine voltage and time-based switching for enhanced cell balancing.
- **Setup**:
  - Voltage-based switching prioritizes the cell with higher voltage when a significant difference exists.
  - Time-based alternation ensures fairness once voltage levels are balanced.
- **Advantages**:
  - Real-time adjustments prevent over-discharge and improve efficiency.
  - Offers adaptability and fairness in long-term usage.
- **Note**: This approach was not implemented due to the unavailability of precision potentiometers.

---

## **Advantages of the Hybrid Approach**
1. **Protection Against Imbalance**: Prevents over-discharge of weaker cells while ensuring equal usage over time.
2. **Improved Efficiency**: Actively balances cells based on both voltage and time.
3. **Real-Time Monitoring**: Enables dynamic adjustments during operation.

---

## **Code**
The code for this project is available on the following link:  
[Arduino IDE Code](https://drive.google.com/drive/folders/1VzBejXmJDqrnN4v9cj8lPg3IIUGGDNJE?usp=sharing)

---

## **Applications**
- Battery Management Systems (BMS) for multi-cell setups.
- Robotics and IoT applications requiring efficient power distribution.
- Educational demonstration of cell balancing techniques.

---

## **Limitations**
1. **SOC Tracking**: The experiments did not include direct SOC measurement, relying solely on voltage levels.
2. **Load Sharing**: Inconsistencies in current drawn by the servo motor can affect balancing.
3. **Component Constraints**: Precision potentiometers and advanced voltage sensors were unavailable.

---

## **Future Enhancements**
1. Integrate SOC estimation for more accurate balancing.
2. Incorporate real-time cloud monitoring for remote diagnostics.
3. Expand the system for larger multi-cell battery setups with dynamic load distribution.

---

## **License**
This project is licensed under the MIT License. See `LICENSE` for details.

---


