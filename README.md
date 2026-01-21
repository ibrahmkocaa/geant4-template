# Geant4 Project Template

Minimal and clean Geant4 project template for high-energy physics simulations.

## Project Structure

```
geant4-template/
├── CMakeLists.txt          # Build configuration
├── main.cc                 # Main program entry point
├── README.md               # This file
├── include/
│   ├── DetectorConstruction.hh
│   ├── Materials.hh
│   ├── ActionInitialization.hh
│   └── PrimaryGeneratorAction.hh
├── src/
│   ├── DetectorConstruction.cc
│   ├── Materials.cc
│   ├── ActionInitialization.cc
│   └── PrimaryGeneratorAction.cc
└── macros/
    ├── vis.mac             # Visualization macro
    └── run.mac             # Batch run macro
```

## Requirements

- Geant4 (tested with 10.7+, 11.x)
- CMake 3.16+
- C++ compiler with C++17 support

## Building

```bash
# Create build directory
mkdir build && cd build

# Configure (make sure Geant4 is in your PATH)
cmake ..

# Build
make -j$(nproc)
```

## Running

### Interactive Mode (with visualization)
```bash
./g4template
```

### Batch Mode
```bash
./g4template macros/run.mac
```

## Customization Guide

### Adding Detector Geometry
Edit `src/DetectorConstruction.cc` in the `DefineVolumes()` function.

### Adding Custom Materials
Edit `src/Materials.cc` in the `DefineCustomMaterials()` function.

### Changing Primary Particles
Edit `src/PrimaryGeneratorAction.cc` or use macro commands:
```
/gun/particle proton
/gun/energy 100 MeV
```

### Adding User Actions
1. Create new action classes (e.g., `RunAction`, `EventAction`, `SteppingAction`)
2. Uncomment and add them in `src/ActionInitialization.cc`

## License

This template is free to use for academic and research purposes.
