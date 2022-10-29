# FpgaMacro
A Chisel3 package to describe verilog FPGA template and macro for hardened FPGA modules

## Use it globally (with maven.pkg.github.com)

To use it without clone the repository, add the following lines to your
build.sbt project :

```scala
...
externalResolvers += "fpgamacro packages" at "https://maven.pkg.github.com/Martoni/fpgamacro",
...
libraryDependencies ++= Seq(
...
  "Martoni" %% "fpgamacro" % "0.1.0"
  ...
),
```

## Use it locally

To install it, clone it then publish local:
```bash
$ git clone https://github.com/Martoni/fpgamacro.git
$ cd fpgamacro
$ sbt publishLocal
```
Then add these lines in your `build.sbt` project :
```scala
//publish local https://github.com/Martoni/fpgamacro.git
libraryDependencies ++= Seq("org.armadeus" %% "fpgamacro" % "0.1.0")
```

## Generic

### ResetGen

Generating a reset pulse with initial 0 state.

### TriStateBuffer

Instanciation of 1 bit and 16bits tri-state buffers.

## MachXO3

### ReverseClock

A PLL instanciation of MachXO3 to reverse clock (180° phase).

## ECP5



## Gowin

Some primitives blackboxed instanciation :

- `OSC` : internal oscillator blackbox
- `Gowin_OSC` : internal oscillator with FREQ_DIV parameter
- `PLLVR` : Some PLL instanciation for TMDS and HyperRam
- `RPLL` : PLL instanciation mainly for GW1NR-9
- `CLKDIV`: clock divider (by 5 default)
- `TMDS_PLLVR`: PLL block generated by gowin ide to drive TMDS blocks
- `OSER10`: 10:1 serializer with friendler module named `Oser10Module`
