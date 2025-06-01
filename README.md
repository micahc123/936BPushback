# HighStakes-936B

## Description
HighStakes-936B is a robotics project utilizing the PROS library and lemlib for advanced chassis control, odometry, and subsystem management. This repository contains code for motor and sensor initialization, chassis configuration, and modular subsystems for movement and autonomous routines.

## Table of Contents
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Code Structure](#code-structure)
- [Subsystems Overview](#subsystems-overview)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Features
- Modular motor and sensor initialization
- Advanced chassis control with lemlib
- Odometry with tracking wheels and IMU
- Subsystem-based architecture for movement and autonomous routines
- Easy-to-extend for new subsystems

## Installation
1. **Clone the repository:**
   ```sh
   git clone https://github.com/yourusername/HighStakes-936B.git
   cd HighStakes-936B
   ```
2. **Install PROS CLI:**
   [PROS Installation Guide](https://pros.cs.purdue.edu/v5/getting-started/)
3. **Install dependencies:**
   - Ensure lemlib is included in your project (see [lemlib documentation](https://lemlib.github.io/))

## Usage
- Open the project in PROS Editor or your preferred IDE.
- Build and upload to your VEX V5 Brain:
  ```sh
  pros make
  pros upload
  ```
- Modify `src/globals.cpp` to adjust motor ports, gear settings, or subsystem parameters as needed.

## Code Structure
```
HighStakes-936B/
├── include/           # Header files
├── src/               # Source files
│   └── globals.cpp    # Global motor, sensor, and subsystem initialization
├── README.md          # Project documentation
└── ...
```

### Example: Motor and Sensor Initialization (from `src/globals.cpp`)
```cpp
pros::Motor leftFrontMotor(LEFT_MOTOR_1, pros::E_MOTOR_GEAR_BLUE);
pros::Motor leftMiddleMotor(-LEFT_MOTOR_3, pros::E_MOTOR_GEAR_BLUE);
pros::Motor leftBackMotor(LEFT_MOTOR_2, pros::E_MOTOR_GEAR_BLUE);
pros::MotorGroup leftMotors({leftFrontMotor, leftMiddleMotor, leftBackMotor});
pros::Rotation horizontalEncoder(HORIZONTAL_ENCODER_PORT);
pros::Imu imu(IMU_PORT);
```

## Subsystems Overview
- **Movement:** Handles chassis movement and path following using lemlib.
- **Auton:** Manages autonomous routines.
- **Selector:** Allows selection of autonomous routines.

### Example: Subsystem Initialization
```cpp
subsystems::Movement movement(&chassis);
subsystems::Auton auton(&chassis);
subsystems::Selector selector(&auton);
```

## Contributing
Contributions are welcome! Please open issues or submit pull requests for improvements or bug fixes. Follow best practices for code documentation and formatting.

## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Contact
For questions or support, open an issue or contact the maintainer at [your.email@example.com](mailto:your.email@example.com).
