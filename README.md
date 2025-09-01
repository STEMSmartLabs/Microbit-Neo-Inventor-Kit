
# Neo Inventor Kit for micro:bit (MakeCode Extension)

Blocks and helpers for the **Neo Inventor Kit**: Servo, NeoPixel ring, Ultrasonic, Fan (DC), Buzzer, LDR, Switch, Trimpot, and OLED (via dependency).  
After installing, blocks appear under the **Neo Inventor Kit** toolbox category in MakeCode.

> This package depends on two official/community extensions:
> - **neopixel** (Microsoft) for WS2812/NeoPixel
> - **oled** (STEM Smart Labs) for SSD1306 OLED display

## Install
In MakeCode (micro:bit):
- **Extensions →** search for this repo URL once you publish it on GitHub *or* copy the folder into local PXT.
- After install, look for **Neo Inventor Kit** in the toolbox.

## Examples
Open these from the **Examples** section of this package's docs (once published), or copy the code below.

### Servo Sweep
```blocks
neoinventor.setServoAngle(AnalogPin.P0, 0)
basic.pause(500)
neoinventor.setServoAngle(AnalogPin.P0, 90)
basic.pause(500)
neoinventor.setServoAngle(AnalogPin.P0, 180)
```

### NeoPixel Rainbow
```blocks
let ring = neoinventor.createNeoPixel(DigitalPin.P8, 16)
ring.showRainbow(1, 360)
basic.forever(function () {
    ring.rotate(1)
    ring.show()
    basic.pause(50)
})
```

### Ultrasonic Distance + OLED
```blocks
oled.init(128, 64)
basic.forever(function () {
    let d = neoinventor.ultrasonicCm(DigitalPin.P1, DigitalPin.P2)
    oled.clear()
    oled.showString("Dist: " + d + "cm", 0, 0)
    basic.pause(200)
})
```

### Fan Speed
```blocks
neoinventor.setFan(AnalogPin.P12, 50)
basic.pause(1000)
neoinventor.setFan(AnalogPin.P12, 100)
basic.pause(1000)
neoinventor.setFan(AnalogPin.P12, 0)
```

### Buzzer Tone
```blocks
neoinventor.buzzerTone(AnalogPin.P0, 880, 500)
```

---

## Pin Notes
Your board/wiring may differ between kits/labs. All functions allow choosing pins in the Blocks editor.

## License
MIT
