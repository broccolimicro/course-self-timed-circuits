# Introduction to Self Timed Circuits (Summer, 2023)

**Lecturer:** [Ned Bingham](https://www.nedbingham.com/index.py)

**Time:** May 15, 2023 to August 16, 2023

This course covers the fundamentals of self-timed circuits including timing assumptions and guarantees, failure modes, pipeline structures, data encodings, conditional logic, internal memory, and non-deterministic behavior, hardware description languages for different layers of abstraction, and two design methodologies. It is designed with a bottom up approach, starting with circuitry and working its way up through more abstract representations. Background experience with programming is required, and circuit design is helpful but optional. The course is offered for free with the goal of building local expertise and community in VLSI, Computer Architecture, and Self-Timed Circuits.

There are 24 sessions and each involves roughly 30 minutes of lecture and 30 minutes of exercises. A full toolset will be provided in the form of a docker container for Linux, facilitating both digital and analog simulation. Each session will be recorded and made available within 24 hours.

## Set up the toolset
1. On Ubuntu, install the `docker.io` package from apt: `sudo apt install docker.io`, the `docker-ce` package doesn't let you write files from within the container.
2. Pull the development environment image: `docker pull public.ecr.aws/l5h5o6z4/broccoli-cli:latest`
3. Clone the [Toolset for Self Timed Circuits](https://git.broccolimicro.io/Broccoli/broccoli-cli.git): `git clone https://git.broccolimicro.io/Broccoli/broccoli-cli.git`
4. Clone the [Lectures and Exercises](https://github.com/nbingham1/async-course): `git clone https://github.com/nbingham1/async-course.git`
5. Set up the toolset: `source broccoli-cli/bcli-develop.sh`
6. Download the [Skywater 130nm PDK and Configuration Files](https://broccoli-hosting.s3.us-east-2.amazonaws.com/sky130.tar.gz)
7. Extract to your home directory: `mkdir ~/tech; tar -xzvf sky130.tar.gz -C ~/tech`
8. Configure the technology directory location: `export BCLI_TECH="$HOME/tech"`
9. Start the docker container for the toolset: `bcli up`

## Digital and analog simulation
1. Connect to the docker container for the toolset: `bcli`
2. `cd /host/async-course/lecture_1`
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

1. Digital Logic and Production Rules ([slides](https://docs.google.com/presentation/d/1cLKMn4uYdLjXH_-CSFSHtB_IwZgCw5KPNmtQ7OIhKKQ/edit?usp=share_link), [video](https://youtu.be/_dsd3ecJ-8Y))
2. Introduction to Self Timed Circuits ([slides](https://docs.google.com/presentation/d/1OzqIr0iPFxu5Yyru-aGmRNN8m_EwbITPKqGwrZ-rIzQ/edit?usp=share_link), [video](https://youtu.be/nOvawxM2c1I))
3. Weak Condition Half Buffers ([slides](https://docs.google.com/presentation/d/1Ae6GOhyKmqAqawERvFYdDchxlWtKP1cmSZtyE2wq20E/edit?usp=share_link), [video](https://youtu.be/a-rgJJXfn2I))
4. Fundamental Concepts ([slides](https://docs.google.com/presentation/d/1f23xGafgNvVpY4guUtqyL1xsdXDWSiiRfqSzW01iOHA/edit?usp=share_link), [video](https://youtu.be/Im1H-s8ZOvU))
5. Pre-Charge Half Buffers ([slides](https://docs.google.com/presentation/d/1Fg7Uer-RXjpMPTauT6M7l8CnJ1Y1Dcn6qQndKsx_7Bg/edit?usp=share_link), [video](https://youtu.be/6bvNrrWV1Ks))
6. Encoding Data ([slides](https://docs.google.com/presentation/d/1PHXakPZGedAyphqwSpcx1uw0RQ562dQeh3ZTjLnZw2s/edit?usp=share_link), [video](https://youtu.be/PkEi-iDIyPA))

## Templated Synthesis
* Andrew Lines. "[Pipelined asynchronous circuits](https://authors.library.caltech.edu/26834/5/CSTR1998.pdf)." California Institute of Technology, 1998.

7. Multiple Requests ([slides](https://docs.google.com/presentation/d/1s_f3T7RSWY7VonrMGS_M-SNdooi7cuic0O5wLWw85O4/edit?usp=share_link), [video](https://youtu.be/51VIQZzjbcY))
8. Early Out and Stack Length ([slides](https://docs.google.com/presentation/d/1iFA7rXCNSSa9zDEqBfaddh-w30ixjOPi9SmSWKnzHjM/edit?usp=share_link), [video](https://youtu.be/cwQGCfJ8ouQ))
9. Conditional Inputs and Outputs ([slides](https://docs.google.com/presentation/d/1nXX4WGaIJvcG3CUZzMOjIllyQe81UEInZ6kzA65aitg/edit?usp=share_link), [video](https://youtu.be/vPRKxspzhaY))
10. Internal Memory ([slides](https://docs.google.com/presentation/d/1Tme2K670CnikIEX6aqYH_krpukfNJIAZXqUp0d_spv4/edit?usp=share_link), [video](https://youtu.be/iLYEX_bV1-Q))
11. Protected Forward Drivers ([slides](https://docs.google.com/presentation/d/1CO_WGqkgJpxIOGpSIcCbnd1i7_t2oloIKbncIudVl5E/edit?usp=share_link), [video](https://youtu.be/t1L7jFcWvKs))
12. ACT Language ([slides](https://docs.google.com/presentation/d/169Bvo2WfLbIdNftJpTsod2BLpuai5bUOgmNEvfK_cyk/edit?usp=sharing), [video](https://youtu.be/HiLu4iZKn80))

## Formal Synthesis
* Alain Martin. "[Synthesis of asynchronous VLSI circuits](https://authors.library.caltech.edu/26746/2/postscript.pdf)." California Institute of Technology, 1991.
* Rajit Manohar. "[An analysis of reshuffled handshaking expansions](https://csl.yale.edu/~rajit/ps/2phase.pdf)." Proceedings Seventh International Symposium on Asynchronous Circuits and Systems (ASYNC), IEEE, 2001.
* Martin, Alain J. "[The design of an asynchronous microprocessor](https://authors.library.caltech.edu/26709/2/postscript.pdf)." (1989).
* Manohar, Rajit, and Alain J. Martin. "[Slack elasticity in concurrent computing](https://csl.yale.edu/~rajit/ps/mpc98.pdf)." International Conference on Mathematics of Program Construction. Berlin, Heidelberg: Springer Berlin Heidelberg, 1998.
* Manohar, Rajit, Tak-Kwan Lee, and Alain J. Martin. "[Projection: A synthesis technique for concurrent systems](https://csl.yale.edu/~rajit/ps/proj.pdf)." Proceedings. Fifth International Symposium on Advanced Research in Asynchronous Circuits and Systems. IEEE, 1999.

13. Handshake Expansion and Reshuffling ([slides](https://docs.google.com/presentation/d/1Cjdcc43FuQkDwYWfZaaUgW7zwDpzmnJi6e053RyDCiI/edit?usp=share_link), [video](https://youtu.be/sAV6k8oy0qQ))
14. Projection and Process Decomposition ([slides](https://docs.google.com/presentation/d/1fXyl0wN0fv4famViQDVF_8QApX_w_qpV0blpjHbfB8M/edit?usp=share_link), [video](https://youtu.be/vEq8xGYPv1c))
15. Simulation and State Elaboration ([slides](https://docs.google.com/presentation/d/1EAigIlVp28rD18Mkruxvsko_O_NQGI2qISWhO0gteHo/edit?usp=share_link), [video](https://youtu.be/YvWJSxtVFVU))
16. State Conflicts and State Variable Insertion ([slides](https://docs.google.com/presentation/d/1NI-LZrIMI5yvlKZjqODRm32WSbFEpjYA7WzkWfSq0Ug/edit?usp=sharing), [video](https://youtu.be/yjr1paF0nZA))
17. Guard Strengthening ([slides](https://docs.google.com/presentation/d/1S8ujsxvv7ltKwSV2uigVr-9X6ETQeYiRBgNnjnOvZWQ/edit?usp=sharing), [video](https://youtu.be/ng_nlX8wLdg))
18. Bubble Reshuffling ([slides](https://docs.google.com/presentation/d/1pYNqix_kSkc02P3PfxtAyoQcAnKbhx0ZJ0ZSoFoJegI/edit?usp=sharing), [video](https://youtu.be/yPcKZXKuYLM))

## Advanced Topics
* Jackson, Sandra, and Rajit Manohar. "[Gradual synchronization](https://csl.yale.edu/~rajit/ps/gsync.pdf)." International Symposium on Asynchronous Circuits and Systems (ASYNC). IEEE, 2016.
* Bingham, Ned, and Rajit Manohar. "[QDI constant-time counters](https://www.nedbingham.com/papers/counter/QDI%20Constant%20Time%20Counters.pdf)." Transactions on Very Large Scale Integration Systems, volume 27 issue 1 pages 83-91. IEEE, 2018.
* Bingham, Ned, and Rajit Manohar. "[A Systematic Approach for Arbitration Expressions](https://nedbingham.com/papers/arbiters/A%20Systematic%20Approach%20for%20Arbitration%20Expressions.pdf)." Transactions on Circuits and Systems I: Regular Papers, volume 67 issue 12 pages 4960-4969. IEEE, 2020.

19. Exchange Channels ([slides](https://docs.google.com/presentation/d/1bujkCqs-5HKKHDRdo_iM0S6Byzh8RAWoymV6BtUTdvA/edit?usp=sharing), [video](https://youtu.be/Axt62h4xwpE))
20. Design Strategies ([slides](https://docs.google.com/presentation/d/1735DeGTcIrFjmesAWIuHNHNa_zZTKaqzHVCPDckyKU8/edit?usp=sharing), [video](https://youtu.be/q-kXIVXnIqM))
21. Implementation Strategies ([slides](https://docs.google.com/presentation/d/1uSolp00w9HCGm745ZWZ_vtcJndgYpUsQVVaFwhME5N4/edit?usp=sharing), [video](https://youtu.be/nqi-XvYiTXQ))
22. Synchronization and Non-Deterministic Behavior ([slides](https://docs.google.com/presentation/d/1ybkYp-tTL46dY55aAq2HqurGcnwElfrnLPaaca4T1Fg/edit?usp=sharing), [video](https://youtu.be/HFPgRnr1A4M))
23. Arbitration Expressions ([slides](https://docs.google.com/presentation/d/1hfMYihDBMVtDfJ3LPqE1Yk6iAPw83NG43BmTYJZF1TI/edit?usp=sharing), [video](https://youtu.be/p67RmRL7C_s))
24. Asynchronous to Synchronous Interfacing ([slides](https://docs.google.com/presentation/d/1UyWOnfrYo1JnUG4SKZ8hMDjiY-bNxN9FPVhxRP5AcuY/edit?usp=sharing), [video](https://youtu.be/PC8Rf9AMBHE))
