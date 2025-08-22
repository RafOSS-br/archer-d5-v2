# Archer D5 v2 - Hardware Documentation

## Component Summary

| Component     | Model / Marking    | Details                                     |
|---------------|--------------------|---------------------------------------------|
| **CPU/SoC**   | Broadcom BCM6318B0 | MIPS BCM3302 @ 333 MHz, DSL CPE SoC         |
| **RAM**       | 16 MB SDRAM        | 166 MHz                                     |
| **Flash**     | Winbond W25X16     | 2 MB SPI NOR                                |
| **Switch/PHY**| Integrated         | Inside BCM6318 (bcmsw driver)               |
| **Wi-Fi**     | Not detected       | PCIe disabled; some revisions may have BCM4352KMLHG |
| **Magnetics** | HST-48002SAR       | Ethernet transformer for RJ45 isolation     |
| **Other**     | –                  | Passive components (Bob Smith termination, EMI caps) |

## Interfaces
- **UART**:  
  - Location: ![Here](images/uart.png)  
  - Voltage: 3.3 V (logic level, do not connect external VCC)  
  - Baudrate: **115200 8N1**  

## Ethernet Front-End

**Bob Smith termination:** resistors marked *85X* (EIA-96), **75 Ω ±1%**, connected from each differential pair (after magnetics) to a common node.  
Measured in-circuit: ~100–107 Ω (expected due to parallel paths).  
Function: dissipates common-mode noise from the cable side.  

**Capacitor C434:** ceramic, connected from the common node of the 75 Ω network to chassis ground.  
Function: shunts **common-mode noise** to ground (EMI/EMC suppression).  
Typical value: **1–4.7 nF**.  

### Simplified schematic
```

PHY → Magnetics (HST-48002SAR) → RJ45
        │
        75 Ω network
        │
        C434
        │
        Chassis GND
```

## Notes
- Shielding covers removed for analysis.  
- Heatsinks mounted over SoC.  
- Boot logs confirm: **BCM6318B0 + 16 MB RAM + 2 MB SPI Flash**.  
- No Wi-Fi device detected in this firmware build.  