# Python Command Benchmark Tool

A high-precision benchmarking tool for measuring command execution times with a beautiful CLI interface and spinner animation.

![Benchmark exemple while coding](https://i.imgur.com//0uSiias.png)

## Features

- Nanosecond-precision timing measurements
- Spinning progress animation
- Warmup runs for more accurate results
- Support for command-line arguments
- Human-readable time formatting (µs, ms, s)
- Statistical analysis (mean, median, min, max, standard deviation)
- Beautiful Unicode output formatting

## Installation

1. CLone the repository : 
```
git clone https://github.com/luvth/benchmark && cd benchmark
```
2. Make the setup executable :
```bash
chmod +x setup.sh
```
3. Run the setup
```
./setup.sh
```
## Usage

Basic usage:
```bash
benchmark <command> [args...]
```

Options:
- `-n, --iterations`: Number of benchmark iterations (default: 100)
- `-w, --warmup`: Number of warmup runs (default: 3)

## Examples

Benchmark a Python script:
```bash
benchmark python3 your_script.py
```

Benchmark with arguments:
```bash
benchmark your_program arg1 arg2
```

Custom number of iterations:
```bash
benchmark -n 500 your_script.py
```

Specify warmup runs:
```bash
benchmark -w 5 your_script.py
```

## Output Example

```
📊 Benchmark Results:
════════════════════════════════════
📌 Command: python3 script.py
🔄 Iterations: 100
────────────────────────────────────
⌛ Average:  15.23ms
⚡ Minimum:  14.85ms
🐢 Maximum:  17.92ms
📊 Median:   15.12ms
📏 StdDev:   0.45ms
────────────────────────────────────
⏱️  Total Time: 1.52s
════════════════════════════════════
```

## Requirements

- Python 3.6 or higher
- Standard library packages only (no external dependencies)

## Error Handling

- Graceful handling of Ctrl+C interruptions
- Clear error messages for invalid commands or arguments
- Non-zero exit codes for error conditions

## Technical Details

- Uses `time.perf_counter_ns()` for high-precision timing
- Implements threading for spinner animation
- Captures command output to prevent interference with measurements
- Supports any executable command available in system PATH

## License

This tool is released under the MIT License. Feel free to modify and distribute as needed.
