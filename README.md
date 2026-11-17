# Pendulum Equation Solver

I was working with pendulum equations and wanted to understand how their mathematical models behave when different values are used. Solving the equations manually and calculating the results every time felt repetitive, so I thought of building a small tool that could handle these calculations for me.

That's how I came up with **Pendulum Equation Solver**. The idea was to make working with pendulum equations easier by turning the mathematical calculations into something that could be solved and explored through code.

## Features

- **Realistic Physics**: Implements the equations of motion for an inverted pendulum using Runge-Kutta 4th order numerical integration
- **PID Controller**: Standard PID controller with adjustable gains (Kp, Ki, Kd) to balance the pendulum
- **Interactive Controls**: Start/pause/reset simulation and add disturbances to test controller response
- **Real-time Visualization**: Smooth canvas-based rendering of the cart and pendulum
- **Responsive Design**: Beautiful, modern UI that works on all screen sizes
- **Live Metrics**: Display of angle, cart position, and control force

## Getting Started

### Installation

```bash
npm install
```

### Development

```bash
npm run dev
```

### Build

```bash
npm run build
npm start
```

## How It Works

The inverted pendulum system is based on the relationship between the cart, pendulum, and the forces acting on them.

The following diagram illustrates the system, its input parameters, governing equations, and calculated outputs.

<p align="center">
  <img src="assets/Inverted Pendulum Control Infographic.png" alt="Inverted Pendulum System" width="850"/>
</p>

### Physics Simulation

The inverted pendulum is modeled using classical mechanics:
- Cart mass: 1.0 kg
- Pendulum mass: 0.1 kg
- Pendulum length: 1.0 m
- Gravity: 9.81 m/s²

The system uses the Lagrangian equations of motion with friction to simulate realistic behavior.

### PID Controller

The PID controller generates a force to keep the pendulum upright:
- **Proportional (Kp)**: Responds to current error (angle from vertical)
- **Integral (Ki)**: Eliminates steady-state error
- **Derivative (Kd)**: Dampens oscillations

Default gains (Kp=100, Ki=1, Kd=50) provide stable control, but you can adjust them to see their effects.

## Usage

1. **Start**: Begin the simulation with the current settings
2. **Pause**: Freeze the simulation
3. **Reset**: Return to initial state (pendulum at 0.1 radians from vertical)
4. **Add Disturbance**: Apply a sudden angular displacement to test controller response
5. **Tune PID**: Adjust the sliders to change controller behavior in real-time

## Project Structure

```
├── components/
│   └── PendulumCanvas.tsx    # Visualization component
├── lib/
│   ├── InvertedPendulum.ts   # Physics simulation
│   └── PIDController.ts      # PID controller implementation
├── pages/
│   ├── _app.tsx              # Next.js app wrapper
│   └── index.tsx             # Main simulation page
└── styles/
    └── globals.css           # Global styles with Tailwind
```

## Technologies

- **Next.js 14**: React framework with server-side rendering
- **TypeScript**: Type-safe development
- **Tailwind CSS**: Utility-first styling
- **HTML Canvas**: High-performance rendering

## License

MIT
