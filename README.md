# mount-storage-for-docker-volume
In cloud provider connect your storage to instance, than go to your instance

* Check disk is connected
  ```sh
  lsblk -l
  ```

* than make a partition with
  ```sh
   cfdisk /dev/name_of_your_disk
  ```

* format partition to ext4
  ```sh
  mkfs.ext4 /dev/your_partition
  ```

* mount your partition to the directory
  ```sh
  mount /dev/your_partition /path/to/mount

* add partition to fstab
  ```sh
  blkid
  output: /dev/sda1: UUID="your_uid" TYPE="ext4"
  
  nano /etc/fstab
  and insert: UUID=your_uuid /home/ubuntu/disk auto rw,user,auto 0 0
  
* than create an .htpasswd file in elastic folder
 ``` sh
 htpasswd -c /path/to/elastic/.htpasswd username
 ```

* start docker compose files
``` sh 
sudo docker-compose up -d
sudo docker-compose -f nginx-compose.yaml up -d

