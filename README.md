# Humanoid Robot URDF Project

This repository contains URDF (Unified Robot Description Format) models for a humanoid robot. The project includes two separate robot configurations:

1. `dummy_robot` - A basic humanoid robot configuration
2. `dummy_robot_head` - A humanoid robot configuration with an enhanced head model

## Project Structure

```
humanoid_urdf_test/
├── dummy_robot/           # Basic humanoid robot package
│   ├── urdf/              # URDF model files
│   ├── meshes/            # 3D mesh files (STL format)
│   ├── launch/            # ROS launch files
│   ├── config/            # Configuration files
│   ├── textures/          # Texture files
│   ├── package.xml        # ROS package definition
│   └── CMakeLists.txt     # Build configuration
├── dummy_robot_head/      # Enhanced humanoid robot package with head
│   ├── urdf/              # URDF model files
│   ├── meshes/            # 3D mesh files (STL format)
│   ├── launch/            # ROS launch files
│   ├── config/            # Configuration files
│   ├── textures/          # Texture files
│   ├── package.xml        # ROS package definition
│   └── CMakeLists.txt     # Build configuration
├── full-body/             # (Empty directory)
└── full-body-leg/         # (Empty directory)
```

## Robot Components

Each robot configuration includes the following components:

- **Base Link**: Main body of the robot
- **Arms**: Left and right arms with shoulder joints
- **Legs**: Left and right legs with limb joints
- **Head**: Head component with neck joint

## Dependencies

These packages require the following ROS dependencies:
- `roslaunch`
- `robot_state_publisher`
- `rviz`
- `joint_state_publisher_gui`
- `gazebo`

## Usage

### Display in RViz

To visualize the robot in RViz:

```bash
# For the basic dummy robot
roslaunch dummy_robot display.launch

# For the enhanced dummy robot with head
roslaunch dummy_robot_head display.launch
```

### Simulation in Gazebo

To simulate the robot in Gazebo:

```bash
# For the basic dummy robot
roslaunch dummy_robot gazebo.launch

# For the enhanced dummy robot with head
roslaunch dummy_robot_head gazebo.launch
```

## URDF Details

The URDF files were automatically generated using the SolidWorks to URDF Exporter:
- Original creator: Stephen Brawner (brawner@gmail.com)
- Commit Version: 1.6.1-11-gaed57c3-dirty
- Build Version: 1.6.9385.29558

Each URDF contains:
- Links with defined inertial properties, visual meshes, and collision geometries
- Joints with defined types, axes, and limits
- Material definitions with color properties

## Notes

- All joints are currently configured as revolute joints with limits set to 0
- Mesh files are referenced using the `package://` URI scheme
- The robots are designed for use with ROS (Robot Operating System)