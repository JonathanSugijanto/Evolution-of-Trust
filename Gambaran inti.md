Inti bahasan paper: bagaimana kepercayaan (trust) bisa muncul dan bertahan dalam kelompok agen, kalau tiap orang punya pilihan strategi dan motivasi pribadi. 

Untuk menelitinya, mereka menggunakan N-player trust game, mereka tambahkan sistem insentif baru yang mereka bangun: _**transformation incentive mechanism**_


### **1. Pendahuluan**
Skema: sekumpulan populasi dan dari situ ambil N orang untuk main dalam satu ronde. Ada tiga jenis pemain:

| Simbol | Nama                  | Peran                                                               |
| :----- | :-------------------- | :------------------------------------------------------------------ |
| I      | Investor              | Orang yang “percaya” dan menginvestasikan uangnya                   |
| T      | Trustworthy trustee   | Orang yang menerima investasi dan **mengembalikan sebagian + keuntungan** |
| U      | Untrustworthy trustee | Orang yang menerima investasi tapi **tidak mengembalikan**      |


**Mekanisme:**
1. Investor (I) kasih sejumlah uang 𝑡𝑣 ke semua trustee (T dan U).
2. Trustee yang jujur (T) menggandakan uang itu dengan faktor $$𝑅_{𝑇​}$$ dan mengembalikan ke investor.
3. Trustee yang tidak jujur (U) gandakan uang dengan $$𝑅_{U​}$$​, tapi tidak mengembalikan ke investor.

> Jadi, kalau banyak U di grup, para investor rugi dan berhenti percaya.

### **2. Masalah: Cara agar trust bisa tetap ada?**
Biasanya, orang pakai dua solusi klasik:
- _Reward system_: memberikan hadiah ke pemain jujur.
- _Punishment system_: hukum pemain tidak jujur.

Tapi dua-duanya memiliki kelemahan:
- _Reward_ = membutuhkan biaya, bisa disalahgunakan.
- _Punishment_ = membuat suasana negatif.

### **3. Ide Utama: _Transformation Incentive Mechanism_**
Mereka memperkenalkan parameter $$M$$ (_threshold_) dan $$\alpha$$ (_mixing parameter_) untuk mengatur “mode” insentif:\
- Kalau jumlah _trustee_ jujur ($$NT$$) lebih kecil dari ambang $$M$$ → sistem memberikan _reward_ ke _trustee_ yang jujur.
- Kalau $$NT ≥ M$$ → sistem aktifkan _punishment_ buat _trustee_ yang tidak jujur.

> kalau kejujuran langka → orang jujur dihargai\
> kalau kejujuran banyak → yang bohong dihukum

Semua pemain harus bayar sedikit “biaya insentif” $$\delta$$ di awal.

### **4. Daftar Metode**

| No | Nama Metode                                 | Fungsi dalam Paper                                                                                                |
| :- | :------------------------------------------ | :-------------------------------------------------------------------------------------------------------------- |
| 1  | Evolutionary Game Theory (EGT)         | Kerangka umum untuk menggambarkan bagaimana strategi (I, T, U) berubah dari waktu ke waktu dalam populasi.        |
| 2  | N-player Trust Game                     | Model dasar interaksi antar individu (aturan main + _payoff_ untuk tiap strategi).                                |
| 3  | Transformation Incentive Mechanism      | Mekanisme baru yang diusulkan: sistem insentif adaptif (bisa berubah antara _reward_ dan _punishment_).        |
| 4  | Hypergeometric Distribution             | Untuk menghitung peluang munculnya kombinasi pemain (berapa investor, _trustee_, _untrustworthy_) dalam grup acak.    |
| 5  | Fermi Function (Imitation Probability)  | Rumus probabilitas seorang pemain meniru strategi orang lain berdasarkan perbedaan _payoff_.            |
| 6  | Markov Chain / Transition Matrix        | Untuk merepresentasikan seluruh kemungkinan perubahan komposisi strategi dalam populasi.                     |
| 7  | Stationary Distribution Analysis        | Untuk menemukan kondisi jangka panjang (_steady state_) dari evolusi strategi.                            |
| 8  | Numerical Simulation (Matrix iteration) | Metode numerik untuk menghitung distribusi stasioner dan menggambar hasil (bukan simulasi acak, tapi iterasi deterministik).|
| 9  | Parameter Sensitivity Analysis          | Uji pengaruh δ, M, α, N terhadap hasil evolusi (bagaimana _trust_ naik/turun).                                 |

