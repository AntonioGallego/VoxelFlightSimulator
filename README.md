# VoxelFlightSimulator — First-Person Flight Simulator
A browser-based first-person flight simulator built entirely in a single HTML file using Three.js. Fly through a procedurally generated 2048×2048 voxel world with realistic flight physics, a full instrument panel, GPWS alerts, and day/night/weather environments — no install, no dependencies beyond a CDN script.

<img width="1725" height="862" alt="imagen" src="https://github.com/user-attachments/assets/84f7c039-3354-45d6-a536-b91bfc4cc8ef" />

# Features
Flight Model
Quaternion-based orientation system with no gimbal lock — full 360° rolls, inverted flight, and coordinated turns all work correctly. Pitch and roll are controlled via the left stick, rudder via shoulder buttons. Bank angle drives yaw through a tan(bank) turn-rate formula, giving realistic coordinated turns. Gyroscopic stabilisation provides a gentle dihedral effect that bleeds roll back toward wings-level when the stick is released.

# World
Terrain is a 2048×2048 voxel grid generated on-demand from multi-octave value noise — no heightmap array is stored in memory. Only the 192-voxel radius around the player is built into meshes at any time, with chunks streaming in and out as you fly. The world wraps toroidally so you can fly forever. Terrain types include sand beaches, grassland, rocky highlands, snow-capped peaks, and ocean.

# Cockpit & Instruments
A full instrument panel sits at the bottom of the screen with attitude indicator, directional gyro, elevator and rudder gauges — all driven directly by the flight physics every frame. A scrolling altitude tape on the right shows altitude in metres and vertical speed. A circular minimap at the top centre shows terrain height-coded in real time with a heading arrow.

# GPWS — Ground Proximity Warning System
A320-inspired callout sequence announces altitude on descent: 2500, 1000, 500, 400, 300, 200, 100, 50, 40, 30, 20, 10. Continuous mode alerts — TERRAIN TERRAIN, PULL UP, SINK RATE, TOO LOW TERRAIN, DON'T SINK, GLIDESLOPE — trigger based on radio altitude and vertical speed, with spoken audio via the Web Speech API and a red screen flash.

# Pre-flight Options
Choose terrain ruggedness (Flat to Alpine), sea level (Arid to Ocean), time of day (Day, Twilight, Night with stars), and weather (Clear, Cloudy, Foggy) before each flight.

# Controls
Gamepad or keyboard. Left stick: roll + pitch. Right stick: freelook camera. RB/LB: rudder. RT/LT: throttle.
