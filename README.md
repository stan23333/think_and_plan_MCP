<div style="text-align: center;">
    <img src="img/asset.jpg" alt="展示图片">
    <p>Help Claude think systematically and plan before tackling tasks, improving efficiency and quality!</p>
    <p>
        <a href="README_zh.md">中文</a> | <a href="README.md">English</a>
    </p>
</div>

# 📝 Task Planner MCP Server

An MCP (Model Context Protocol) server implementation that provides task planning and tracking tools for Claude and other MCP-compatible AI assistants.

## 📋 Overview

This Task Planner MCP server enables AI assistants to:

1. Create structured task plans ✨
2. Add and track steps for completing tasks 📊
3. Mark steps as complete as they are finished ✅
4. Document and resolve issues that arise during task execution 🛠️
5. Review the current state of plans 👀

All planning information is stored in a local `plan.md` file that can be reviewed and edited by humans.

## ✨ Features

- **Structured Planning**: Create organized task plans with steps and planning notes 📑
- **Progress Tracking**: Mark steps as complete as you execute them ⏱️
- **Issue Management**: Document problems and their resolutions 🔍
- **Review Capability**: Review the entire plan or specific tasks at any time 👁️
- **File-Based Storage**: All information stored in a human-readable Markdown file 📁

## 🛠️ Tools Provided

This MCP server exposes the following tools:

| Tool | Description |
|------|-------------|
| `think_and_plan` | Create a new structured plan for a task 🧠 |
| `add_step` | Add a new step to an existing task plan ➕ |
| `mark_step_complete` | Mark a step as completed ✓ |
| `review_plan` | View the current plan contents 📖 |
| `add_issue` | Document an issue with a specific step ⚠️ |
| `resolve_issue` | Mark an issue as resolved with explanation 🎯 |
| `update_planning_notes` | Update the planning notes for a task 📝 |
| `check_task_completion` | Check the completion status of a task 🔄 |
| `delete_step` | Delete a step from the plan 🗑️ |
| `delete_task` | Delete a task from the plan 🗑️ |
| `set_priority` |Set task priority High🔴Medium🟠Low🟢|

## 📥 Installation

### Prerequisites

- Python 3.10+ 🐍
- MCP SDK (`pip install mcp`)

### Setup

1. Clone this repository:
   ```
   git clone https://github.com/may3rr/think_and_plan_MCP.git
   cd think_and_plan_MCP
   ```

2. Install dependencies:
   ```
   pip install mcp
   ```

3. Run the server directly:
   ```
   python planner_server.py
   ```

### Integration
#### Option1: Use with Claude Desktop
To use with Claude Desktop:

1. Open Claude Desktop settings
2. Edit the configuration file
3. Add the following to your `claude_desktop_config.json`:

```json
"TaskPlanner": {
  "command": "/path/to/python",
  "args": [
    "/path/to/think_and_plan_MCP/planner_server.py"
  ]
}
```

Replace `/path/to/python` with your Python interpreter path and update the path to the planner_server.py file.
#### Option2: Use with Cursor
To use with Cursor:

1. Open **Settings** -> **Cursor settings** -> **Features**.
2. Edit the **MCP Servers** section and add a new MCP server.
3. Set the following:
   - **Name**: `TaskPlanner`
   - **Type**: `Command`
4. Set the **Command** to:
   ```
   /path/to/python /path/to/think_and_plan_MCP/planner_server.py
   ```

   Replace `/path/to/python` with the path to your Python interpreter and update the path to the `planner_server.py` file.

⚠️ **Note**: Ensure there is a space between the two paths.

## 🚀 Usage

Once the server is running and connected to an MCP client (like Claude Desktop), you can use the tools in your conversations:

### Example Workflow
```
Think and plan, create a personal website
```

## 📄 Structure of plan.md

The planner creates a `plan.md` file with a structure like this:

```markdown
# Task Plan

Created on: 2025-03-16 14:30:00

## Build a personal website

Created: 2025-03-16 14:30:00

### Planning Notes

This is a preliminary analysis of the task.

### Steps

[✅] Set up development environment
[ ] Create HTML structure
[ ] Style with CSS
    - ⚠️ ISSUE: CSS styles not applying to navigation menu (✓ RESOLVED: Fixed by correcting CSS selector specificity)
[ ] Add JavaScript interactions
[ ] Deploy to hosting service
```

## ❓ Troubleshooting

- **Permission errors**: Ensure the directory where `plan.md` is created has write permissions.
- **Integration issues**: Check Claude Desktop logs for connection errors.
- **MCP errors**: Ensure the MCP SDK is properly installed.

## 📋 TODOLIST

## 📜 License

MIT

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.