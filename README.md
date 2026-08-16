# 🍫 Double Chocolate Cone (Double C*) Language

Double Chocolate Cone (Double C*) is a game‑focused scripting language designed for the ConeEngine ecosystem.  
It is simple for beginners, powerful for advanced users, and transpiles directly to JavaScript.

Double C* is built for:
- 2D and 3D game development
- beginner‑friendly scripting
- advanced component‑based logic
- fast execution through JS transpilation
- clean, readable syntax

This repository contains:
- the official Double C* language specification
- grammar definition (EBNF)
- example scripts
- roadmap for future language features

**File extension:**  
`.dc*`

---

## ✨ Features

- Game‑native syntax (entities, scenes, events)
- Beginner + advanced scripting modes
- Simple, readable structure
- Built‑in engine actions (move, jump, rotate, spawn)
- Event‑driven logic (start, update, click, collide)
- Transpiles to JavaScript
- Designed for DC* Studio and ConeEngine

---

## 📚 Contents

- `spec.md` — Full language specification  
- `grammar.ebnf` — Formal grammar definition  
- `examples/` — Example Double C* scripts  
- `roadmap.md` — Future plans and development goals  

---

## 🧪 Example
entity Player {
var speed = 6
var jumpForce = 12

on start {
print "Player ready!"
}

on update {
if key W {
move(0, -speed)
}
if key SPACE {
jump(jumpForce)
}
}
}

scene Level1 {
spawn Player at (0, 0)
}

---

## 🚀 Status

Double C* is currently in **early development**.  
Compiler, runtime, and DC* Studio integration are planned in future milestones.

