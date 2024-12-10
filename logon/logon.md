# Logon Writeup - picoCTF

Halo semuanya!!

Beginilah caraku menyelesaikan salah satu challenge picoCTF **Logon**.

## 1. Langkah Awal
Kita sudah tahu bahwa kita disuruh login pada websitenya:

![Login Page](https://prod-files-secure.s3.us-west-2.amazonaws.com/f9787adf-148f-4979-803f-4b03bd638a07/95889894-756f-40ae-acde-ca49e6f17289/image.png)

## 2. Login Tanpa Password
Aku mencoba login tanpa memasukkan password, dan ternyata berhasil!

![Login Successful](https://prod-files-secure.s3.us-west-2.amazonaws.com/f9787adf-148f-4979-803f-4b03bd638a07/49ddd169-6f59-4c77-9627-17465d287548/image.png)

Namun, tidak ada flag yang muncul.

## 3. Analisis dengan Burp Suite
Karena merasa ada yang janggal, aku membuka Burp Suite untuk menganalisis request dan hasilnya seperti ini:

![Burp Suite Intercept](https://prod-files-secure.s3.us-west-2.amazonaws.com/f9787adf-148f-4979-803f-4b03bd638a07/233828ee-fd33-491a-bad2-4bb1ee168059/image.png)

## 4. Temuan Parameter `admin=false`
Setelah mem-forward request, aku menemukan sesuatu yang mencurigakan: `admin=false`.

![Admin Parameter](https://prod-files-secure.s3.us-west-2.amazonaws.com/f9787adf-148f-4979-803f-4b03bd638a07/52597c72-0e9d-482d-a0c8-2d7d4af90797/image.png)

## 5. Mengubah `admin=false` menjadi `admin=true`
Aku mengganti nilai `false` menjadi `true`. Pastikan memperhatikan huruf besar/kecil (meskipun tidak selalu diperlukan, lebih baik berhati-hati).

![Edit Admin Parameter](https://prod-files-secure.s3.us-west-2.amazonaws.com/f9787adf-148f-4979-803f-4b03bd638a07/832930ad-31be-40aa-ba51-aeb6854bd796/image.png)

## 6. Flag Ditemukan
Setelah mem-forward request lagi, akhirnya flag muncul!

![Flag Found](https://prod-files-secure.s3.us-west-2.amazonaws.com/f9787adf-148f-4979-803f-4b03bd638a07/7c490dd8-179b-4de8-9879-ca771f96596f/image.png)
