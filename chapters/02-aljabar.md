# Kuliah 2: Aljabar

Seri kuliah “Mekanika Kuantum Minimalis 2.0” ini ditujukan bagi para pelajar fisika secara khusus, serta sains dan teknologi secara umum, untuk dapat menggunakan (dan syukur-syukur memahami) mekanika kuantum sehingga kita tidak terlalu ketinggalan mengikuti perkembangan “Revolusi Kuantum 2.0”.  Sebelum benar-benar “tercemplung” dalam berbagai postulat mekanika kuantum, pada awal-awal ini kita siapkan terlebih dahulu kelengkapan “persenjataan” kita, terutama terkait metode matematis yang menunjang pemahaman mekanika kuantum.  Statistika memiliki peranan penting dalam mekanika kuantum, terutama untuk memahami konsep pengukuran.  Oleh karenanya, kita akan menelaah ulang statistika dasar dalam sesi kali ini, yang secara khusus melibatkan pembahasan tentang rerata, momen, dan probabilitas (peluang).

## Rerata Data Terukur

Misalkan kita ingin mengukur nilai besaran $x$ dari suatu objek.  Untuk melakukannya, kita cari alat ukur $x$ dan melakukan beberapa pengukuran untuk memperoleh $N$ buah nilai $x$, yakni $x_1$, $x_2$, $x_3$, dst.  Kita dapat melabeli hasil pengukuran ini sebagai $x_i$, dengan $i = 1, 2, \ldots, N$.  Nilai rata-rata (**atau sering kita singkat rerata**) $\langle x \rangle$ dari besaran $x$ dapat diperoleh dengan menjumlahkan seluruh nilai hasil pengukuran $x_i$ dan membaginya dengan banyaknya pengukuran atau banyaknya data $N$.  Secara matematis, kita dapat menuliskannya sebagai
```{math}
:label: eq:xrerata

\langle x \rangle = \frac{1}{N} \sum_{i=1}^{N} x_{i}.
```

Simbol “braket" $\langle \ldots \rangle $ merupakan simbol rerata dari suatu besaran yang berada di dalam braket tersebut.  Jadi, $\langle x \rangle $ merupakan rerata $x$, $\langle x^n \rangle $ merupakan rerata $x^n$, dst.  Untuk menghitung $\langle x^n \rangle $, kita dapat menggunakan formula serupa pers. {eq}`eq:xrerata`, yakni:
```{math}
:label: eq:xnrerata

\langle x^n \rangle = \frac{1}{N} \sum_{i=1}^{N} \left(x_{i} \right)^n.
```
Nama lain dari $\langle x^n \rangle$ adalah momen orde ke-$n$ dari $x$ (“$n$th-order moment of $x$”).  Selain itu, dalam statistika, nilai rata-rata dikenal sebagai *mean*.  Sebagai informasi tambahan, referensi lain tentang statistika juga cukup sering menotasikan *mean* dengan “bar”, misalnya $\bar{x}$ (dibaca “$x$-bar”), tetapi dalam seluruh seri kuliah ini kita akan menggunakan notasi braket.  Karena braket $\langle \ldots \rangle$ bermakna kita dapat merata-ratakan apapun besaran di dalamnya, kita juga bisa mencari nilai rata-rata dari sembarang fungsi $f(x)$, yakni:
```{math}
:label: fxrerata

\langle f(x) \rangle = \frac{1}{N} \sum_{i=1}^{N} f(x_{i}).
```

Besaran rerata bersifat linear, yang berarti bahwa rata-rata dari penjumlahan seluruh fungsi atau besaran yang diukur merupakan penjumlahan dari rata-rata setiap fungsi atau besaran tersebut. Secara matematis, kita dapat menuliskan:
```{math}
:label: eq:kombfxrerata

\langle A_1 f_1(x)+ A_2 f_2(x) \rangle 
  =  A_1 \langle f_1(x) \rangle + A_2 \langle f_2(x) \rangle,
```
dengan $A_1$ dan $A_2$ adalah suatu konstanta.

Terkadang kita ingin melihat seberapa jauh suatu nilai pengukuran $x$ melebar dari reratanya.  Gagasan ini disebut dengan deviasi (*deviation*) atau simpangan, $\delta x$, yang secara matematis dapat didefinisikan sebagai
```{math}
:label: eq:devx

\delta x = x - \langle x \rangle.
```
Dengan menggunakan sifat linear rerata [pers. {eq}`eq:kombfxrerata`], kita dapat buktikan bahwa rerata deviasi ternyata bernilai nol,
```{math}
:label: eq:devxNotfluct

\langle \delta x \rangle = 
  \langle x - \langle x \rangle \rangle = 
  \langle x \rangle - \langle \langle x \rangle \rangle 
  = \langle x \rangle - \langle x \rangle = 0.
```

