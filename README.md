# dsai-m3-coaching-moneyball-analytics-kaggle

# Objective

Run:

- Jupyter server inside `tmux`  
- Notebook kernel attached to that server  
- VS Code connects as a client (optional)

---

# 1. Start a tmux session

In your **VS Code terminal (WSL)**:

```bash
tmux new -s jupyter
```

You are now inside a persistent session.

---

# 2. Launch Jupyter server inside tmux

```bash
jupyter notebook --no-browser --port=8888
```

### What this does

- `--no-browser` → avoids opening a GUI (important in WSL)  
- `--port=8888` → fixed port for easy reconnection  

---

# 3. Copy the access URL

You’ll see output like:

```
http://127.0.0.1:8888/?token=abc123...
```

👉 Copy this entire URL (including token)

---

# 4. Detach tmux (server keeps running)

Press:

```
Ctrl + B, then D
```

Now:
- Jupyter server continues running  
- You can close terminal/VS Code safely  

---

# 5. Connect from VS Code

In VS Code:

1. Open Command Palette:
   ```
   Ctrl + Shift + P
   ```

2. Select:
   ```
   Jupyter: Specify Jupyter Server for Connections
   ```

3. Choose:
   ```
   Existing
   ```

4. Paste the URL from Step 3  

---

# 6. Open your notebook

- Open `.ipynb` file in VS Code  
- Select the connected kernel  
- Run your cells normally  

---

# 7. What happens now

Even if:
- VS Code closes  
- SSH/WSL session drops  

👉 Your notebook kernel **keeps running inside tmux**

---

# 8. Reconnect later

## Reattach tmux (optional)

```bash
tmux attach -t jupyter
```

## Or just reconnect via VS Code
(using same URL)

---

# 9. Stop everything cleanly

Reattach tmux:

```bash
tmux attach -t jupyter
```

Then:

```
Ctrl + C   # stop Jupyter
exit       # exit tmux
```

---

# 10. Optional stability improvements

## Disable idle shutdown

```bash
jupyter notebook --no-browser --port=8888 \
--NotebookApp.shutdown_no_activity_timeout=0
```

---

## Use logging (optional)

```bash
jupyter notebook > jupyter.log 2>&1
```

---

# 11. Common pitfalls

| Issue               | Cause                    |
| ------------------- | ------------------------ |
| Kernel dies         | Jupyter not inside tmux  |
| Can't reconnect     | Token changed            |
| Port conflict       | Another Jupyter instance |
| Job stops overnight | Laptop sleep             |

---

# 12. Recommended minimal workflow

```bash
tmux new -s jupyter
jupyter notebook --no-browser --port=8888
# Copy URL
# Detach: Ctrl+B D
```

---

# Final note

This setup gives you:

- Persistent execution  
- UI-independent training  
- Safe long-running jobs (3+ hours)