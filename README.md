# Thread_Safe_DS

Small collection of thread-safe data-structure implementations and a lab report demonstrating them.

## Repository layout
- labReport/report.tex         — LaTeX report (includes screenshots and source listings)
- exercise1.cpp               — Thread-safe queue & stack (Producer/Consumer, Undo/Redo)
- priorityQueue.cpp           — Thread-safe priority queue
- circularBuffer.cpp          — Thread-safe circular buffer (condition variables)
- threadSafeDeque.cpp         — Thread-safe deque
- threadSafeLinkedList.cpp    — Thread-safe linked list
- README.md                   — this file

## Prerequisites
- g++ (>= 9) with pthread support
- make (optional)
- LaTeX toolchain: pdflatex (or latexmk)
- Linux (dev container uses Ubuntu 24.04.2 LTS in this workspace)

Install minimal packages on Ubuntu:
```bash
sudo apt update
sudo apt install -y build-essential g++ make texlive-latex-recommended texlive-latex-extra texlive-fonts-recommended
```

## Build & run C++ examples
From the repository root, compile an exercise and run it. Examples:
```bash
g++ -std=c++17 -O2 -pthread exercise1.cpp -o exercise1
./exercise1
```
Replace `exercise1.cpp` with any other source (priorityQueue.cpp, circularBuffer.cpp, threadSafeDeque.cpp, threadSafeLinkedList.cpp). Add `-Wall -Wextra` to enable warnings.

## Build the PDF report
From the repo root:
```bash
cd labReport
pdflatex report.tex
pdflatex report.tex
```
The report includes code listings and screenshots. If images are missing, pdflatex will still compile but the figures will be empty placeholders.

## Notes
- The examples use coarse-grained locking for correctness and simplicity; performance/scalability trade-offs are discussed in the report.
- If compilation of any C++ example fails, run with `-Wall -Wextra` and inspect the errors. Missing headers or C++ standard mismatches are the most common causes.
- The LaTeX file uses the `float` package for strict figure placement; edit only when you need to change formatting — content is intended to match the lab submission.

## Contributing
Open issues or submit PRs for fixes, additional examples, or improved tests.

## License
No license specified. Contact the repository owner for reuse permissions.