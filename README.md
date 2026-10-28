# 🥖 Bakery: Producer-Consumer Simulation

An interactive, web-based visualizer for the classic **Producer-Consumer Problem**, themed around a busy bakery. This project demonstrates how process synchronization works in operating systems using **Semaphores** and a shared **Buffer** (the display shelf).

## 🚀 Live Demo
*If you host this via GitHub Pages, you can place your link here!*

## 💡 How It Works (The Operating System Concept)
In an operating system, when multiple processes share a fixed-size space to write and read data, they can clash. This simulation visualizes the exact rules used to prevent data corruption:

*   **Bakers (Producers):** Create data (bake loaves of bread 🍞) and add them to the shelf. If the shelf is **FULL**, they must wait (`wait(empty)`).
*   **Customers (Consumers):** Take data (buy loaves of bread 🛍️) from the shelf. If the shelf is **EMPTY**, they must wait (`wait(full)`).
*   **The Shelf (Bounded Buffer):** A finite space tracking the current inventory.
*   **Semaphores & Mutex:** 
    *   `empty`: Tracks how many free slots are left on the shelf.
    *   `full`: Tracks how many loaves are ready to be eaten.
    *   `mutex` (Mutual Exclusion): Ensures only **one** baker or customer can touch the shelf at a fraction of a second, preventing sync errors.

## 🛠️ Features
*   **Real-time Visuals:** Watch bakers bake, customers line up, and bread dynamically slide onto the shelf.
*   **Dynamic Controls:** Adjustable sliders to alter the shelf capacity, baker speed, and customer shopping speeds on the fly.
*   **Semaphore Status Dashboard:** Watch the live counts of `empty`, `full`, and visual flashes whenever the `mutex` locks.
*   **Live Log Terminal:** A rolling command-line style terminal log showing exactly which thread is waiting, producing, or consuming.

## 📂 Tech Stack
*   **HTML5** - Semantic structure.
*   **CSS3** - Responsive Grid layout, custom property variations, and smooth CSS transform transitions.
*   **Vanilla JavaScript** - Clean ES6 state updates, async loop ticks, and DOM manipulation.

## 📝 Synchronization Logic Followed
```text
PRODUCER (Baker):             CONSUMER (Customer):
-----------------             --------------------
wait(empty)                   wait(full)
wait(mutex)                   wait(mutex)
[ Add bread to shelf ]        [ Take bread from shelf ]
signal(mutex)                 signal(mutex)
signal(full)                  signal(empty)
```

## ⚙️ Installation & Usage
Because this project is built entirely using standard web technologies, there are no dependencies to install!

1. Clone or download this repository.
2. Open the `index.html` file directly in any modern web browser (Chrome, Safari, Firefox, Edge).
3. Click **Start** to run the simulation!
