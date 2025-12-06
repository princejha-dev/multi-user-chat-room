# Flask Chat Application

A simple real-time chat application built with **Flask** and **Flask-SocketIO**. Users can create chat rooms, join existing rooms, and exchange messages in real time.

---

## 🚀 Features

* Create or join chat rooms using unique 4-letter codes
* Real-time messaging with WebSockets (Flask-SocketIO)
* Persistent messages stored per room (in-memory)
* Automatic cleanup of empty rooms

---

## 📂 Project Structure

```
project/
├── app.py
├── Procfile
├── requirements.txt
├── .gitignore
├── templates/
│   ├── base.html
│   ├── home.html
│   └── room.html
└── static/
    └── style.css

```

---

## 🔧 Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/princejha-dev/multi-user-chat-room.git
cd multi-user-chat-room
```

### 2. Create a virtual environment (optional but recommended)

```bash
python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the application

```bash
python app.py
```

The app will start at:

```
http://127.0.0.1:5000
```

---

## 🧠 How It Works

### Room Creation

A new room is created with a **random 4-letter uppercase code**:

* Stored in the `rooms` dictionary
* Holds `members` count and list of `messages`

### Joining a Room

Users enter:

* Their name
* An existing room code

If valid, they are redirected to the chat interface.

### Messaging

Messages are:

* Broadcast to everyone in the same room
* Saved to room history

### Disconnect Cleanup

If the last user leaves, the room is automatically deleted.

---

## 🛡️ Environment Variables

Update your secret key in `app.config["SECRET_KEY"]`:

```python
app.config["SECRET_KEY"] = "your-secure-key-here"
```

---

## 📌 Future Improvements

* Add user list panel in room
* Store history using a database instead of memory
* Implement permanent date in chat room
* Add authentication system

---

## 📄 License

This project is open-source. Modify and use as you wish!
