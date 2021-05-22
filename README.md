# Controlling the FPS with `tk.after(ms, func)`.

In short, I wanted to control the `frames per second` within my main loop. 
This is how I did it.

```python
fps = FPSController(fps=10)

def loop():
    root.after(fps.pause(), loop)

root = tk.Tk()
root.after(0, loop)
root.mainloop()
```

Now `after` is not called after a fixed given time, but it auto-corrects itself to maintain the given FPS.
