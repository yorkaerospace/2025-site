+++
date = '2022-12-15T00:00:00+00:00'
draft = true
title = 'Designing a Simple Avionics PCB For Model Rocketry'
image = 'banner.png'
tags = [
    "electronics",
    "CAD"
]
+++
In our [previous]( {{< relref "2022-07-avionics" >}}) blog post, we talked about assembling a simple avionics system using off-the-shelf development boards. This is quick and cheap, but it leaves you with a system that is quite bulky, and quite fragile. In some of our previous designs, we have had pins bend under acceleration or vibrate loose. None of these issues is insurmountable, but if you want something that is small and sturdy, you’ll need a PCB.
## Component Choice

This is the most important, and perhaps the most frustrating part of a PCB design. Sensors are in short supply, so finding suitable ones can be quite tedious. A lot of the stock from big-name brands that we were previously using has all been snapped up, but there are still some components out there.
### Barometers

The barometer is a critical component in rocket avionics, as it allows us to determine the rocket's altitude based on the barometric pressure. In one of our upcoming designs, we’re planning to use the MS5637-02BA03 from TE Connectivity. This is a no-frills barometer in an absolutely tiny package; perfect for a compact avionics system. There’s also Wurth Elektronik’s 2511020213301, which comes with interrupt lines and a fully featured SDK.
### Inertial Measurement Units

IMUs are in very short supply at the moment, especially high-performance ones, you may have an easier time shopping for separate accelerometers and gyroscopes. This comes at the cost of increased size, but you’ll get far better results than you would otherwise. The ADXL375 from our original post is still easily available, with its whopping 200g range. We’ve combined this with an I3G4250 gyroscope from STMicroelectronics to form a single IMU. Together these units give us finer detail about the speed, orientation and angular velocity of the rocket.
### Microcontrollers

In order to pull all these components together, we need a microcontroller to coordinate the communication and log data. For most of our designs nowadays we are using the RP2040chip from Raspberry Pi. This chip is frankly overkill, with two ARM M0+ cores running at 133 MHz, yet it only costs about 90 pence. It has plenty of IO for controlling pyro channels and comes in a tiny QFN package. The downside is that it requires an external flash chip and crystal to operate, driving up the size and cost of your board. The SDK is also less mature than those from other manufacturers, such as STM and PIC.
### Other Components

Depending on your application, you may wish to include other components in your design. For instance, a GPS and Radio are a good combination for locating your rocket after landing, especially when you find yourself trudging through a muddy field.
## Schematic Design

Once you have all your components together, It's time to move into your EDA software. There are a number of good options here, but if you’re looking for a good free one, consider DesignSpark PCB. We’ve tried a number of free EDA tools for our projects, but since we tend to use more obscure parts, we often ended up wasting time preparing symbols and footprints for each part we had to use. RS has already done the hard work here, and you can simply download schematic symbols and footprints as you browse components. It also comes with a large number of tutorials and documentation, making it easy to pick up and start using.

If you’re new to electronic design, the simplest way to get started is to work off the reference schematics shown in the component’s datasheets. These typically include all the decoupling capacitors, filters and any other ancillary components the component needs, but be sure to read the documentation in full. There may be other components not shown on the schematic, or the schematic may be broken down into sections across multiple pages.

There are a couple of common pitfalls you’ll need to watch out for, especially with I2C. Firstly, the pullup resistors may seem trivial but choosing a value that is too high can cause some very hard-to-debug problems, and choosing a value that is too low will waste power. For this application, you want a value that is as close to the maximum as possible, which is approximately [1]:

$$
\begin{aligned}
R_{Max} &= \mathrm{3.54e}{-7} / C_b \text{ for I2C Fast mode (400kHz) or}\\\
R_{Max} &= \mathrm{1.18e}{-6} / C_b \text{ for I2C Standard mode (100kHz)}
\end{aligned}
$$

(Rounded for ease of use, see [1] for full formulae)

Where $C_b$ is the bus capacitance. If we assume that the trace capacitance is small compared to the capacitance of the loads, then $C_b$ is simply the sum of the load capacitances for each component on the line, which should be listed in their respective datasheets. If not, 25 pF per component is usually a safe assumption.

You’ll also want to integrate test points into all of your SPI and I2C lines. These are little pads or holes that you can attach a logic analyser or oscilloscope to. These will make debugging your firmware a lot easier, as even the cheapest logic analyser will come with tools for decoding I2C, SPI and UART.
## PCB Design

You could write an entire book on this, and I’m sure someone has. For simple applications like this though, there are a few guidelines that you can follow to get a nice working PCB, no matter what EDA package you use:

1. **Keep traces short.**

    The longer your traces are, the worse the parasitic effects will be. Length adds capacitance, and winding around components adds inductance. It shouldn’t matter too much on a PCB like this, but still, you want it to be compact.
2. **Use copper fills to create a ground plane**

    This allows you to very quickly and efficiently connect all of your components ground’s together, with minimal parasitic effects. It also makes manufacturing a bit easier, as less copper will have to be milled or etched away.
3. **Be careful about your component sizing.**

    Your manufacturer might be able to place 0201 components, but can you? If you don’t have the tooling and experience then you will struggle to solder anything below an 0805. This may make your board larger, but you’ll be glad you did it whenever you have to adjust something.
4. **Use the grid.**

    This is partly just for neatness’s sake. Most EDA software will let you set a grid size for your components to snap to, which will make aligning traces and fills to your components so much easier.
5. **Keep your silkscreen neat and reasonably sized.**

    Your silkscreen almost acts as documentation for your PCB, it lets you and the manufacturer identify components without having to go back to a diagram. If it's confusing or illegible, it may as well not be there. As a rule, silkscreen text below 1.6mm in height will be difficult to read.
6. **The DRC is your friend, use it!**

    After staring at a PCB for hours on end, it can become easy to overlook problems, even especially simple ones. The DRC can check for most manufacturing issues automatically. It's no guarantee, but it makes your life a lot easier.
7. **Think about how you are going to mount the PCB**

    This is especially important for model rocketry. We used to just pack our avionics system in with sponges. This worked well enough until we had an incident where the avionics system was rammed into the nose cone, and got stuck. We had to cut it out with a saw. Just add a few mounting holes.
