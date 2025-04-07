## SLURM
Simple Linux Utility for Resource Management

![SLURM](https://github.com/user-attachments/assets/8a84031f-20df-4890-8254-d92150c1d439)

#### Use nano job_script.sh

Create a file like job_script.sh with the following content:

```bash
#!/bin/bash
#SBATCH --job-name=my_job_name         # Job name
#SBATCH --output=output_%j.log         # Output log file (%j = job ID)
#SBATCH --error=error_%j.log           # Error log file
#SBATCH --partition=standard           # Partition to use
#SBATCH --nodes=1                      # Number of nodes
#SBATCH --ntasks=4                     # Number of tasks (processes)
#SBATCH --time=01:00:00                # Time limit (HH:MM:SS)
#SBATCH --mem=4G                       # Memory per node

# Load modules and run your application
module load python/3.9

#your script
python my_script.py


sbatch job_script.sh
```

### Shebang

![Shebang](https://github.com/user-attachments/assets/23ef6da0-7bd1-434d-9d3d-38fc2f8d5564)


### Use squeue to check your job status:

```bash
squeue --user=$USER              # Show jobs for current user
squeue --job <job_id>           # Show specific job
squeue --partition=standard     # Filter by partition
squeue --format="%.18i %.9P %.8j %.8u %.2t %.10M %.6D %R"  # Custom format

```

### Cancel or Requeue Jobs

```bash
scancel <job_id>                # Cancel a job
scontrol requeue <job_id>       # Requeue a job

```

<p align="center">
  <img src="https://github.com/user-attachments/assets/79de0224-d0cf-4d41-86ef-a73aa378d36d" alt="SLURM Cheatsheet Part 1" width="49%" />
  <img src="https://github.com/user-attachments/assets/f38eab3a-0e04-4e45-9ff8-784b461f8513" alt="SLURM Cheatsheet Part 2" width="49%" />
</p>
