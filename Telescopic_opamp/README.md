# Telescopic CMOS Operational Amplifier  
### Sky130A | Xschem | NGSpice

---

## 📌 Project Overview
This project presents the **design and AC performance analysis of a Telescopic CMOS Operational Amplifier**
using the **SkyWater 130nm (Sky130A) PDK**.  
The schematic is implemented in **Xschem**, and simulations are carried out using **NGSpice**.

The main objective is to study the **high-gain characteristics, frequency response**, and the effect of
**bias voltage, bias current, and transistor sizing (W/L)** on the amplifier performance.

---

## 🛠️ Tools & Technology
- **Xschem** – Schematic capture  
- **NGSpice** – Circuit simulation  
- **SkyWater 130nm (Sky130A) PDK**  
- **Linux environment**

---

## 🧩 Circuit Architecture
The Telescopic Op-Amp is a **single-stage, high-gain amplifier** that uses cascoding to increase output resistance.

### 🔹 Key Blocks
- **NMOS differential input pair**
- **NMOS and PMOS cascode transistors**
- **Current source tail bias**
- **Single-ended output node**

### 🔹 Characteristics
- High intrinsic gain
- Low power consumption
- Limited output swing compared to two-stage op-amps
- Suitable for high-speed applications

---

## ⚙️ Simulation Setup

### AC Analysis
AC analysis is performed to evaluate the **gain vs frequency response**.

```spice
.ac dec 100 1 1e9
````

### Model Include

```spice
.lib <path_to_sky130_models>/sky130.lib.spice tt
```

---

## 📈 Simulation Results

### 🔹 Initial Gain–Frequency Response

* Moderate DC gain observed
* Early roll-off due to biasing and device sizing
* Limited bandwidth optimization

<img width="615" height="508" alt="image" src="https://github.com/user-attachments/assets/7a680de9-4f47-45d2-87d9-bcd2a56b61bb" />

---

### 🔹 Improved Gain–Frequency Response

After tuning the following parameters:

* Bias voltages
* Tail current
* Transistor W/L ratios

The amplifier shows:

* **Improved DC gain**
* Better frequency response
* Enhanced overall performance

<img width="708" height="540" alt="Screenshot 2025-11-27 235254" src="https://github.com/user-attachments/assets/618b8573-5de6-40e0-9b42-fcc7688127d8" />


---

## ✅ Performance Summary (Qualitative)

| Parameter | Observation                              |
| --------- | ---------------------------------------- |
| DC Gain   | Improved after bias & W/L tuning         |
| Bandwidth | Increased                                |
| Power     | Low (single-stage design)                |
| Stability | Inherently stable (single dominant pole) |

---

## 🧠 Design Insights

* Cascoding significantly increases output resistance → higher gain
* Proper biasing is critical for:

  * Keeping transistors in saturation
  * Maximizing gain
* Telescopic op-amps trade **output swing** for **high speed and gain**
* Single-stage nature avoids the need for Miller compensation


## 📚 Learning Outcomes

* Understanding telescopic op-amp architecture
* Hands-on experience with Sky130A PDK
* Biasing and sizing impact on analog performance
* AC analysis using NGSpice

---

## 📄 License

This project is intended for **educational and academic purposes only**.

## 🔍 How to Find the SKY130 Model File??

If you need to locate the SKY130 model file (`sky130.lib.spice`) on your Linux system, run this command:

```bash
sudo find / -type f -name "sky130.lib.spice" 2>/dev/null
```

This will search your entire filesystem and print the full path of the model file.
And select the appropriate path and copy to file in the schmatic.

##  How to Plot the frequency repsonse??
Enter this command in the after simulatig in the ngspcie command terminal
```bash
plot db(v(vout)/v(vip))
```
Change the names according to the pins you used in the schematic.
