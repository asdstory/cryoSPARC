Source: https://cryosparc.com/docs/quickstart/

## Edit following script using your own account and worksation, and run it to install cryosparc.

````
#!/bin/bash
<install_path> = /home/cryosparc_user/software/cryosparc
<license_id> = 682437fb-d2ae-47b8-870b-b530c587da94 #Change to your own license id
<cuda_path> = /usr/local/cud
<ssd_path> = /scratch/cryosparc_cache
<ssd_path> = /scratch/cryosparc_cache
<user_password> = Password123
<user_name> = "FirstName LastName"
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
