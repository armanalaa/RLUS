**RLUS: Rate Limit Update Service**

Welcome to the RLUS project repository! RLUS (Rate Limit Update Service) provides a statistical toolbox for computing and effectively managing API throttling limits. 

**Project Background**

Rate limiting is critical for managing access to APIs, protecting resources, and enabling value-added services. RLUS provides a principled approach to determining the optimal query rate limits to ensure API usage aligns with organizational goals. By leveraging statistical models and algorithms, RLUS empowers public and private entities to balance access and control effectively.

**Use Cases**

- Throttling API access for public and private services.
- Supporting value-added services while protecting sensitive system metrics.
- Preventing unauthorized analysis of service-le
- Efficiently setting query limits for APIs based on real-time data.

**Repository Contents**

RLUS-BINARY-SEARCH/: Binary search-based algorithm implementation.

RLUS-BRUTEFORCE/: Brute-force algorithm implementation.

RLUS-HEURISTIC_H1/ to RLUS-HEURISTIC_H4/: Various heuristic search methods.

README.md: Documentation of the project.


Each repository is structured as follows:

**Repository Contents**

| Directory             | Description                                           |
|-----------------------|-------------------------------------------------------|
| `data/`               | Contains input datasets.                             |
| `results/`            | Contains computed outputs in `.csv` format.          |
| `logs/`               | Stores real-time execution logs.                     |


- data/: Contains input datasets.

scripts/: Shell scripts for running, evaluating, and managing the RLUS algorithms.

 - master_script.sh: Orchestrates the parallel execution of various scripts, including run_20.sh to run_26.sh.

 - measure_time.sh: Tracks the time taken by master_script.sh and logs it into a time log file (master_script_time.log).

 - run_20.sh to run_29.sh: Executes specific Python-based computations with different configurations and epsilon ranges, logging the results for each range.

- results/: Contains computed \rho outputs from the scripts, stored as CSV files:

- logs/: Real-time execution logs.

**How to Use This Repository**

Quick Start (Using RLUS-BINARY-SEARCH as an Example)

1. Clone the repository:
   
   ```bash
    git clone https://github.com/armanalaa/RLUS.git
   ```
   ```bash
    cd RLUS/RLUS-BINARY-SEARCH
   ```
   
   ```bash
    cd RLUS/RLUS-BINARY-SEARCH
   ```

2. Set up the environment: Use Docker for a consistent and isolated environment:

  a. Building the Docker Image:

   ```bash
    docker build -t RLUS-BINARY-SEARCH .
   ```
    
  b. Run the RLUS-BINARY-SEARCH Example: Inside the container or locally (if dependencies are installed):
    
   ```bash
    # Windows
    docker run -v %cd%:/app RLUS-BINARY-SEARCH
   ```
   ```bash
    # Linux
    docker run -v $(pwd):/app RLUS-BINARY-SEARCH
   ```

**Check Live Log**

```bash
docker logs -f RLUS-BINARY-SEARCH # Stream live logs from the Docker container.
```
```bash
docker logs RLUS-BINARY-SEARCH | tail -n 100 # retrieve the last 100 lines of logs from the RLUS-BINARY-SEARCH Docker container, aiding in monitoring and debugging
```

 
**Check Results**

 ```bash    
 sudo docker cp RLUS-BINARY-SEARCH:/app/results .
 ```
 ```bash
 sudo docker cp RLUS-BINARY-SEARCH:/app/logs .
 ```

  - The commands copy the results and log directories from the /app path inside the RLUS-BINARY-SEARCH Docker container to the current directory on your host system.
  - This lets you access the container's output files directly on your local machine.
  - In the results folder, the sample size (rho) values in the .csv format is saved.
  - In the logs folder, the execution times in the .text format is saved.
 
**Known Issues**

- Memory Usage: Some algorithms may require significant memory for large datasets.

- Execution Time: Brute-force algorithms are computationally expensive compared to heuristic methods.

- Docker Compatibility: Ensure Docker is correctly installed and updated.

**Citations** (to be updated..)

If you use RLUS in your research or project, please cite:

Ala Arman, Donatella Firmani, Francesco Leotta, Massimo Mecella, Marzio Monticelli. "An Adaptive Toolbox for Computing Throttling Rate Limits in Web APIs." (2024). Available at https://github.com/armanalaa/RLUS

**Acknowledgments**

This work was inspired by collaboration with public service operators and supported by the "Dipartimento di Eccellenza" grant and the H2020 RISE project FIRST (#734599). Special thanks to Manuel Coppotelli and the Italian Ministry of Infrastructure and Transport for their contributions.

Contact

For any questions or feedback, feel free to reach out:

- Prof. Donatella Firmanai

  - donatella.firmani@uniroma1.it 

- Assistant Prof. Ala Arman

  - Email: ala.arman@gmail.com

