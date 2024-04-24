# Tutorial Modul 8 - Subscriber
### Muhammad Ilham Zikri
### 2206083533
### Pemrograman Lanjut A

## 1. What is **amqp**?
AMQP (_Advanced Message Queueing Protocol_) adalah protokol open-source yang bisa mengatur message queuing di antara aplikasi atau komponen perangkat lunak.

Di dalam file main.rs, saya menggunakan protokol AMQP untuk menerima pesan dari sebuah antrian menggunakan library crosstown_bus. AMQP digunakan untuk menangkap dan mengelola pesan yang masuk dari antrian bernama user_created. Setiap kali ada pesan baru di dalam antrian, fungsi penanganan yang kami sebut UserCreatedHandler akan diaktifkan untuk mengolah pesan tersebut.

## 2. What it means? `guest:guest@localhost:5672` , what is the first **guest**, and what is the second **guest**, and what is `localhost:5672` is for?
guest pertama pada kode tersebut merupakan username yang digunakan untuk mengakses server _AMQP_ _RabbitMQ_. sedangkan guest kedua merupakan password dari username, yang dimana pada kode tersebut merupakan guest. 

localhost:5672 merujuk pada tempat kode ini dijalankan,yaitu pada mesin lokal itu sendiri, yang mendengar pada port `5672`. 

![image](https://github.com/ilhamzik/tutorial8-subscriber/assets/124953758/dbbb14f1-67e0-4d53-a46b-a9d7354bbb85)

3 terminal subscriber
![image](https://github.com/ilhamzik/tutorial8-subscriber/assets/124953758/3a51baa7-2181-439f-ac46-fd6ae6301e)

Ketika menjalankan beberapa aplikasi subscriber untuk satu antrian yang sama, jumlah pesan yang diterima oleh setiap subscriber akan berkurang dibandingkan jika hanya ada satu subscriber. RabbitMQ menggunakan strategi load balancing untuk mendistribusikan pesan di antara subscriber yang tersedia. Secara default, RabbitMQ menggunakan strategi round-robin untuk mendistribusikan pesan ke subscriber yang terhubung ke antrian yang sama. Artinya, jika terdapat tiga subscriber terhubung ke antrian "user_created", setiap subscriber akan menerima sekitar sepertiga dari total pesan yang dikirimkan ke antrian tersebut. Contohnya, jika ada 15 pesan yang dikirimkan ke antrian "user_created" dan ada tiga subscriber terhubung, masing-masing subscriber akan menerima sekitar 5 pesan (dengan asumsi pembagian merata). Namun, jika hanya ada satu subscriber yang terhubung ke antrian, subscriber tersebut akan menerima semua pesan yang dikirimkan ke antrian. Strategi load balancing ini bertujuan untuk membagi beban kerja antara subscriber dan meningkatkan throughput keseluruhan sistem. Dengan lebih banyak subscriber, setiap subscriber hanya perlu memproses sebagian dari total pesan, yang dapat mengurangi kemacetan dan meningkatkan kinerja sistem secara keseluruhan.
