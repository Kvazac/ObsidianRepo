## Selection Criteria
### General

- I/O: ≥3 SPI (IMU, sensors, radio), ≥2 CAN-FD (intra-vehicle + diagnostics), plenty of timers/PWM for TVC.
- Memory: Enough tightly-coupled SRAM for control/filters; consider external QSPI NOR + FRAM/MRAM for logs and fault counters.
- Clocking: Dual oscillators (HSE + LSE) with clock-failover; lock control loop timing to a hardware timer.
- Safety hooks: Independent watchdog (IWDG) + window watchdog (WWDG), ECC/parity where available, brown-out reset, robust boot-mode strapping.
- Thermals/grade: Prefer packages with –40…105/125 °C rating; avoid BGAs unless you control assembly/thermal profile tightly.
- *Determinism: Pin control and sensor busses on DMA-capable peripherals; reserve one core (or RTOS high-prio task) strictly for the control loop.* -ehh

### SW Team
- 

## Options:
1. STM32H745/755 (Cortex-M7 + M4, dual-core, 400–480 MHz)
	- **Why:** Clean core separation (M7 = control; M4 = I/O/FDIR), tons of timers, SPI/I²C/UART, CAN-FD, Ethernet, ample SRAM/Flash, DSP/FPU for filters.
	- **Use:** Great for **TMR** (3 identical boards/cores) or 2+1 hybrid (two identical primaries + diverse monitor on M4).
	- [STM32H745/755 Arm Cortex-M7+M4 Dual Core Microcontrollers (MCU) - STMicroelectronics](https://www.st.com/en/microcontrollers-microprocessors/stm32h745-755.html)
2. STM32H753/750 (single-core M7, 400–480 MHz)
	- **Why:** Maximum deterministic performance with simpler scheduling; fewer moving parts than dual-core.
	- **Use:** Pure **TMR** (same binary on three MCUs) with an external supervisor.
	- [STM32H743/753 Arm Cortex-M7 Microcontrollers (MCUs) - STMicroelectronics](https://www.st.com/en/microcontrollers-microprocessors/stm32h743-753.html)
3. STM32H563/H573 (Cortex-M33 @ ~250 MHz, TrustZone-M)
	- **Why:** Built-in security (secure boot, isolation) for command/auth and telecommands; still plenty fast for guidance/FDIR if loop rates are moderate.
    - **Use:** As a **secure I/O & comms/health node** alongside an H7 control primary, or as diverse monitor.
    - [STM32H563/573 - STMicroelectronics](https://www.st.com/en/microcontrollers-microprocessors/stm32h563-573.html)
4. STM32G474 (Cortex-M4 @ ~170 MHz, “power/control” MCU)
	- **Why:** Excellent high-res timers, fast ADCs, motor-control features; low power and wide temp options.
	- **Use:** **Actuator/servo driver companion** or low-rate safety monitor; also good as the “+1” diverse lane.
	- [STM32G474RE | Product - STMicroelectronics](https://www.st.com/en/microcontrollers-microprocessors/stm32g474re.html)