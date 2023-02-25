<img src="https://img.shields.io/badge/Spring-6DB33F?style=for-the-badge&logo=spring&logoColor=white" />
<img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white" />

<br>
# Aplikasi Invoice Management #
 Aplikasi ini dipakai untk mengelola dan menyambungkan dengan berbagai
 metode. <br>
 Diatara metode pembayaran yang akan di support antara lain :
 * Virtual Account Bank
    * Bank BNI
    * Bank CIMB
    * Bank BSI
 
* E Wallet
    * Ovo
    * Gopay
  
* QR Payment
    * QRis

# Setup Database using docker
1. Jalankan service docker desktop
   2. Jalankan posgresql di docker
       ```docker
       docker run --rm \
           --name invoice-db \
           -e POSTGRES_DB=invoicedb \
           -e POSTGRES_USER=invoice \
           -e POSTGRES_PASSWORD=FvKmDaHdz6Mby9aL43kZ \
           -e PGDATA=/var/lib/postgresql/data/pgdata \
           -v "$pwd/invoice_db:/var/lib/postgresql/data" \
            -p 5432:5432 \
             postgres:13
       ```
      2. Buka terminal pada docker & ketik command berikut: 
      ```
       psql -h 127.0.0.1 -U invoice invoicedb
      ```
      3. Buat properties di resources/application.yml
      ```yml
      spring:
       datasource:
        url: jdbc:postgresql://localhost/invoicedb
        username: invoice
        password: FvKmDaHdz6Mby9aL43kZ
       jpa:
         hibernate:
          ddl-auto: validate
       show-sql: true
       properties:
        hibernate:
          format_sql: true
      ```

