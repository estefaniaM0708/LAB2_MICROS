# LAB2_MICROS
# Comparación MicroPython vs Arduino IDE

El sistema de control de velocidad fue desarrollado en dos plataformas diferentes: **MicroPython** y **Arduino IDE**, utilizando el mismo hardware basado en ESP32. Ambas implementaciones tienen la misma lógica de control: adquisición de velocidad, procesamiento de señal, controlador PI y regulación mediante DAC.

## Comparación de implementaciones

| Característica | MicroPython | Arduino IDE |
|---|---|---|
| Microcontrolador | ESP32 | ESP32 |
| Lenguaje | Python | C++ |
| ADC | GPIO 35 (12 bits) | GPIO 35 (12 bits) |
| DAC | GPIO 25 | GPIO 25 |
| LCD | I2C 16x2 (0x27) | I2C 16x2 (0x27) |
| Teclado | Matricial 4x4 | Matricial 4x4 |
| Encoder | GPIO 32 y GPIO 26 | GPIO 32 y GPIO 26 |
| Período de control | 200 ms | 200 ms |
| Controlador | PI | PI |
| Ganancias | Kp=0.25, Ki=0.02 | Kp=0.25, Ki=0.02 |
| Filtrado | Promedio móvil de 10 muestras | Promedio móvil de 10 muestras |
| Velocidad máxima | 3000 RPM | 3000 RPM |

---

# Diferencias principales

## MicroPython

- Implementación más sencilla y rápida de modificar.
- Manejo de periféricos mediante librería `machine`.
- Temporización mediante `ticks_ms()`.
- Salida DAC mediante:

```python
dac.write(valor)
