#  Zeta-26 · Relic Ring Protocol

**Team:** ByteForce  
**Competition:** Launch 26 — IEEE Computer Society, University of Kelaniya

---

##  What is This?

A communication network simulator for the Zeta-26 star system.  
After the Hyper-Flare of 3704 destroyed the quantum network, this system  
reconnects planets using physical fiber cables and laser transceivers.

---

##  How to Run

1. Download or clone this repository
2. Open `zeta26_simulator.html` in any modern browser
3. That's it — no installation required!

> Works best on Chrome or Firefox.

---

##  Features

-  Interactive universe map with all 6 planetary nodes
-  Real-time packet transmission between planets
-  Automatic base conversion (each planet uses a different codex)
-  Full latency breakdown — Fiber, Tower, Atmosphere, Void
-  Hop-by-hop packet trace with tower routing
-  Live node kill/revive with dynamic rerouting
-  Zoom, pan, and inspect any planet

---

##  Planets (Nodes)

| Planet | Codex | Towers | Radius |
|--------|-------|--------|--------|
| Aegis | Base-8 | 8 | 6,371 km |
| Boreas | Base-5 | 4 | 3,389 km |
| Dawn | Base-6 | 6 | 1,500 km |
| Elysium | Base-10 | 12 | 6,051 km |
| Fenix | Base-16 | 4 | 1,200 km |
| Caelum | Base-14 | 16 | 58,232 km |

---

##  How It Works

### Latency Calculation
Every packet has 4 delay components:
- **Fiber** — Travel along planet's equatorial ring at 0.67c
- **Tower** — 7ms processing delay per tower hit
- **Atmosphere** — Signal slowed by refraction index (n)
- **Void** — Laser transmission between planets at speed of light

### Routing
- Dijkstra's algorithm finds the lowest-latency route
- Max single hop: 50,000,000 km (Lmax)
- If exceeded, routes through intermediate planets

### Data Encoding
- Each planet receives in its own numerical base (codex)
- Message converts to next hop's base before void transmission
- Internally processed as ASCII between towers

### Fault Tolerance
- Kill any node using the button
- System instantly reroutes around dead nodes
- No data loss

---

##  Project Structure

---

##  Configuration

The system reads all values from `universe-config.json` — no hardcoded planetary values.

Key constants (from config):
- Speed of light: 300,000 km/s
- Tower delay: 7ms
- Fiber speed: 0.67c
- Max void hop: 50,000,000 km

---

*Built for Launch 26 · IEEE CS University of Kelaniya*

