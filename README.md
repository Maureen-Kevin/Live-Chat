# Live-Chat
What do you think about this site?
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Simple Chat System</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f8f8f8;
      padding: 20px;
    }
    .chat-box {
      width: 100%;
      max-width: 500px;
      margin: auto;
      background: #fff;
      padding: 15px;
      border: 1px solid #ccc;
      border-radius: 6px;
    }
    .chat-window {
      height: 300px;
      overflow-y: auto;
      border: 1px solid #ddd;
      padding: 10px;
      margin-bottom: 10px;
      background: #fefefe;
    }
    .msg {
      margin: 5px 0;
    }
    .user {
      color: #007bff;
    }
    .bot {
      color: #28a745;
    }
    input[type="text"] {
      width: 75%;
      padding: 8px;
    }
    button {
      padding: 8px 12px;
      margin-left: 5px;
    }
  </style>
</head>
<body>

  <div class="chat-box">
    <h3>Simple Electronic Chat</h3>
    <div id="chat-window" class="chat-window">
      <div class="msg bot"><strong>Bot:</strong> Hello! Type a message below.</div>
    </div>
    <input id="user-input" type="text" placeholder="Type your message..." />
    <button onclick="sendMessage()">Send</button>
  </div>

  <script>
    function sendMessage() {
      const input = document.getElementById("user-input");
      const message = input.value.trim();
      if (message === "") return;

      const chatWindow = document.getElementById("chat-window");

      // Add user message
      const userMsg = document.createElement("div");
      userMsg.className = "msg user";
      userMsg.innerHTML = "<strong>You:</strong> " + message;
      chatWindow.appendChild(userMsg);

      // Simulate bot response
      const botMsg = document.createElement("div");
      botMsg.className = "msg bot";
      botMsg.innerHTML = "<strong>Bot:</strong> " + generateReply(message);
      chatWindow.appendChild(botMsg);

      input.value = "";
      chatWindow.scrollTop = chatWindow.scrollHeight;
    }

    function generateReply(message) {
      // Simple response logic (expandable)
      const lower = message.toLowerCase();
      if (lower.includes("hello")) return "Hi there!";
      if (lower.includes("help")) return "How can I assist you?";
      if (lower.includes("bye")) return "Goodbye! Have a nice day.";
      return "Thanks for your message!";
    }
  </script>

</body>
</html>
