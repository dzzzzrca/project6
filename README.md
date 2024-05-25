# Session 60 - Project 6 - Data Analytics with Hadoop Project

## Tools

- Postgres (via Docker or direct install)
- Hadoop versi < 3.2.1
- Script Project 3 - Batch Processing
- GUI Postgres (Pgadmin, Dbeaver, dll) (optional)

## Preparation

1. Download script proyek terkait batch processing sebelumnya, [link download](https://github.com/MSinggihP/digitaskola_de_10_batch_processing)
2. Pahami script project diatas terlebih dahulu (Tutor akan membantu menjelaskan)
3. Install hadoop (Harusnya sudah di Install pada sesi Hadoop)
    1. [tutorial cara menginstall hadoop](https://www.rosehosting.com/blog/how-to-install-hadoop-on-debian-11/) untuk ubuntu
    2. https://towardsdatascience.com/installing-hadoop-3-2-1-single-node-cluster-on-windows-10-ac258dd48aef untuk windows
    3. https://medium.com/analytics-vidhya/hadoop-single-node-cluster-on-docker-e88c3d09a256 via docker
        1. can run with this command:
        `docker run -d -it --name hadoop-local -p 9864:9864 -p 9870:9870 -p 8088:8088 --hostname hadoop-local hadoop`
4. Jangan lupa untuk tambahkan host nya
    
    ```sql
    127.0.0.1 hadoop-local
    35.222.31.142 hadoop-server
    ```
    
    Add hosts in device windows:
    
    https://ecompile.io/blog/localhost-custom-domain-name
    
5. Setelah install Hadoop, Pastikan apps dibawah ini running:
    1. Hadoop Namenode
    2. Hadoop datanode
    3. YARN Resource Manager
    4. YARN Node Manager
6. 3 Optional untuk menggunakan hadoop dalam project ini:
    1. install hadoop di os device masing2
    2. install hadoop via docker
    3. menggunakan hadoop server dari tutor [http://35.222.31.142:9870](http://35.222.31.142:9870/) (temporary)
7. (Optional) Sambungkan koneksi database postgres dengan GUI yang kalian punya di device masing - masing
8. Flow Project 4 - Data Analytics with Hadoop:
    
    https://drive.google.com/file/d/1rzhm4n4sy4_668xCfLXOlJKhUkj0HV2j/view?usp=sharing
    

## Study Case

Di proyek sebelumnya anda telah membuat batch processing untuk data migrasi. Sebagai tambahan, anda diminta untuk membuat tabel data mart yang nantinya akan digunakan oleh data analis untuk membuat dashboard report order setiap bulannya. Proses yang dilakukan tidak boleh lebih dari 1 jam.

Requirement tabel data mart:

- output columns: `month`, `total_orders`

Setelah memahami tugas yang diberikan, kita bisa menjabarkan task - task apa saja yang harus dikerjakan, task tersebut sebagai berikut:

1. Extract data source ke database postgres (skip, sudah ada di project 3).
2. Buatlah file DWH `dim_orders` dengan menggunakan hadoop.
3. Buatlah data mart `total_orders_based_on_month` dengan MapReduce, data diambil dari DWH.

## Step by Step

1. Proyek ini melanjutkan proyek sebelumnya terkait batch processing. (Silakan dibuka script yang telah disiapkan sebelumnya)
2. Buatlah flow diagram ETL yang akan dibuat
3. Tambahkan koneksi json hadoop
4. Buatlah script koneksi hadoop
5. Define datetime now
6. Buatlah script data dummy DWH ke local terlebih dahulu
7. Buatlah script upload data ke hadoop sebagai DWH
8. Buatlah script transform dengan menggunakan MapReduce
9. Sesuaikan output yang diminta
