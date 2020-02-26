Source: https://cryosparc.com/docs/quickstart/

## Edit following script using your own account and worksation, and run it to install cryosparc.

````
#!/bin/bash
<install_path> = /home/dout2/Application/cryosparc
<license_id> = 133a762e-54e1-11ea-88c5-6b3d93485143 #Change to your own license id
<worker_path> = /home/dout2/Application/cryosparc/cryosparc2_worker
<cuda_path> = /usr/local/cuda
<ssd_path> = /scratch/nvme-ssd/cryosparc_cache
<ssd_path> = /scratch/nvme-ssd/cryosparc_cache
<user_password> = d000001
<user_name> = "Tongyi Dou"
<port_number> = 39000
#SSH into the workstation as cryosparc_user (the UNIX user that will run all cryosparc processes, could be your personal account). The following assumes bash is your shell.

cd <install_path>
export LICENSE_ID="<license_id>"

curl -L https://get.cryosparc.com/download/master-latest/$LICENSE_ID > cryosparc2_master.tar.gz
curl -L https://get.cryosparc.com/download/worker-latest/$LICENSE_ID > cryosparc2_worker.tar.gz

tar -xf cryosparc2_master.tar.gz
tar -xf cryosparc2_worker.tar.gz

cd cryosparc2_master

./install.sh    --standalone \
                --license $LICENSE_ID \
                --worker_path <worker_path> \
                --cudapath <cuda_path> \
                --ssdpath <ssd_path> \
                --initial_email <user_email> \
                --initial_password <user_password> \
                --initial_name <user_name> \

source ~/.bashrc

````

## After completing the above, navigate your browser to http://<workstation_hostname>:39000 to access the cryoSPARC user interface.
