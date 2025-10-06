
# 240W USB-PD 3.1 Sink Board (HUSB238A) for Xbox 360

This project is a 240 W USB Power Delivery 3.1 sink board built around the **HUSB238A** PD controller. It is designed to replace the original external power brick for the Xbox 360 console by negotiating high-power USB-C power delivery and providing the required voltages directly to the motherboard.  

The board supports all Xbox 360 hardware revisions, including the original **Xenon motherboard**, which requires the highest power delivery of all models. By using this board, you can power an Xbox 360 using a compact, modern USB-C PD 3.1 power supply instead of the large OEM unit.

---

## Features

- **USB-PD 3.1 Sink:** Requests and negotiates up to **240 W** (48 V × 5 A) from a compliant USB-C power supply.
- **HUSB238A Controller:** Handles USB-PD 3.1 Extended Power Range (EPR) communication and profile selection.
- **Two USB-C Ports:**
  - **Top Port (Power Input):** Connect a USB-PD 3.1 power supply here. This is the board’s primary power input.
  - **Bottom Port (RP2040 Programming):** Dedicated to programming and debugging the onboard RP2040 microcontroller. **This port does not negotiate power and should not be used as a power source.**

---

## USB-C Power and Cable Requirements

USB-C power delivery depends on both the capabilities of the power source and the cable used. To reliably power an Xbox 360, you need:

- **Power Supply:** Must support **USB-PD 3.1 EPR** and be capable of delivering **up to 48 V at 5 A (240 W)**.  
- **Cable:** Must be **EPR-rated (240 W)**. Standard USB-C cables (commonly rated for 60 W or 100 W) will not provide sufficient power and may prevent negotiation.  
- **16AWG Wire:** You **MUST** use properly rated wire for high amperage if you want to minimize the risk of injury to yourself or your surroundings.

Failure to use properly rated components can result in insufficient power delivery, system instability, or a failure to power on the console.

---

## Use Case: Powering an Xbox 360

This board is specifically designed to supply power to Xbox 360 consoles, including:

- **Original Xenon motherboard:** The most power-hungry revision of the Xbox 360.
- **Falcon, Jasper, and Trinity revisions:** Later models that require less power but are fully supported.


---

## Board Connections

| Port | Function | Description |
|------|----------|-------------|
| **Top USB-C** | Power Input | Connect a USB-PD 3.1 power supply (240 W recommended). This port handles all power negotiation via the HUSB238A. |
| **Bottom USB-C** | RP2040 Programming | For uploading firmware or debugging. This port does not supply power to the board. |
|**PD_EN**| Power Delivery Enable| For activating the main power rail when the power button on the console is pressed |
|**12V**| 12V Power Rail | Main Power |
|**5V_STD**| 5V Standby Power | Standby power for the SMC|
|**GND/GND_1**| Ground| Common Ground | 
---

## Getting Started

1. Connect a **240W USB-PD 3.1 power supply** to the **top USB-C port** using a **240 W-rated EPR USB-C cable**.
2. The **HUSB238A** controller will negotiate the proper voltage and current from the power supply.
3. The board will output the required power rails to the Xbox 360 motherboard.
4. (Optional) Connect the **bottom USB-C** port to a PC to program or debug the onboard RP2040.

---

## Recommended Applications

- Powering original Xbox 360 consoles, including Xenon-based systems, with a modern USB-C power source.
- Building compact, portable power solutions for modified or repaired consoles.
- Supplying power for testing and development environments without the original Xbox 360 power brick.
---
## Safety Notice

This board negotiates and delivers high-power DC up to **48 V at 5 A**. Incorrect wiring, an under-rated power supply, or insufficient cable quality can cause malfunction or damage to the Xbox 360 console. Always verify your power source, cable ratings, and connections before use.