Rerata deviasi bernilai nol karena peluang dari deviasi bernilai positif sama besar dengan peluangnya bernilai negatif sehingga $\delta x$ tidak dapat menjadi indikator yang baik untuk menunjukkan fluktuasi besaran fisis.  Untuk mengatasi masalah ini, kita bisa merata-ratakan kuadrat dari $\delta x$, yakni
```{math}
:label: eq:defvariansi

\begin{aligned}
\langle (\delta x)^2 \rangle
    =& \langle (x - \langle x \rangle)^2 \rangle 
    =& \langle (x^2 - 2x \langle x \rangle 
    + \langle x \rangle^2) \rangle 
    =& \langle x^2 \rangle 
    + \langle (-2 \langle x \rangle x) \rangle 
    + \langle (\langle x \rangle^2) \rangle 
    =& \langle x^2 \rangle - 2 \langle x \rangle \langle x \rangle
    + \langle x \rangle^2, 
    \therefore \langle (\delta x)^2 \rangle
    =& \langle x^2 \rangle - \langle x \rangle^2.
\end{aligned}
```

Hasil akhir yang diberikan pada pers. {eq}`eq:defvariansi` kemudian didefinisikan sebagai variansi, yakni $\Delta x^2$, yang merupakan variansi dari besaran $x$, sedangkan akar kuadrat variansi dikenal sebagai simpangan baku (*standard deviation*) dari $x$, yakni $\Delta x$.  Secara matematis, variansi dituliskan sebagai
```{math}
:label: eq:varx

\Delta x^2 \equiv \langle (\delta x)^2 \rangle 
  = \langle x^2 \rangle - \langle x \rangle^2,
```
sedangkan simpangan baku dituliskan sebagai
```{math}
:label: eq:stdx

\Delta x \equiv \sqrt{\Delta x^2} 
  = \sqrt{\langle x^2 \rangle - \langle x \rangle^2}.
```
Simpangan baku dapat menjadi indikator seberapa jauh suatu hasil pengukuran menyimpang dari reratanya.  Dalam mekanika kuantum, kita menggunakan konsep ini untuk menguantifikasi **ketidakpastian** suatu proses pengukuran.

:::{admonition} Contoh soal: Rerata dan simpangan baku dari data pengukuran
:class: tip


Serangkaian pengukuran $x$ menghasilkan nilai sebagai berikut:
```{math}
:label: eq:data

x_i = 9, 5, 25, 23, 10, 22, 8, 8, 21,
  20; \quad i = 1, \ldots, 10.
```
Hitunglah rerata dan simpangan baku dari data tersebut.

**Solusi:**
Untuk menghitung rerata dari $x$ kita dapat menggunakan
pers. {eq}`eq:xrerata`:
```{math}

\langle x \rangle = 
  \frac{1}{10} (9 + 5 + 25 + 23 + 10 + 22 + 8 + 8 + 21 + 20)
  = 15{,}1.
```
Selanjutnya, untuk menghitung simpangan baku, kita hitung dulu $\langle x^2 \rangle$.  Dengan menggunakan pers. {eq}`eq:xnrerata`, kita dapatkan
```{math}

\langle x^2 \rangle = \frac{1}{10}
  (9^2 + 5^2 + 25^2 + 23^2 + 10^2 + 22^2 + 8^2 + 8^2 
  + 21^2 + 20^2) = 281{,}3.
```
Substitusi hasil tersebut pada pers. {eq}`eq:stdx` menghasilkan
```{math}

\Delta x = \sqrt{281{,}3 - (15{,}1)^2} = 7{,}3.
```
Dengan menggunakan simpangan baku sebagai ketidakpastian pengukuran, kita dapat menuliskan $x = 15{,}1 \pm 7{,}3$.
:::
## Probabilitas
Mari kita tinjau data pengukuran pada contoh soal sebelumnya [pers. {eq}`eq:data`] dengan sedikit berbeda, yakni dengan membuat histogram data tersebut.  Kita memecah seluruh rentang data menjadi $M$ bagian yang kita sebut sebagai “kelas interval” (dalam bahasa Inggris dikenal pula sebagai “*bin*”).  
Setiap kelas interval memiliki lebar yang sama dan dilabeli sebagai $x_j$ ($j = 1,2,3, \ldots M$).  Perhatikan indeks $j$ digunakan untuk setiap kelas interval alih-alih $i$ karena kita hanya melabeli setiap kelas dengan sebuah nilai $x_j$ walaupun dalam satu kelas tersebut ada kemungkinan masuknya beberapa hasil pengukuran $x_i$.  Kita kelompokkan pengukuran individu $x_i$ yang dapat masuk pada kelas interval $x_j$ kemudian kita hitung banyaknya pengukuran pada kelas tersebut.  Banyaknya data yang masuk $x_j$ dinotasikan $N(x_j)$. Proses semacam ini dikenal dengan *histogramming* ataupun *binning*.

