# Google Play Store Analytics
<img src="https://raw.githubusercontent.com/fafilia/capstone-UIFlask/master/full_capstone.png">
## Introduction
This project was developed as one of the capstone projects at the Algorithm Academy Data Analytics Specialization. The expected deliverables are that you can build a simple web application (dashboard) using the Flask framework. This project will focus on the appearance of the Flask user interface.

## Data Summary
The data used in this project's capstone is scraped data from the Google Playstore App. The Google Playstore App data consists of several variables with the following details:
- `App` : Application name
- `Category` : Application category
- `Rating` : Overall rating given by application users (when scraped)
- `Reviews` : The number of reviews given by application users (when scraped)
- `Size` : Application size(when scraped)
- `Installs` : The number of users who installed/downloaded the application (when scraped)
- `Type` : Application type (paid/free)
- `Price` : App price (when scrap)
- `Content Rating` : The age group this app is targeted at - Children / Mature 21+ / Adult
- `Genres` : Application genre.
- `Last Updated` : Date when the app was last updated on Play Store (when it was scrapped)
- `Current Ver` : Current version of app available in Play Store (when discrap)
- `Android Ver` : Minimum Android version required (when scrapped)

## Dependencies
- Flask
- Matplotlib
- Pandas
- Numpy

You can install all of these dependencies in this way :
```
pip install -r requirements.txt
```

## Rubrics
Pada capstone ini, Anda diharapkan untuk dapat membangun sebuah aplikasi Flask yang fokus pada tampilan user interface. Langkah pertama yang harus Anda lakukan adalah silahkan download atau clone repositori ini. File pada repositori ini merupakan sebuah skeleton untuk membuat sebuah dashboard aplikasi Flask. Pada bagian `app.py` dan `templates/index.html` ada beberapa bagian yang rumpang dan harus Anda lengkapi. Beberapa bagian yang harus diperhatikan adalah sebagai berikut:

### 1. Setting Repository Github dan Environment (2 poin)
- Repository 

a. Membuat repository baru di Github

b. Clone repository tersebut ke local dengan git clone
- Environment 

a. Created virtual environment called "capstone-flask"

Hal pertama yang harus dilakukan adalah melakukan pengaturan environment conda. Untuk menyiapkan conda environment dan kernel, silahkan gunakan command berikut:
```
conda create -n <ENV_NAME> python=3.7
conda activate <ENV_NAME>

conda install ipykernel
python -m ipykernel install --user --name <ENV_NAME>
```

b. Install packages: pandas, flask, matplotlib, dan numpy
Seluruh dependecies telah di-export ke dalam file requirements.txt. Oleh karena itu untuk melakukan install packages, Anda dapat menggunakan perintah berikut:
```
pip install -r requirements.txt --user
```

### 2. Data Preproses and Exploratory Data Analysis (2 poin)
Pada tahap praproses ini, Anda diminta untuk melengkapi praproses data seperti menghapus data yang duplikat, mengubah tipe data dan memodifikasi nilai data. Pada file `app.py` Anda diminta untuk melengkapi data yang rumpang tanpa mengubah alur praproses yang telah ada.
Berikut ini contoh bagian yang harus Anda lengkapi saat praproses data:
```
playstore._________(subset ="_____", keep = '_____', inplace=True) 
playstore.drop([10472], inplace=True)
# Buang tanda koma(,) dan tambah(+) kemudian ubah tipe data menjadi integer
playstore.Category = playstore.Category.astype('category')
playstore.Installs = ________.apply(lambda x: x.replace(______))
playstore.Installs = ________.apply(lambda x: x.replace(______))
```
### 3. Data Wrangling (4 poin)
- Pada tahap ini Anda diminta untuk melakukan grouping dan agregasi data. Data wrangling digunakan untuk menyiapkan data yang tepat sesuai analisis yang diminta. Pada capstone ini terdapat objek dictionary dengan nama `stats` dan Anda diminta untuk melengkapi bagian yang rumpang agar menghasilkan data/nilai yang sesuai. Sebagai gambaran pada objek `stats` terdapat variabel `rev_tablel` dimana Anda harus melakukan grouping dan agregasi data yang digunakan untuk membuat data table seperti di bawah ini:
<img src="https://raw.githubusercontent.com/fafilia/capstone-UIFlask/master/table_rev.PNG" width=400>

### 4. Data Visualization (4 poin)
- Membuat atau menduplikasi bar plot yang menggambarkan top 5 Category pada Google Playstore
- Membuat atau menduplikasi scatter plot yang menggambarkan sebaran aplikasi jika dilihat berdasarkan Review, Rating, dan jumlah aplikasi yang terinstall.
- Membuat atau menduplikasi histogram plot untuk melihat distribusi ukuran aplikasi 
- Membuat 1 plot tambahan bebas yang dapat merepresentasikan insight di dalam data

*Notes : Anda dapat melihat contoh plot lain yang hraus dibuat/diduplikat pada repositori ini. Silahkan clone/download repositori ini. 

### 5. Build Flask App (4 poin)
Mengacu pada poin ke empat Data Visualization di atas, selain membuat plot baru Anda harus mendemonstrasikan bagaimana cara merender plot tersebut pada aplikasi Flask dan menampilkannya pada templates / halaman html. Yang perlu Anda perhatikan adalah pada bagian `app.py`:
```
render_templates(__________)
```
dan pada `templates/index.html` Anda perlu memanggil source plot.png tempat Anda menyimpan gambar plot tersebut.
```
<img src="________________________" height="450" width=500>
```
