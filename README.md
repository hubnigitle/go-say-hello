1. Membuat module di Go
   1. Buat project misal 'go-say-hello'
   2. Buat repository di github dengan nama yang sama (direkomendasikan)
   3. Pada terminal project ketik 'go mod init github.com/usernameGithub/go-say-hello'
   4. Akan terbuat file go.mod
   5. Buat file baru misal 'say_hello' lalu isi file sesuai dengan kode yang diiginkan misal hanya mengeluarkan output 'Hello'
   6. git init
   7. git add go.mod
   8. git add say_hello.go
   9. git status (memastikan go.mod dan say_hello sudah berhasil di add)
   10. git commit -m 'membuat module say hello'
   11. git remote add origin https://github.com/usernameGithub/go-say-hello.git
   12. git push origin master
   13. git tag v1.0.0
   14. git push origin v1.0.0
   15. pastikan repository sudah terupdate dengan tag v1.0.0
       
2. Menggunakan module di aplikasi go (main project)
   1. Buat repository github untuk aplikasi main project misal 'app-say-hello'
   2. Buat project di text editor (rekomendasi new window) beri nama yang sama 'app-say-hello'
   3. Buat file main.go yang nantinya akan menggunakan module go yang sudah dibuat
   4. Pada terminal project ketik 'go mod init github.com/usernameGithub/app-say-hello'
   5. go get github.com/usernameGithub/go-say-hello (menggunakan modul go-say-hello)

3. Minor upgrade module
   1. Buat perubahan kecil pada module 'go-say-hello' di file 'say_hello.go' misal dengan menambahkan output menjadi 'Hello world'
   2. git add say_hello.go
   3. git commit -m 'update SayHello'
   4. git tag v1.1.0
   5. git push origin v1.1.0
   6. Lihat repository untuk memastikan tag v1.1.0 sudah terupdate
   7. Untuk melakukan upgrade dependency ubah file 'go.mod' dalam aplikasi menjadi versi terbaru, misal v1.0.0 menjadi v1.1.0
   8. Pada terminal ketik 'go get'
      
5. Major upgrade module
   1. Lakukan perubahan major pada file say_hello.go yang ada dalam project go-say-hello, misal dengan menambahkan parameter name
   2. Pada file go.mod tambahkan '/v2' pada alamat github menjadi 'github.com/usernameGithub/go-say-hello/v2'
   3. git add go.mod say_hello.go
   4. git commit -m 'update say hello dengan menambahkan parameter nama'
   5. git push origin master
   6. git tag v2.0.0
   7. git push origin v2.0.0
   8. Cek di repository github

6. Update dependency ke v2.0.0
   1. Pada project 'app-say-hello' buka file go.mod dan hapus require datanya lalu save
   2. Lalu pada terminal ketik 'go get github.com/usernameGithub/go-say-hello/v2@v2.0.0'
   3. Gunakan module pada main.go
  
PS : i am using go 1.22.4