Sekarang kita coba membuat histogram dari data pada contoh soal sebelumnya.  Rentang datanya dari $5$ sampai dengan $25$.  Kita dapat memecah rentang ini menjadi $7$ kelas interval dengan lebar yang sama. Kelas interval pertama mengandung nilai pengukuran $5, 6$ dan $7$, dan dapat kita labeli dengan $x_1 = 6$, yang merujuk pada nilai tengahnya. Kelas interval kedua kita labeli dengan $x_2 = 9$, yang mengandung nilai pengukuran individu $8, 9$ dan $10$, begitu seterusnya.

Merujuk data pada pers. {eq}`eq:data`, kita menemukan hanya satu pengukuran yang menghasilkan nilai $5$.  Dengan demikian, jumlah pengukuran pada kelas interval pertama adalah $N(6) = 1$. Selanjutnya, pada kelas interval kedua, ada empat nilai pengukuran (dua bernilai $8$, satu bernilai $9$, dan satu bernilai $10$) sehingga $N(9) = 4$. Kelas interval ketiga tidak mengandung nilai pengukuran karena tidak ada nilai $11, 12$ dan $13$ sehingga pada kelas interval ketiga dapat kita tuliskan $N(12) = 0$.  Begitulah seterusnya sehingga plot histogram data pers. {eq}`eq:data` seperti ditunjukkan pada Gambar {numref}`fig:01-histogram`.


```{figure} ../figures/01-histogram-probability.svg
:name: fig:01-histogram
:align: center

Histogram data pada sumbu vertikal bagian kiri dan kerapatan probabilitas pada sumbu vertikal bagian kanan.
```

Histogram memungkinkan kita untuk memperkirakan probabilitas yang akan kita peroleh dari suatu pengukuran tertentu.  Probabilitas $P(x_j)$ bahwa suatu pengukuran akan berada pada suatu kelas interval tertentu $x_j$ secara sederhana merupakan perbandingan dari jumlah pengukuran yang ada pada kelas interval tersebut terhadap total seluruh jumlah pengukuran.  Secara matematis, kita dapat tulis,
```{math}
:label: eqprob

P\left(x_j \right) =\frac{N\left(x_j \right)}{N}.
```

Distribusi probabilitas histogram juga diplot pada sumbu vertikal sebelah kanan Gambar {numref}`fig:01-histogram`.
Plot $N(x_j)$ berimpit dengan $P(x_j)$ dengan skala yang berbeda.  Oleh karena itu, distribusi probabilitas dapat dikatakan sebagai suatu versi histogram yang diskalakan.

Penjumlahan semua nilai histogram $N(x_j)$ harus menghasilkan total jumlah pengukuran $N$.  Jika histogram memiliki $M$ kelas interval, kita dapatkan
```{math}

\sum_{j=1}^{M} P\left(x_j \right) 
  = \frac{\sum_{j=1}^{M} N\left(x_j \right)}{N} = \frac{N}{N} = 1,
```
sehingga probabilitasnya ternormalisasi dengan benar, yakni jumlah seluruh probabilitas bernilai $1$.

Persamaan {eq}`eqprob` memberikan suatu estimasi probabilitas yang cukup kasar jika jumlah pengukuran $N$ kecil.  Selain itu, dengan $N$ yang kecil, kelas interval yang digunakan semestinya cukup lebar sehingga resolusi $x$ dari $P(x_j)$ tidaklah begitu baik.  Sebaliknya, jika $N$ besar, kita mungkin memperoleh estimasi $P\left(x_j \right)$ yang cukup akurat dengan resolusi tinggi.

