

---

## 🧠 **Muscle Memory Linux Commands for ROS 2**

We'll divide this into three levels:

### 🔹 1. Basic File System Navigation

### 🔸 2. ROS 2 Workspace Operations

### 🔺 3. Common ROS 2 Environment/Tools

---

## 🔹 1. **Linux Basics — Navigating and Managing Files**

| Command    | Purpose                 | Example                |
| ---------- | ----------------------- | ---------------------- |
| `pwd`      | Show current directory  | `/home/kandarp/ROS2`   |
| `ls`       | List contents           | `ls src/`              |
| `cd`       | Change directory        | `cd ~/ROS2/src`        |
| `mkdir -p` | Make directory (nested) | `mkdir -p ~/ROS2/src`  |
| `touch`    | Create empty file       | `touch talker.py`      |
| `chmod +x` | Make a file executable  | `chmod +x talker.py`   |
| `cp`       | Copy files              | `cp file.py backup.py` |
| `mv`       | Move or rename files    | `mv old.py new.py`     |
| `rm`       | Remove files            | `rm old.py`            |

⏱️ **Use often**: `cd`, `ls`, `pwd`, `mkdir`, `chmod`

---

## 🔸 2. **ROS 2 Workspace Essentials**

### 🔧 Create your workspace

```bash
mkdir -p ~/ROS2/src
cd ~/ROS2
```

* `mkdir -p`: Makes `ROS2` and `ROS2/src` in one shot.
* `cd ~/ROS2`: Changes to that directory.

---

### 🔧 Build your workspace

```bash
colcon build
```

* `colcon`: ROS 2’s build tool (like `make`)
* Builds all packages inside `src/`

---

### 🔧 Source the workspace

```bash
source install/setup.bash
```

* `source`: Executes the script in your current shell.
* Sets ROS 2 environment variables so `ros2` commands work.

🧠 Add to muscle memory:

```bash
source ~/ROS2/install/setup.bash
```

---

### 🔧 Create a ROS 2 package

```bash
ros2 pkg create --build-type ament_python my_package
```

* `ros2 pkg create`: Creates boilerplate code
* `ament_python`: Python-based package

---

## 🔺 3. **ROS 2 Node Running & Debugging**

### 🏃‍♂️ Run a Node

```bash
ros2 run my_package talker
```

* `ros2 run`: Run any node
* `my_package`: Package name
* `talker`: Entry point from `setup.py`

---

### 🔎 List Nodes

```bash
ros2 node list
```

* Shows currently running nodes

---

### 🧠 Common Gotchas to Debug

| Problem                     | Solution                                                           |
| --------------------------- | ------------------------------------------------------------------ |
| `ros2: command not found`   | `source /opt/ros/humble/setup.bash` or `source install/setup.bash` |
| `colcon: command not found` | `sudo apt install python3-colcon-common-extensions`                |
| `Permission denied`         | Use `chmod +x file.py`                                             |
| Changes not reflecting      | Rebuild: `colcon build && source install/setup.bash`               |

---

## 🥋 Final Pro Practice Flow (Every time you boot up)

```bash
cd ~/ROS2
source install/setup.bash
```

Then work as usual:

```bash
cd src/my_package/my_package
code .          # if using VS Code
ros2 run my_package talker
```

# I took this shit from chat gpt , you are welcome 

