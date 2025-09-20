# Introduction to Self-Timed Circuits (Summer, 2024)
See [Summer 2023](https://github.com/broccolimicro/course-self-timed-circuits/tree/summer-2023)

**Lecturer:** [Ned Bingham](https://www.nedbingham.com/index.py)

**Time:** June 3, 2024 to August 21, 2024

This course covers the fundamentals of self-timed circuits including timing assumptions and guarantees, failure modes, pipeline structures, data encodings, conditional logic, internal memory, and non-deterministic behavior, hardware description languages for different layers of abstraction, and two design methodologies. It is designed with a bottom up approach, starting with circuitry and working its way up through more abstract representations. Background experience with programming is required, and circuit design is helpful but optional. The course is offered for free with the goal of building local expertise and community in VLSI, Computer Architecture, and Self-Timed Circuits.

There are 24 sessions and each involves roughly 30 minutes of lecture and 30 minutes of exercises. A full toolset will be provided in the form of a docker container for Linux, facilitating both digital and analog simulation. Each session will be recorded and made available within 24 hours.

## Set up the toolset
1. On Ubuntu, install the `docker.io` package from apt: `sudo apt install docker.io`, the `docker-ce` package doesn't let you write files from within the container.
2. Pull the development environment image: `docker pull broccolimicro/broccoli-cli:latest`
3. Clone the [Toolset for Self-Timed Circuits](https://github.com/broccolimicro/bcli.git): `git clone https://github.com/broccolimicro/bcli.git`
4. Clone the [Lectures and Exercises](https://github.com/broccolimicro/course-self-timed-circuits.git): `git clone https://github.com/broccolimicro/course-self-timed-circuits.git`
5. Set up the toolset: `source bcli/bcli-develop.sh`
6. Download the [Skywater 130nm PDK and Configuration Files](https://broccoli-hosting.s3.us-east-2.amazonaws.com/sky130.tar.gz)
7. Extract to your home directory: `mkdir ~/tech; tar -xzvf sky130.tar.gz -C ~/tech`
8. Configure the technology directory location: `export BCLI_TECH="$HOME/tech"`
9. Start the docker container for the toolset: `bcli up`

## Digital and analog simulation
1. Connect to the docker container for the toolset: `bcli`
2. `cd /host/course-self-timed-circuits/lecture_1`
3. fill in `e1.act`
4. compile: `make e1`
5. run the digital simulation: `prsim e1.prs`
6. `source e1.rc`
7. `exit`
8. run the analog simulation: `cd e1`
9. `prsim env.prs`
10. `source prsim.rc`
11. `exit`

## Fundamentals
* Alain Martin. "[The limitations to delay-insensitivity in asynchronous circuits](https://apps.dtic.mil/sti/pdfs/ADA447737.pdf)." Springer New York, 1990.

1. Digital Logic and Production Rules ([slides](https://docs.google.com/presentation/d/1cLKMn4uYdLjXH_-CSFSHtB_IwZgCw5KPNmtQ7OIhKKQ/edit?usp=sharing), video)
2. Introduction to Self-Timed Circuits ([slides](https://docs.google.com/presentation/d/1OzqIr0iPFxu5Yyru-aGmRNN8m_EwbITPKqGwrZ-rIzQ/edit?usp=sharing), video)
3. Weak Condition Half Buffers (slides, video)
4. Fundamental Concepts (slides, video)
5. Pre-Charge Half Buffers (slides, video)
6. Encoding Data (slides, video)

## Templated Synthesis
* Andrew Lines. "[Pipelined asynchronous circuits](https://authors.library.caltech.edu/26834/5/CSTR1998.pdf)." California Institute of Technology, 1998.

7. Multiple Requests (slides, video)
8. Early Out and Stack Length (slides, video)
9. Conditional Inputs and Outputs (slides, video)
10. Internal Memory (slides, video)
11. Protected Forward Drivers (slides, video)
12. ACT Language (slides, video)

## Formal Synthesis
* Alain Martin. "[Synthesis of asynchronous VLSI circuits](https://authors.library.caltech.edu/26746/2/postscript.pdf)." California Institute of Technology, 1991.
* Rajit Manohar. "[An analysis of reshuffled handshaking expansions](https://csl.yale.edu/~rajit/ps/2phase.pdf)." Proceedings Seventh International Symposium on Asynchronous Circuits and Systems (ASYNC), IEEE, 2001.
* Martin, Alain J. "[The design of an asynchronous microprocessor](https://authors.library.caltech.edu/26709/2/postscript.pdf)." (1989).
* Manohar, Rajit, and Alain J. Martin. "[Slack elasticity in concurrent computing](https://csl.yale.edu/~rajit/ps/mpc98.pdf)." International Conference on Mathematics of Program Construction. Berlin, Heidelberg: Springer Berlin Heidelberg, 1998.
* Manohar, Rajit, Tak-Kwan Lee, and Alain J. Martin. "[Projection: A synthesis technique for concurrent systems](https://csl.yale.edu/~rajit/ps/proj.pdf)." Proceedings. Fifth International Symposium on Advanced Research in Asynchronous Circuits and Systems. IEEE, 1999.

13. Handshake Expansion and Reshuffling (slides, video)
14. Projection and Process Decomposition (slides, video)
15. Simulation and State Elaboration (slides, video)
16. State Conflicts and State Variable Insertion (slides, video)
17. Guard Strengthening (slides, video)
18. Bubble Reshuffling (slides, video)

## Advanced Topics
* Jackson, Sandra, and Rajit Manohar. "[Gradual synchronization](https://csl.yale.edu/~rajit/ps/gsync.pdf)." International Symposium on Asynchronous Circuits and Systems (ASYNC). IEEE, 2016.
* Bingham, Ned, and Rajit Manohar. "[QDI constant-time counters](https://www.nedbingham.com/papers/counter/QDI%20Constant%20Time%20Counters.pdf)." Transactions on Very Large Scale Integration Systems, volume 27 issue 1 pages 83-91. IEEE, 2018.
* Bingham, Ned, and Rajit Manohar. "[A Systematic Approach for Arbitration Expressions](https://nedbingham.com/papers/arbiters/A%20Systematic%20Approach%20for%20Arbitration%20Expressions.pdf)." Transactions on Circuits and Systems I: Regular Papers, volume 67 issue 12 pages 4960-4969. IEEE, 2020.

19. Exchange Channels (slides, video)
20. Design Strategies (slides, video)
21. Implementation Strategies (slides, video)
22. Synchronization and Non-Deterministic Behavior (slides, video)
23. Arbitration Expressions (slides, video)
24. Asynchronous to Synchronous Interfacing (slides, video)