Satu hal penting yang kadang perlu kita lakukan untuk suatu distribusi probabilitas adalah gambar grafiknya.  Hal ini memungkinkan kita untuk memvisualisasikan data kita, dan melihat nilai terukur mana yang mungkin terjadi dan mana yang tidak.  Sebagai contoh, Gambar {numref}`fig:01-histogram` memberikan informasi bahwa pengukuran $x$ ternyata mengelompok ke dalam daerah-daerah tertentu.  Pembuatan plot ini lebih informatif daripada hanya mengatakan $x = 15{,}1 \pm 7{,}3$.  Kita juga dapat menggunakan probabilitas untuk menghitung momen-momen secara langsung, tanpa harus kembali pada data awal. Jika $P\left(x_j \right)$ diketahui untuk $j = 1,2,\ldots M,$ rerata $x$ dapat dituliskan sebagai
```{math}
:label: eq:meanx

\langle x \rangle = \sum_{j = 1}^{M} x_j P\left(x_j \right).
```
Oleh karena itu, untuk menghitung rerata, kita beri bobot nilai kelas interval dengan probabilitasnya dan selanjutnya jumlahkan semua nilai yang mungkin.  Secara umum, rerata sembarang fungsi $f(x)$ diberikan oleh
```{math}
:label: eq:meanfx

\langle f(x) \rangle = \sum_{j = 1}^{M} f\left(x_j\right) P\left(x_j \right).
```

:::{admonition} Rerata dan simpangan baku berdasarkan distribusi probabilitas
:class: tip


Hitung rerata dan simpangan baku dari data pada contoh soal sebelumnya, kali ini dengan menggunakan distribusi probabilitas. 

**Solusi:** 
Gambar {numref}`fig:01-histogram` menunjukkan histogram data yang perlu kita rujuk.  Kita dapat menggunakan histogram ini untuk mengestimasi distribusi probabilitas sesuai pers. {eq}`eqprob`. Distribusi probabilitas ini diplot pada sumbu vertikal bagian kanan dari Gambar {numref}`fig:01-histogram`. Dengan menggunakan probabilitas ini dan pers. {eq}`eq:meanx`, kita peroleh rerata $x$ adalah
```{math}

\langle x \rangle = (6) (0{,}1) + (9)(0{,}4) + (21)(0{,}3)+(24)(0{,}2)= 15{,}3.
```
Sementara itu, momen kedua dapat dihitung sesuai pers. {eq}`eq:meanfx`
```{math}

\langle x^2 \rangle = (6)^2 (0{,}1) + (9)^2(0{,}4) + (21)^2(0{,}3)+(24)^2(0{,}2)= 283{,}5.
```
Dengan demikian, simpangan bakunya adalah
```{math}

\Delta x = \sqrt{ 283{,}5 - (15{,}3)^2} = 7{,}0
```

:::

Perlu diperhatikan bahwa perhitungan $\langle x \rangle$ yang menggunakan perkiraan distribusi probabilitas pada contoh soal di atas tidak sama persis dengan perhitungan langsung seperti pada contoh soal pertama meskipun penentuan nilai $\langle x \rangle$ masih dalam rentang simpangan baku.  Ketidaksamaan ini dikarenakan distribusi probabilitas pada Gambar {numref}`fig:01-histogram` merupakan sebuah estimasi dari distribusi yang sebenarnya.  Dalam batas jumlah pengukuran yang cukup besar dan resolusi $f\left(x_j\right)$ yang sangat baik, estimasi distribusi akan mendekati distribusi yang sesungguhnya, dan nilai rerata yang dihitung menggunakan probabilitas akan sangat mendekati nilai rerata yang diperoleh langsung dari data.

## Distribusi Probabilitas Kontinu

Sejauh ini kita telah membahas probabilitas yang ditentukan oleh nilai diskret $x$. Sebagai contoh, $P\left(x_j \right)$ untuk $j =1, 2, \ldots, M$.  Ketika kita berbicara data yang sesungguhnya, kita selalu memiliki resolusi pengukuran yang terbatas sehingga distribusi probabilitas pengukuran akan selalu menjadi diskret. Namun, secara teoretis kita dapat membahas distribusi probabilitas dari variabel kontinu.

Tinjau posisi $x$ dari suatu partikel. Posisi merupakan variabel kontinu dan secara prinsip partikel dapat berada di mana saja.  Karena partikel dapat berada di mana saja, probabilitas partikel tersebut untuk berada pada suatu tempat tertentu adalah nol.  Sebagai contoh, probabilitas menemukan partikel yang secara pasti berada pada $x = 9,99 \ldots $ adalah nol, berbeda dengan probabilitas partikel berada pada suatu rentang tertentu, misalnya di antara $x = 9{,}99$ dan $x =10{,}00$.  Jika rentangnya kecil, probabilitas menemukan partikel akan sebanding dengan rentang tersebut.  Sebagai contoh, sebuah partikel yang berada pada interval $$2\,\mu\mathrm{m}$$ itu dua kali lipat lebih mungkin ditemukan  dibandingkan dengan pada interval $$1\,\mu\mathrm{m}$$.

