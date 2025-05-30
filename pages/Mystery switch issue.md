---
title: "Mystery switch issue"
---

![image](https://gyazo.com/9e14160f2cd3a328bbb72e4b7f8f0c6b/thumb/1000)
> I made a simple version of the circuit to take into account the possibility of a mistake, but it still judges that both are pressed when one of them is pressed...

- I made a program that reads whether a switch is pressed or not.
- Interpretation: The
    - The signal line is pulled up with a resistor to 3.3V in normal operation, and when the switch is pressed, the signal line is connected to ground, resulting in 0V.
    - The microcontroller determines that the switch is pressed when the voltage on the signal line is LO (less than about 1.2V).
- Fact: The
    - When one switch is pressed, somehow it is determined that both were pressed.
- Q: What is
    - Explain what is happening.
The answer is after the trial and error section.

Trial and Error Edition

- Pins are IN, of course.

- I thought about how the resistor that I think is 7.5KΩ is actually about 75Ω, what I did wrong, and just pressing one switch causes the voltage of Vcc to drop... but as I thought, that's not true.
    - It was purple-green-red-gold, so the line about the resistance being wrong is gone.

- Is the input pin voltage being watched for a certain period of time, like a chattering countermeasure?
    - Currently, the values read from the GPIOs are directly ASSIGNed to the LEDs and observed by the human eye, so there is no chattering effect.

- Once I gave up and tried to take it apart and put it away, but when I put it back together again for explanation, only one of the buttons would go LO when I pressed one button, and neither would go LO when I pressed the other. Huh?

- Switching to a different cable works easily.

- I tried pulling GND and Vcc from that state, and when Vcc is pulled out, the original phenomenon is reproduced

Solution:
- One of the cables is broken.
- What I thought was "HI" was actually "high impedance" because Vcc was disconnected in the first circuit I made.
- Therefore, if even one of the switches is pushed and shorted to GND, all signal lines will go LO through the pull-up resistor and the Vcc line on the breadboard.

impressions
- The major difference between software and hardware. Software components work as specified in any instance once you confirm that one instance works as specified. Hardware components are sometimes mixed with instances that do not work according to specifications.
- In software, there is no such thing as "Oh, this assignment operator is disconnected"... #Insertion operator disconnection

- [https://www.facebook.com/1129148772/posts/10201043688190917/](https://www.facebook.com/1129148772/posts/10201043688190917/)

---
This page is auto-translated from [/nishio/謎のスイッチの問題](https://scrapbox.io/nishio/謎のスイッチの問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.