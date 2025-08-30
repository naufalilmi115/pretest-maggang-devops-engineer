# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

1. DevOps merupakan pendekatan yang menyatukan Dev (development/pengembangan) dan Ops (operations/operasional) dengan tujuan mempercepat sekaligus meningkatkan kualitas proses pembuatan serta pengelolaan aplikasi. Dengan adanya integrasi ini, tim pengembang dan tim operasional tidak lagi bekerja secara terpisah, melainkan berkolaborasi sejak tahap perencanaan, penulisan kode, pengujian, hingga implementasi dan pemeliharaan sistem. Melalui praktik DevOps, organisasi dapat merilis aplikasi lebih cepat, mendeteksi serta memperbaiki kesalahan lebih dini, dan memastikan layanan tetap stabil serta efisien dalam memenuhi kebutuhan pengguna.

2. Infrastructure (infrastruktur) adalah kumpulan komponen fisik maupun virtual berfungsi sebagai dasar untuk mengoperasikan, mengelola, serta mendukung layanan teknologi informasi. Di dalamnya termasuk perangkat keras, perangkat lunak, jaringan, dan berbagai fasilitas yang memastikan aplikasi maupun layanan digital dapat berfungsi secara optimal.

3. Server adalah sistem komputer, baik fisik maupun virtual, yang menyediakan layanan, data, atau sumber daya bagi komputer lain (client) melalui jaringan dan dirancang untuk bekerja terus-menerus. Beberapa implementasinya meliputi Web Server untuk menyajikan konten website seperti e-commerce atau blog (contoh: Apache, Nginx), File/Database Server untuk menyimpan dan mengelola data aplikasi atau sistem informasi (contoh: Samba Server, FTP Server), serta Proxy Server yang berfungsi sebagai perantara dalam pengelolaan akses internet di lingkungan seperti sekolah atau perusahaan (contoh: Squid Proxy Server).

4. Server dibutuhkan dalam pengembangan software karena berperan sebagai pusat penyimpanan data, kode, dan konfigurasi aplikasi yang bisa diakses oleh seluruh tim. Server juga menyediakan lingkungan testing dan staging untuk menguji aplikasi sebelum dirilis, mendukung kolaborasi antar developer, serta memungkinkan otomatisasi proses build, test, dan deployment melalui CI/CD. Dengan adanya server, pengembangan aplikasi menjadi lebih efisien, aman, terkontrol, dan memastikan layanan dapat diakses secara konsisten.

5. Virtualisasi adalah teknologi yang memungkinkan satu perangkat keras menjalankan beberapa mesin virtual (VM) secara bersamaan, masing-masing dengan sistem operasi dan aplikasinya sendiri. Setiap VM terisolasi, sehingga masalah pada satu VM tidak memengaruhi VM lain. Virtualisasi menggunakan hypervisor untuk membagi resource seperti CPU, RAM, dan storage, dan biasanya digunakan untuk mengoptimalkan pemanfaatan hardware, membuat backup, cloning, serta menjalankan berbagai environment secara bersamaan.
 Container adalah teknologi ringan yang memungkinkan aplikasi dijalankan secara terisolasi bersama semua dependensinya di atas sistem operasi host tanpa perlu OS lengkap seperti VM. Container lebih cepat dan efisien dalam penggunaan resource, mempermudah deployment, scaling, dan menjaga konsistensi aplikasi di berbagai environment. Contohnya adalah Docker dan Kubernetes, yang banyak digunakan untuk menjalankan microservices dan aplikasi modern.

6. Container populer karena ringan, cepat, dan hanya membawa aplikasi beserta dependensinya, sehingga startup lebih cepat dibanding VM. Sifatnya yang portabel dan konsisten di berbagai lingkungan, mudah diskalakan untuk microservices, efisien dalam penggunaan resource, mendukung otomatisasi DevOps/CI/CD, dan menjaga isolasi aplikasi agar sistem tetap stabil.

7. Orchestration Container System adalah teknologi yang digunakan untuk mengelola, mengatur, dan mengotomatisasi deployment serta operasi banyak container dalam skala besar. Dengan sistem ini, container dapat dijalankan, dipantau, dan diskalakan secara otomatis tanpa harus dikelola satu per satu, sehingga memudahkan pengelolaan aplikasi yang kompleks. Contoh populer dari sistem ini antara lain Kubernetes, Docker Swarm, dan OpenShift.

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