Jika kita ambil $dx$ sebagai interval yang kecil, probabilitas $P\left(x\right)$ partikel akan ditemukan di antara $x$ dan $x+dx$ adalah
```{math}

P(x) = p(x) dx,
```
dengan $p(x)$ dikenal sebagai kerapatan probabilitas dari $x$. Distribusi kontinu dinormalisasi dengan mengintegrasikan kerapatan probabilitas terhadap seluruh rentangnya.  Jika sebuah partikel dapat ditemukan di mana saja di antara $x = - \infty $ dan $x = \infty$, kondisi normalisasinya adalah
```{math}

\int_{- \infty}^{\infty} p(x) dx = 1.
```

Pada kasus probabilitas diskret, kita telah lihat cara menghitung reratanya melalui pembobotan setiap nilai pengukuran dengan probabilitasnya, dan jumlahkan seluruh nilai-nilai yang mungkin. Untuk distribusi kontinu, pada dasarnya kita dapat melakukan hal yang serupa, tetapi penjumlahannya diganti oleh suatu integral.  Jadi, rerata variabel $x$ untuk distribusi kontinu adalah
```{math}

\langle x \rangle = \int_{- \infty}^{\infty} x p(x) dx,
```
sementara rerata sembarang fungsi $f(x)$ adalah
```{math}

\langle f(x) \rangle = \int_{- \infty}^{\infty} f(x) p(x) dx.
```
Jika kita ingin menghitung simpangan baku $x$, kita melakukan hal yang sama seperti pada kasus diskret pada pers. {eq}`eq:stdx`.

## Probabilitas Gabungan dan Kondisional

Terkadang kita tertarik pada probabilitas lebih dari satu peristiwa. Sebagai contoh, kita ingin mengetahui probabilitas sebuah partikel memiliki nilai besaran tertentu $x$ dan besaran tertentu $y$.  Dengan kata lain, partikel memiliki kedua nilai tersebut secara bersamaan. Probabilitas tersebut dinotasikan dengan $P(x,y)$ yang merupakan **probabilitas gabungan** untuk $x$ dan $y$.

Kerapatan probabilitas gabungan, $p(x,y)$, memiliki karakteristik penting bahwa integrasi terhadap satu variabel akan menghasilkan kerapatan probabilitas variabel yang lain. Sebagai contoh,
```{math}

p(x) = \int_{-\infty}^{\infty} p(x,y) \,dy.
```
Dalam hal ini, $p(x)$ merupakan kerapatan **probabilitas marginal** untuk kejadian $x$ [demikian pula, $p(y)$ adalah probabilitas marginal untuk $y$].  Sementara itu, rerata diperoleh dengan mengintegralkan terhadap kedua variabel:
```{math}

\langle f(x,y) \rangle = \int_{- \infty}^{\infty} f(x,y) p(x,y) dx dy.
```

Pada situasi tertentu, kita mungkin juga ingin mengetahui probabilitas memperoleh $x$ jika nilai $y$ tertentu diketahui.  Kita tuliskan probabilitas semacam ini sebagai $P(x|y)$, dan menyebutnya sebagai **probabilitas kondisional** karena merepresentasikan probabilitas $x$ yang terkondisikan oleh $y$. Probabilitas gabungan dan kondisional dihubungkan oleh formula Bayes, yakni
```{math}

P(x,y) = P(x|y) P(y).
```
Kelak, formula ini akan bermanfaat dalam tinjauan sifat-sifat sistem komposit (seperti kasus multipartikel), misalnya dalam pembahasan fenomena keterbelitan (*entanglement*).

## Latihan (Soal-Jawab)

:::{admonition} Soal
:class: exercise

  Tinjau suatu himpunan data A ($x_i$): $10, 13, 14, 14, 6, 8, 7, 9, 12, 14, 13, 11, 10, 7, 7$.
  
  
i.  Hitunglah rerata dan variansi data A langsung dari himpunan tersebut.
  
ii.  Buatlah histogram data A dan perkirakan distribusi probabilitasnya. Petunjuk: Gunakan angka $5$ sebagai nilai minimum dan $14$ sebagai nilai maksimum dalam $5$ buah kelas interval. Jika ada angka $5$ atau $6$ dalam data, masing-masing masuk ke kelas interval pertama yang dilabeli $x_1 = 5{,}5$. Selanjutnya, untuk angka $7$ dan angka $8$ akan masuk kelas interval kedua yang dilabeli $x_2 = 7{,}5$. Demikian seterusnya sampai $x_5 = 13{,}5$.
  
iii.  Gunakan distribusi probabilitas dari poin (ii) untuk menghitung rerata data A.
  
