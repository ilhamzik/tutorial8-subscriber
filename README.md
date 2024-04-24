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
