https://github.com/ProgrammerZamanNow/belajar-docker-dasar

# docker image  
docker image ls -> liat semua image docker  
docker image pull redis:latest -> namaimage:tag  
docker image rm hello-world:latest -> namaimage:tag  
  
container masih perlu image untuk running

# container list  
docker container ls -a => melihat semua container  
docker container ls -> hanya leihat container yang berjalan

# container create stop remove  
docker container create --name namacontainer namaimage:tag -> buat container  
docker container start namacontainer/idcontainer -> buat running container  
docker container stop namacontainer/idcontainer -> buat stop container  
docker container rm namacontainer -> harus dihentikan dulu baru bisa dihapus

# container logs  
docker container logs containerId/namacontainer -> nampilin log yg udah ada  
docker container logs -f containerId/namacontainer -> melihat logs tanpa blocking  
docker container logs --details containerid/namacontainer -> logs biasa

# container exec  
docker container exec -i -t containerId/namacontainer /bin/bash -> untuk mengeksekusi program yang ada di dalam container  
  
-i -> interaktif  
-t -> argumen untuk alokasi pseudo-TTY (terminal akses)

# container port  
docker container create --name namacontainer --publish porthost:portcontainer namaimage:tag-> port forwarding

# environment variable  
docker container create --name namacontainer --env KEY="value" --env KEY2="value2" image:tag

# container stats  
docker container stats

# container resource limit  
contoh:  
docker container create --name samllnginx --publish 8081:80 --memory 100m --cpus 0.5 ngix:latest
  
kalau nggak dikasih dia bisa menggunakan 100% yang dikasih ke docker