iv.  Hitunglah variansi dari distribusi probabilitas pada poin (ii) menggunakan dua formula berbeda, yakni $\langle (\delta x)^2 \rangle = \langle (x - \langle x \rangle)^2 \rangle$ dan $\langle (\delta x)^2 \rangle = \langle x^2 \rangle - \langle x \rangle^2$.
  
:::

:::{dropdown} Jawaban

  (i) Rerata langsung dari himpunan data A dengan jumlah total data $N = 15$ dapat dihitung sebagai berikut:
  \begin{align*}
   \langle x \rangle &= \frac{1}{N} \sum_{i=1}^{15} x_i 
    &= \frac{10+13+14+14+6+8+7+9+12+14+13+11+10+7+7}{15} 
    &= \frac{155}{15} = \frac{31}{3} \approx 10{,}33.
  \end{align*}
  Untuk mendapatkan variansi $\Delta x^2 = \langle x^2 \rangle - \langle x \rangle^2$, kita perlu hitung dulu momen kedua,
  \begin{align*}
    \langle x^2 \rangle =& \frac{1}{15} \sum_{i=1}^{15} x_i^2 
    =& \frac{100+169+196+196+36+64+49+81}{15}  &+\frac{144+196+169+121+100+49+49}{15} 
    =& \frac{1719}{15} = \frac{573}{5} = 114{,}6.
  \end{align*}
  Maka, variansinya adalah:
  \begin{equation*}
\Delta x^2 = 114,6 - \left(\frac{31}{3}\right)^2 = \frac{1719}{15} - \frac{961}{9} = \frac{5157 - 4805}{45} = \frac{352}{45} \approx 7{,}82.
  \end{equation*}

  (ii) Histogram dan distribusi probabilitas data A.
  
    
- Kelas 1 ($5 \leq x \leq 6$), $x_1 = 5{,}5$:
    data $\{6\}$, $N(x_1) = 1$, $P(x_1) = 1/15$.
    
- Kelas 2 ($7 \leq x \leq 8$), $x_2 = 7{,}5$: 
    data $\{7, 7, 7, 8\}$, $N(x_2) = 4$, $P(x_2) = 4/15$.
    
- Kelas 3 ($9 \leq x \leq 10$), $x_3 = 9{,}5$: 
    data $\{9, 10, 10\}$, $N(x_3) = 3$, $P(x_3) = 3/15 = 1/5$.
    
- Kelas 4 ($11 \leq x \leq 12$), $x_4 = 11,5$:
    data $\{11, 12\}$, $N(x_4) = 2$, $P(x_4) = 2/15$.
    
- Kelas 5 ($13 \leq x \leq 14$), $x_5 = 13,5$:
    data $\{13, 13, 14, 14, 14\}$, $N(x_5) = 5$, $P(x_5) = 5/15 = 1/3$.
  

  
```{figure} ../figures/01-latihan-a-histogram.svg
:name: fig:01-latihan-a-histogram
:align: center

Histogram data A.
```


  (iii) Rerata dari distribusi probabilitas poin (ii).
  \begin{align*}
    \langle x \rangle &= \sum_{j=1}^5 x_j P(x_j) 
    &= 5{,}5\left(\frac{1}{15}\right) + 7{,}5\left(\frac{4}{15}\right) + 9{,}5\left(\frac{3}{15}\right) + 11{,}5\left(\frac{2}{15}\right) + 13{,}5\left(\frac{5}{15}\right) 
    &= \frac{5{,}5 + 30{,}0 + 28{,}5 + 23{,}0 + 67{,}5}{15} = \frac{154{,}5}{15} = 10{,}3.
  \end{align*}

  (iv) Kita hitung variansi dari distribusi probabilitas dengan dua formula berbeda.
  Formula pertama: $\langle (\delta x)^2 \rangle = \langle (x - \langle x \rangle)^2 \rangle$
  \begin{align*}
    \langle (\delta x)^2 \rangle &= \sum_{j=1}^5 (x_j - 10{,}3)^2 P(x_j) 
    &= (-4{,}8)^2\left(\frac{1}{15}\right) + (-2{,}8)^2\left(\frac{4}{15}\right) + (-0{,}8)^2\left(\frac{3}{15}\right) + (1{,}2)^2\left(\frac{2}{15}\right) + (3{,}2)^2\left(\frac{5}{15}\right) 
    &= \frac{23{,}04(1) + 7{,}84(4) + 0{,}64(3) + 1{,}44(2) + 10{,}24(5)}{15} 
    &= \frac{23{,}04 + 31{,}36 + 1{,}92 + 2{,}88 + 51{,}20}{15} = \frac{110{,}4}{15} = 7{,}36.
  \end{align*}

  Formula kedua: $\langle (\delta x)^2 \rangle = \langle x^2 \rangle - \langle x \rangle^2$
  \begin{align*}
    \langle x^2 \rangle &= \sum_{j=1}^5 x_j^2 P(x_j) 
    &= (5,5)^2\left(\frac{1}{15}\right) + (7,5)^2\left(\frac{4}{15}\right) + (9,5)^2\left(\frac{3}{15}\right) + (11,5)^2\left(\frac{2}{15}\right) + (13,5)^2\left(\frac{5}{15}\right) 
    &= \frac{30{,}25 + 225{,}00 + 270{,}75 + 264{,}50 + 911{,}25}{15} = \frac{1701{,}75}{15} = 113{,}45.
  \end{align*}
  \begin{equation*}
    \langle (\delta x)^2 \rangle = 113{,}45 - (10{,}3)^2 = 113{,}45 - 106{,}09 = 7{,}36.
  \end{equation*}
  Kedua formula menghasilkan variansi yang sama, yakni $7{,}36$.
