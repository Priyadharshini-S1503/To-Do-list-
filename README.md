<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>To-Do List</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      padding: 50px;
    }

    .todo-container {
      background: #fff;
      padding: 20px 30px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      width: 300px;
    }

    h2 {
      text-align: center;
      color: #333;
    }

    input[type="text"] {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 6px;
    }

    button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      background: #3498db;
      color: white;
      font-size: 16px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
    }

    ul {
      list-style: none;
      padding-left: 0;
      margin-top: 20px;
    }

    li {
      background: #eee;
      padding: 10px;
      margin-bottom: 10px;
      border-radius: 6px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    li.done {
      text-decoration: line-through;
      color: gray;
    }

    .delete-btn {
      background: #e74c3c;
      color: white;
      border: none;
      padding: 5px 8px;
      border-radius: 4px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <div class="todo-container">
    <h2>To-Do List</h2>
    <input type="text" id="taskInput" placeholder="Enter a task..." />
    <button onclick="addTask()">Add Task</button>
    <ul id="taskList"></ul>
  </div>

  <script>
    function addTask() {
      const taskInput = document.getElementById("taskInput");
      const taskText = taskInput.value.trim();

      if (taskText === "") return;

      const li = document.createElement("li");
      li.textContent = taskText;

      li.addEventListener("click", () => {
        li.classList.toggle("done");
      });

      const deleteBtn = document.createElement("button");
      deleteBtn.textContent = "X";
      deleteBtn.className = "delete-btn";
      deleteBtn.onclick = () => li.remove();

      li.appendChild(deleteBtn);
      document.getElementById("taskList").appendChild(li);
      taskInput.value = "";
    }
  </script>
</body>
</html># To-Do-list-
