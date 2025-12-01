let index = 0
let demoMode = true
let soundDemoMode = false
let demoStep = 0
let currentDemo = 0
let fillDir = 1
let bouncePos = 0
let bounceDir = 1
let waveOffset = 0

let pinsList = [
    DigitalPin.P0, DigitalPin.P1, DigitalPin.P2,
    DigitalPin.P8, DigitalPin.P9, DigitalPin.P12,
    DigitalPin.P13, DigitalPin.P14, DigitalPin.P15, DigitalPin.P16
]

function updateDisplay(num: number) {
    basic.clearScreen()
    for (let i = 0; i < num; i++) {
        let x = i % 5
        let y = Math.floor(i / 5)
        led.plot(x, y)
    }
}

function allOff() {
    for (let p of pinsList) {
        pins.digitalWritePin(p, 0)
    }
}

input.onButtonPressed(Button.A, function () {
    // אם אנחנו במצב B או דמו - עצור ואפס הכל
    if (soundDemoMode || demoMode) {
        demoMode = false
        soundDemoMode = false
        allOff()
        index = 0
        updateDisplay(0)
        basic.pause(100)
        pins.digitalWritePin(pinsList[index], 1)
        index++
        updateDisplay(index)
    } else {
        // מצב רגיל - הוסף נורה
        if (index < pinsList.length) {
            pins.digitalWritePin(pinsList[index], 1)
            index++
            updateDisplay(index)
        } else {
            // הגענו לסוף - איפוס
            allOff()
            index = 0
            updateDisplay(0)
            basic.pause(100)
            pins.digitalWritePin(pinsList[index], 1)
            index++
            updateDisplay(index)
        }
    }
})

input.onButtonPressed(Button.B, function () {
    demoMode = false
    soundDemoMode = true
})

function demoRunnerStep() {
    allOff()
    pins.digitalWritePin(pinsList[demoStep], 1)
    updateDisplay(demoStep + 1)
    demoStep++
    if (demoStep >= pinsList.length) {
        demoStep = 0
        currentDemo = 1
    }
}

function demoFillStep() {
    if (fillDir > 0) {
        for (let j = 0; j < pinsList.length; j++) {
            pins.digitalWritePin(pinsList[j], j <= demoStep ? 1 : 0)
        }
        updateDisplay(demoStep + 1)
        demoStep++
        if (demoStep >= pinsList.length) {
            fillDir = -1
            demoStep = pinsList.length - 1
        }
    } else {
        for (let j = 0; j < pinsList.length; j++) {
            pins.digitalWritePin(pinsList[j], j <= demoStep ? 1 : 0)
        }
        updateDisplay(demoStep + 1)
        demoStep--
        if (demoStep < 0) {
            fillDir = 1
            demoStep = 0
            currentDemo = 2
        }
    }
}

function demoRandomStep() {
    let count = randint(0, pinsList.length)
    updateDisplay(count)
    for (let j = 0; j < pinsList.length; j++) {
        pins.digitalWritePin(pinsList[j], j < count ? 1 : 0)
    }
    demoStep++
    if (demoStep > 20) {
        demoStep = 0
        currentDemo = 3
    }
}

function demoBounceStep() {
    allOff()
    for (let i = -1; i <= 1; i++) {
        let pos = bouncePos + i
        if (pos >= 0 && pos < pinsList.length) {
            pins.digitalWritePin(pinsList[pos], 1)
        }
    }
    updateDisplay(bouncePos + 2)
    bouncePos += bounceDir
    if (bouncePos >= pinsList.length - 1) {
        bounceDir = -1
    } else if (bouncePos <= 0) {
        bounceDir = 1
        currentDemo = 4
        bouncePos = 0
    }
}

function demoWaveStep() {
    for (let i = 0; i < pinsList.length; i++) {
        let val = Math.sin((i + waveOffset) * 0.5)
        pins.digitalWritePin(pinsList[i], val > 0 ? 1 : 0)
    }
    updateDisplay(5)
    waveOffset++
    if (waveOffset > 40) {
        waveOffset = 0
        currentDemo = 0
        demoStep = 0
    }
}

basic.forever(function () {
    if (soundDemoMode) {
        let level = input.soundLevel()
        let num = Math.round(Math.map(level, 0, 255, 0, pinsList.length))
        num = Math.constrain(num, 0, pinsList.length)
        updateDisplay(num)
        for (let i = 0; i < pinsList.length; i++) {
            pins.digitalWritePin(pinsList[i], i < num ? 1 : 0)
        }
        basic.pause(50)
    } else if (demoMode) {
        if (currentDemo == 0) {
            demoRunnerStep()
        } else if (currentDemo == 1) {
            demoFillStep()
        } else if (currentDemo == 2) {
            demoRandomStep()
        } else if (currentDemo == 3) {
            demoBounceStep()
        } else if (currentDemo == 4) {
            demoWaveStep()
        }
        basic.pause(80)
    }
})