:::


:::{admonition} Soal
:class: exercise

  Tinjau suatu himpunan data B $(x_i, y_i)$: $(3,4)$, $(5,8)$, $(4,4)$, $(8,5)$, $(3,5)$, $(4,5)$, $(5,8)$, $(8,5)$, $(8,4)$, $(3,4)$, $(3,8)$, $(4,8)$.
  
  
i.  Tentukan $P(x)$ dan $P(y)$ untuk setiap pengukuran $x$ dan $y$.
  
ii.  Tentukan $P(x = 5, y = 8)$ dan $P(x = 5|y = 8)$. Verifikasi bahwa $P(x,y) = P(x|y) P(y)$ untuk $x = 5$ dan $y = 8$.
  
:::

:::{dropdown} Jawaban

  (i) Perhitungan probabilitas marginal $P(x)$ dan $P(y)$. Total pasangan data $N = 12$.
  Frekuensi kemunculan nilai $x$:
  $n(x=3) = 4$; $n(x=4) = 3$; $n(x=5) = 2$; $n(x=8) = 3$.
  Probabilitas $P(x)$:
  
    
- $P(x=3) = 4/12 = 1/3$
    
- $P(x=4) = 3/12 = 1/4$
    
- $P(x=5) = 2/12 = 1/6$
    
- $P(x=8) = 3/12 = 1/4$
  
  Frekuensi kemunculan nilai $y$:
  $n(y=4) = 4$, $n(y=5) = 4$, $n(y=8) = 4$.
  Probabilitas $P(y)$:
  
    
- $P(y=4) = 4/12 = 1/3$
    
- $P(y=5) = 4/12 = 1/3$
    
- $P(y=8) = 4/12 = 1/3$
  

  (ii) Untuk $P(x=5, y=8)$, kita hitung frekuensi pasangan $(5,8)$ dalam set data. Pasangan $(5,8)$ muncul $2$ kali.
  \begin{equation*}
    P(x=5, y=8) = \frac{2}{12} = \frac{1}{6}.
  \end{equation*}
  Untuk $P(x=5 | y=8)$, ruang sampel dibatasi pada $y=8$. Pasangan data dengan $y=8$ adalah: $(5,8)$, $(5,8)$, $(3,8)$, dan $(4,8)$. Terdapat $4$ data. Nilai $x=5$ muncul sebanyak $2$ kali di dalamnya.
  \begin{equation*}
    P(x=5 | y=8) = \frac{2}{4} = \frac{1}{2}.
  \end{equation*}
  Verifikasi bahwa berlaku hubungan probabilitas $P(x,y) = P(x|y) P(y)$ (formula Bayes) untuk $x=5$ dan $y=8$:
  \begin{equation*}
    P(x=5 | y=8) P(y=8) = \left(\frac{1}{2}\right) \left(\frac{1}{3}\right) = \frac{1}{6}.
  \end{equation*}
  Karena nilainya sama persis dengan $P(x=5, y=8) = 1/6$, formula Bayes dapat terverifikasi.
:::


:::{admonition} Soal
:class: exercise

  Carilah konstanta $c$ yang menormalisasi kerapatan probabilitas berikut ini:
  \[
  p(x) =
    \begin{cases}
      c e^{-\alpha x} & x \geq 0
      0             & x < 0
    \end{cases}
 \]
 dengan $\alpha$ suatu konstanta real positif.
:::

