# Abstraction-Automated-Building-System

## Overview
Python implementation of a Building Automation System for UMaT's auditorium, built for the EL 162/234 Object Oriented Programming Week 7 lab (Abstraction).

Different automated systems (air conditioning, lighting, security) must all support common operations. Python's `abc` module is used to define an abstract class, `BuildingSystem`, that enforces this contract on every child class via `start()`, `stop()`, and `status()`.

## Contents
- `automation_system.py` — the solution

## Design
- **`BuildingSystem`** (abstract class, inherits `ABC`): defines abstract methods `start()`, `stop()`, `status()`. Stores a `name`. Cannot be instantiated directly.
- **`AirConditioningSystem`**, **`Lighting_system`**, **`SecuritySystem`**: concrete subclasses, each implementing `start()`, `stop()`, and `status()`, tracking running state with a `stat` flag.
- Objects are instantiated and stored in a list (`systems`), and the same loop calls `start()`, `stop()`, and `status()` polymorphically across all three, regardless of type.

## Running
```bash
python3 automation_system.py
