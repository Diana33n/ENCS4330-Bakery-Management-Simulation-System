

# 🍞 Bakery Management Simulation System

## 📝 Overview

This project simulates a bakery using **multi-processing** and **inter-process communication (IPC)** techniques under Linux. It models the daily operations of a bakery where chefs, bakers, sellers, and supply-chain staff work together to serve customers.

The system uses:

* 📦 **Shared memory** for inventory management
* 🔐 **Semaphores** for resource synchronization
* 📩 **Message queues** for customer-seller communication
* 📡 **Signals** for process control (pause/resume, termination)
* 🎨 **OpenGL visualization** for a live view of bakery activity

---

## 🚀 Features

### 👨‍🍳 Chefs

* Teams: Paste, Cakes, Sandwiches, Sweets, Sweet & Savory Patisseries
* Dynamic switching between teams when imbalance is detected

### 🥖 Bakers

* Bake items produced by chefs
* Use ovens (managed with semaphores)

### 🚚 Supply Chain

* Replenishes inventory for core ingredients like wheat, yeast, butter, milk, sugar, salt, sweet items, cheese, salami

### 👩‍💼 Manager

* Monitors inventory and adjusts team activities
* Pauses/resumes chef/baker teams to prevent overstocking

### 🛍️ Sellers

* Serve customers’ requests
* Process orders, calculate prices, handle refunds

### 🧑‍🤝‍🧑 Customers

* Randomly arrive and place orders
* Get frustrated or leave if wait time is too long or complaints occur

### 🎨 Visualization (OpenGL)

* Displays:

  * Chefs, bakers, sellers, customers in action
  * Stock levels and business metrics
  * Animations for item movement and customer satisfaction

---


## ⚙️ How It Works

1. **Initialization**:

   * Loads configuration from `config.txt`
   * Sets up shared memory and semaphores
   * Spawns processes for each role (chefs, bakers, sellers, supply chain, manager, customers, visualizer)

2. **Customer Orders**:

   * Randomized item selection (bread, cakes, sandwiches, sweets, patisseries)
   * Sellers process orders and update profits

3. **Dynamic Management**:

   * Manager balances stock levels and prevents overproduction by pausing/resuming teams.

4. **End Conditions**:

   * Profit target achieved
   * Max frustrated customers reached
   * Max complaints reached
   * Missing item requests exceeded threshold
   * Simulation time exceeded

---



### ▶️ Run Simulation

```bash
./main config.txt
```

### 🖥️ Visualization

Ensure OpenGL (`GLUT`) is installed:

```bash
sudo apt-get install freeglut3-dev
```

---

## 📊 IPC Mechanisms Used

* **Shared Memory** (`shmget`, `shmat`, `shmctl`) for inventory
* **Semaphores** (`sem_t`, `sem_wait`, `sem_post`) for synchronization
* **Signals** (`SIGTERM`, `SIGUSR1`, `SIGUSR2`) for process control
* **Message Queues** (`msgget`, `msgrcv`, `msgsnd`) for customer-seller communication

---

## 🎯 Goals Achieved

✅ Realistic bakery workflow
✅ Multi-processing simulation
✅ Resource synchronization
✅ Dynamic management of processes
✅ OpenGL-based live visualization

---