### **5. Parameter Variasi**
**1. Incentive value — δ**\
Peran: besar kecilnya insentif (biaya/bonus per orang).\
Nilai yang dipakai di paper: contoh eksplisit δ = 0, 0.1, 0.25, 0.3, 0.4; juga sweep kontinu dari 0 → 1 di beberapa grafik.\
Efek diamati: perubahan besar pada frekuensi U / T / I dan pada payoff rata-rata.

**2. Transformation threshold — M**\
Peran: ambang jumlah trustworthy (NT) yang menentukan apakah mekanisme memberi reward atau punishment.\
Nilai yang dipakai: M = 0, M = 3, M = 7; juga kasus M = N/2, M = N+1; dan analisis kondisi M > 3N/4.\
Efek diamati: apakah reward atau punishment lebih efektif pada rentang δ tertentu.

**3.Mixing level of incentives — α**\
Peran: seberapa “pure” reward vs punishment (α = 0 → pure reward; α = 1 → pure punishment; 0<α<1 → mixed).\
Nilai yang dipakai: α = 0, 0.5, 1; dan pembahasan 0<α<1.\
Efek diamati: pure incentives (α=0/1) sering lebih berdampak daripada mixed.

**4. Group size — N**\
Peran: ukuran kelompok interaksi per ronde.\
Nilai yang dipakai: N = 6 (default), juga N ∈ {6,8,10,12,14} dan variasi lain (grafik per-N).\
Efek diamati: kenaikan N umumnya mendorong I & T naik, U turun; sensitivitas tergantung M.

**5. Population size — X**\
Peran: total populasi untuk model finite.\
Nilai yang dipakai: X = 100 (sering dipakai di semua eksperimen).

**6. Return factors — RT dan RU (atau rasio RU/RT)**\
Peran: pengganda hasil trustee jujur (RT) dan tidak jujur (RU), dengan constraint 1 < RT < RU < 2RT.\
Nilai yang dipakai: contoh RT = 4, RU = 6; juga eksplorasi RU/RT pada rentang di atas (grafik variasi RU/RT).\
Efek diamati: memengaruhi keuntungan relatif T vs U → mempengaruhi evolusi strategi.

**7. Intensity of selection — ω**\
Peran: seberapa sensitif imitasi terhadap beda payoff (Fermi).\
Nilai yang dipakai: sweep lebar, contoh titik di grafik: ω ∈ {10⁻⁵, 10⁻³, 10⁻², 10⁻¹, 10⁰, 10¹, 10²}; default sering ω = 10 untuk sebagian eksperimen.\
Efek diamati: pada ω kecil evolusi dominan oleh kebetulan (random drift), pada ω besar payoff menentukan.

**8. Mutation rate — µ**\
Peran: peluang perubahan strategi acak; menghindarkan penyerapan mutlak.\
Nilai yang dipakai: µ ≈ 0.01 default; juga sweep lebar (10⁻⁵ → 1) dalam sensitivitas.\
Efek diamati: µ besar → distribusi mendekati 1/3 tiap strategi; µ kecil → strategi berbasis payoff muncul.

**9. Investment amount — tv**\
Peran: unit investasi yang dikirim investor; biasanya set ke tv = 1 di eksperimen (konvensi).

### **6. Kombinasi & Kasus Khusus yang Diuji**
1. δ kecil vs δ besar: membandingkan efektivitas reward (lebih baik saat δ kecil) vs punishment (lebih baik saat δ besar).
2. Pure reward (α=0) vs pure punishment (α=1) vs mixed (0<α<1).
3. M relatif terhadap N: termasuk kasus M > 3N/4 (paper menunjukkan threshold di atas 3/4N membuat perubahan M kurang berpengaruh).
4. Variasi N sambil pegang δ konstan: lihat bagaimana ukuran grup mengubah dinamika walau insentif tetap.
5. Sensitivitas terhadap RU/RT: menguji robustness hasil terhadap beda keuntungan T vs U.
6. Sensitivitas ω & µ: lihat transisi dari drift-dominated → selection-dominated.
