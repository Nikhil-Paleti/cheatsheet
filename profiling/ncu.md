# Nsight Compute (ncu) — Cheatsheet

Use `ncu` for individual kernel metrics. Start with [nsys](nsys.md) to find where time goes.

Linux / WSL commands. Replace `./app` with your executable or `python script.py`; put application arguments last. Replace `vectorAdd` with your kernel name.

## Profile

| Goal | Command |
| --- | --- |
| Quick look at the first kernel launch | `ncu --launch-count 1 ./app` |
| Full metrics for one launch; save `kernel.ncu-rep` | `ncu --set full --launch-count 1 -o kernel ./app` |
| Profile one matching kernel launch | `ncu --kernel-name-base function --kernel-name 'regex:vectorAdd' --launch-count 1 ./app` |
| Skip 10 launches, then profile one | `ncu --launch-skip 10 --launch-count 1 ./app` |

Combine filters with `--set full` and `-o kernel` when needed. Skip/count apply to matching launches, not training iterations.

## Read reports

| Goal | Command |
| --- | --- |
| Read saved results in the terminal | `ncu --import kernel.ncu-rep --page details` |
| Export collected metrics as CSV | `ncu --import kernel.ncu-rep --page raw --csv > metrics.csv` |
| Open in the GUI, if installed | `ncu-ui kernel.ncu-rep` |

## Check options

| Goal | Command |
| --- | --- |
| Version / help | `ncu --version` / `ncu --help` |
| Available metric sets / sections | `ncu --list-sets` / `ncu --list-sections` |

`--set full` can replay kernels many times. Filter to a few representative launches; measure normal application speed separately.

For `ERR_NVGPUCTRPERM` in WSL, enable GPU performance-counter access on the **Windows host**. `sudo` inside WSL does not change that host setting.

[CLI reference](https://docs.nvidia.com/nsight-compute/NsightComputeCli/index.html) · [Profiling and WSL permissions](https://docs.nvidia.com/nsight-compute/ProfilingGuide/index.html)
