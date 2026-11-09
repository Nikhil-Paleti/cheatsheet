# Nsight Systems (nsys) — Cheatsheet

Use `nsys` for the CPU / GPU timeline: kernel launches, copies, gaps, and overlap. Use [ncu](ncu.md) to inspect a slow kernel.

Linux / WSL commands. Replace `./app` with your executable or `python script.py`; put application arguments last.

## Capture

```sh
nsys profile --trace=cuda,nvtx --sample=none --cpuctxsw=none -o timeline ./app
```

Saves `timeline.nsys-rep`. Records CUDA activity and existing NVTX labels; skips CPU sampling and thread-scheduling data. Use a new output name for each run.

## Read reports

| Goal | Command |
| --- | --- |
| Default summaries | `nsys stats timeline.nsys-rep` |
| Kernel time and launch counts | `nsys stats --report cuda_gpu_kern_sum timeline.nsys-rep` |
| GPU copy / memset time | `nsys stats --report cuda_gpu_mem_time_sum timeline.nsys-rep` |
| CPU time inside CUDA API calls | `nsys stats --report cuda_api_sum timeline.nsys-rep` |
| Open the timeline, if the GUI is installed | `nsys-ui timeline.nsys-rep` |

Kernel summary percentages are shares of summed kernel time, not application wall time. Use the timeline to see overlap and idle gaps.

## Check options

| Goal | Command |
| --- | --- |
| Version / capture help | `nsys --version` / `nsys profile --help` |
| List available summary reports | `nsys stats --help-reports` |
| Check CPU profiling support | `nsys status --environment` |

For WSL captures, you can open the `.nsys-rep` in the Windows GUI. Use the same or a newer GUI version than the capturing CLI.

[User guide](https://docs.nvidia.com/nsight-systems/UserGuide/index.html) · [Summary reports](https://docs.nvidia.com/nsight-systems/AnalysisGuide/index.html)
