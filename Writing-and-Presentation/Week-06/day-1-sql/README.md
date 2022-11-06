# Database
Database adalah sebuah tempat dimana data disimpan dalam bentuk tabel dan data dari tabel dapat diakses menggunakan query. Database berada dibalik layar yang umumnya berbeda dengan server yang terhubung dengan dunia luar(internet). Server database biasanya hanya local dan interaksi database hanya melalui server utama yang meminta data untuk keperluan processing.

# SQL Basic
Berikut adalah list dari query database dasar yang sering digunakan dengan sedikit penjelasan:


```sql
-- Membuat database
create database db_name;

-- Memilih database
use db_name;

-- Membuat sebuah tabel didatabase yang dipilih
create table table_name (
    coloumn_name1 coloumn_data_type,
    coloumn_name2 coloumn_data_type,
    ...
    coloumn_nameN coloumn_data_type,
);
/* ada special case dalam pembuatan tabel seperti tabel
 id sebagai primary key dan auto_increment */
create table table_name (
    id int primary key auto_increment,
    coloumn_name1 coloumn_data_type,
    coloumn_name2 coloumn_data_type,
    ...
    coloumn_nameN coloumn_data_type,
);

-- Melihat tabel yang ada pada sebuah database
show tables;

-- Melihat tabel secara detail
desc table_name;

-- Menghapus tabel
drop table table_name;

-- Menambahkan sebuah coloumn setelah tabel dibuat
alter table table_name add coloumn_name data_type;

-- Memasukan 1 data ketabel
insert into table_name (coloum1_name, coloumn2_name, ... , coloumnN_name) values
(coloum1_value, coloum2_value, ... , coloumN_value);

-- Memasukan banyak data ketabel
insert into table_name (coloum1_name, coloumn2_name, ... , coloumnN_name) values
(coloum1_value, coloum2_value, ... , coloumN_value)
(coloum1_value, coloum2_value, ... , coloumN_value)
... --  dapat disesuaikan dengan banyak data yang harus dimasukkan
(coloum1_value, coloum2_value, ... , coloumN_value);

-- Membaca data dalam tabel
select * from table_name;
/* 
* = all
query bisa dibilang
select all from table_name
*/

-- mengedit data
update table_name set coloumn_name = "new_value" where condition;
-- update tabel pada coloumn_name dimana condition(true);

-- delete data
delete from table_name where condition;
-- hapus data di table_name dimana condition(true);

-- menampilkan beberapa coloumn saja saat ingin melihat table
select coloumn1_name, coloumn2_name, ... from table_name;

-- menggunakan alias untuk mengubah nama coloumn saat querying
select coloumn1_name as HALO, coloumn2_name from table_name;
/*
akan menampilkan coloumn1_name sebagai halo dan coloumn2_name
tanpa perubahan
*/

-- ambil sebuah data dengan pola
select * from table_name where coloumn_name like pattern;
/*
pattern disini berupa /regex/ sederhana:
1. "R%" == /^R.+/ --> pilih semua dengan depan R.
2. "%@gmail.com" == /.+(@gmail.com)/ pilih semua yang diakhiri dengan @gmail.com.
3. "%o%" == /.+o.+/ pilih semua yang ada o ditengah-tengah.
*/

-- ambil data dengan limit N
select * from table_name limit N;

-- urutkan select berdasarkan alphanumeric
select * from table_name order by coloumn ASC|DESC
/*
jika coloum angka maka akan di sort dari terkecil|terbesar
jika coloum huruf maka akan di sort dari a|z
*/

```