# SLURM
Simple Linux Utility for Resource Management

![SLURM](https://github.com/user-attachments/assets/8a84031f-20df-4890-8254-d92150c1d439)

Use nano job_script.sh

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

Shebang

[Shebang](https://github.com/user-attachments/files/19636716/SLURM.pptx)