:::{dropdown} Jawaban

  (ii) Untuk distribusi $p(x) = c e^{-\alpha x}$ pada $x \geq 0$, syarat normalisasinya adalah
  \begin{equation*}
    \int_{0}^{\infty} c e^{-\alpha x} dx = 1 \implies c \left[ -\frac{1}{\alpha} e^{-\alpha x} \right]_0^\infty = \frac{c}{\alpha} = 1 \implies c = \alpha.
  \end{equation*}
  Rerata $\langle x \rangle$:
  \begin{equation*}
    \langle x \rangle = \int_{0}^{\infty} x (\alpha e^{-\alpha x}) dx = \alpha \left( \frac{1}{\alpha^2} \right) = \frac{1}{\alpha}.
  \end{equation*}
  Momen kedua $\langle x^2 \rangle$:
  \begin{equation*}
    \langle x^2 \rangle = \int_{0}^{\infty} x^2 (\alpha e^{-\alpha x}) dx = \alpha \left( \frac{2}{\alpha^3} \right) = \frac{2}{\alpha^2}.
  \end{equation*}
  Simpangan baku $\Delta x$:
  \begin{equation*}
    \Delta x = \sqrt{\langle x^2 \rangle - \langle x \rangle^2} = \sqrt{\frac{2}{\alpha^2} - \left(\frac{1}{\alpha}\right)^2} = \sqrt{\frac{1}{\alpha^2}} = \frac{1}{\alpha}.
  \end{equation*}
:::


:::{admonition} Soal
:class: exercise

  Hitung $\langle x \rangle$ dan $\Delta x$ untuk kerapatan probabilitas ternormalisasi:
  ```{math}

p(x) = \frac{1}{\beta \sqrt{\pi}} e^{-(x-\alpha)^2 / \beta^2}
```
  dengan $\alpha$ dan $\beta$ sama-sama konstanta real positif.
:::

:::{dropdown} Jawaban

  Distribusi probabilitas ini berbentuk distribusi Gaussian dengan domain $x~\in~(-\infty, \infty)$.
  Rerata, $\langle x \rangle$, dapat dihitung dengan:
  \begin{equation*}
    \langle x \rangle = \int_{-\infty}^{\infty} x \frac{1}{\beta \sqrt{\pi}} e^{-(x-\alpha)^2 / \beta^2} dx.
  \end{equation*}
  Substitusi $u = x - \alpha \implies dx = du$ dan $x = u + \alpha$:
  \begin{equation*}
    \langle x \rangle = \frac{1}{\beta \sqrt{\pi}} \int_{-\infty}^{\infty} (u + \alpha) e^{-u^2 / \beta^2} du.
  \end{equation*}
  Karena $u e^{-u^2 / \beta^2}$ merupakan fungsi ganjil, integralnya bernilai nol. Dengan demikian,
  \begin{equation*}
    \langle x \rangle = \alpha \frac{1}{\beta \sqrt{\pi}} \int_{-\infty}^{\infty} e^{-u^2 / \beta^2} du = \alpha (1) = \alpha.
  \end{equation*}
  
  Momen kedua $\langle x^2 \rangle$:
  \begin{equation*}
    \langle x^2 \rangle = \int_{-\infty}^{\infty} (u + \alpha)^2 \frac{1}{\beta \sqrt{\pi}} e^{-u^2 / \beta^2} du.
  \end{equation*}
  Uraikan $(u+\alpha)^2 = u^2 + 2\alpha u + \alpha^2$. Integral dari suku $2\alpha u$ adalah nol (fungsi ganjil).
  \begin{equation*}
    \langle x^2 \rangle = \frac{1}{\beta \sqrt{\pi}} \int_{-\infty}^{\infty} u^2 e^{-u^2 / \beta^2} du + \alpha^2 \int_{-\infty}^{\infty} p(x) dx.
  \end{equation*}
  Gunakan identitas integral (bisa cek tabel integral di banyak referensi metode matematika), $\displaystyle \int_{-\infty}^{\infty} u^2 e^{-u^2 / \beta^2} du = \frac{\sqrt{\pi}}{2} \beta^3$, sehingga:
  \begin{equation*}
    \langle x^2 \rangle = \frac{1}{\beta \sqrt{\pi}} \left( \frac{\sqrt{\pi}}{2} \beta^3 \right) + \alpha^2 (1) = \frac{\beta^2}{2} + \alpha^2.
  \end{equation*}
  
  Simpangan baku, $\Delta x$, pada akhirnya adalah:
  \begin{equation*}
    \Delta x = \sqrt{\langle x^2 \rangle - \langle x \rangle^2} = \sqrt{\left(\frac{\beta^2}{2} + \alpha^2\right) - \alpha^2} = \sqrt{\frac{\beta^2}{2}} = \frac{\beta}{\sqrt{2}}.
  \end{equation*}
:::
