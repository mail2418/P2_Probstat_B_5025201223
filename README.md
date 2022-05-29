# P2_Probstat_A_5025201223

Praktikum Probabilitas dan Statistik 2022 Modul 2 (Distribusi Probabilitas)

## Generated By:
| Nama          | NRP                                                      |  Kelas                                                     | 
| ------------- | -------------------------------------------------------- | --------------------------------------------------------   |
| Muhammad Ismail | 5025201223 | Probabilitas dan Statistik B |

## Dosen: Dr. Ahmad Saikhu, S.Si., MT.

<br />

## Soal 1
> Seorang peneliti melakukan penelitian mengenai pengaruh aktivitas 𝐴 terhadap kadar saturasi oksigen pada manusia. Peneliti tersebut mengambil sampel sebanyak 9 responden. Pertama, sebelum melakukan aktivitas 𝐴, peneliti mencatat kadar saturasi oksigen dari 9 responden tersebut. Kemudian, 9 responden tersebut diminta melakukan aktivitas 𝐴. Setelah 15 menit, peneliti tersebut mencatat kembali kadar saturasi oksigen dari 9 responden tersebut. Berikut data dari 9 responden mengenai kadar saturasi oksigen sebelum dan sesudah melakukan aktivitas 𝐴

![soal 1](https://user-images.githubusercontent.com/70510279/170801862-fb8feada-e470-4bdd-90c8-2b1b050563ca.jpg)

Berdasarkan data pada tabel diatas, diketahui kadar saturasi oksigen dari responden ke-3 ketika belum melakukan aktivitas 𝐴 sebanyak 67, dan setelah melakukan aktivitas 𝐴 sebanyak 70.

  - A. Carilah Standar Deviasi dari data selisih pasangan pengamatan tabel diatas

    Langkah pertama penyelesaian adalah memasukkan semua data yang ada pada tabel pada sebuah variabel sebagai berikut

        ```
         # Poin 1a
          before <- c(78, 75, 67, 77, 70, 72, 28, 74, 77)
          after <- c(100, 95, 70, 90, 90, 90, 89, 90, 100)

        ```  

    Setelah dimasukkan semua datanya, maka dilakukan cek data menggunakan `data.frame` yaitu

        ```
          my_data <- data.frame(
              group = rep(c("before", "after"), each = 9),
              saturation = c(before, after)
          )
        ```

    Setelah itu dilihat hasil framenya sebagai berikut:

        ```R
          print(my_data)
        ```

    <img width="435" alt="image" src="https://user-images.githubusercontent.com/86004023/170858094-792f1a04-8114-4add-80cf-c51cdc4fcd86.png">

    Selanjutnya mencari standar deviasinya. Standar deviasi sebelum dan sesudah aktivitas adalah
    
      ```
          # Standar Devisiasi before activity
          SD_before <- sd(before)
          SD_before
          
           # Standar Devisiasi after activity
           SD_after <-sd(after)
           SD_after
       ```         
     Maka hasilnya : 

     <img width="347" alt="image" src="https://user-images.githubusercontent.com/86004023/170858149-b2e4b403-f4a1-4515-97bd-e990edcbd699.png">

</br>

   - B. carilah nilai t (p-value)
      Untuk mencari nilai t (p-value) dapat menggunakan fungsi `t.test` yaitu sebagai berikut
        ```
         # Menggunakan t-test
         t.test(before, after, alternative = "greater", var.equal = FALSE)
       ```    
       Sehingga Hasilnya sebagai berikut:
       
      <img width="616" alt="image" src="https://user-images.githubusercontent.com/86004023/170858480-4e5c7d24-b5be-4ad1-8c0f-554450bbb4ca.png">
  
  </br>

   - C. Tentukanlah Apakah Terdapat Pengaruh yang Signifikan Secara Statistika dalam Hal Kadar Saturasi Oksigen, Sebelum dan Sesudah Melakukan Aktivitas 𝐴  jika Diketahui Tingkat Signifikansi 𝛼 = 5% serta H0 : “tidak ada pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen , sebelum dan sesudah melakukan aktivitas 𝐴”
       Langkah pertama yaitu melihat hasil komparasi dua variabel berikut
        ```
         var.test(before, after)
       ```    
       Sehingga Hasilnya sebagai berikut:
       
       <img width="593" alt="image" src="https://user-images.githubusercontent.com/86004023/170858996-31f369f7-66ad-4279-9b12-2562a1f0e027.png">
       
       Selanjutnya, untuk melihat pengaruh jika tingkat signifikasi 5% dan tidak ada pengaruh yang signifikan secara statistika, maka adalah sebagai berikut
       ```
         t.test(before, after, mu = 0, alternative = "two.sided", var.equal = TRUE)
       ```  
      Sehingga Hasilnya sebagai berikut:

      <img width="692" alt="image" src="https://user-images.githubusercontent.com/86004023/170859040-a1c6aaaa-0fe0-4834-8778-eedcf4530034.png">

</br>

## Soal 2
> Diketahui bahwa mobil dikemudikan rata-rata lebih dari 20.000 kilometer per tahun. Untuk menguji klaim ini, 100 pemilik mobil yang dipilih secara acak diminta untuk mencatat jarak yang mereka tempuh. Jika sampel acak menunjukkan rata-rata 23.500 kilometer dan standar deviasi 3900 kilometer. (Kerjakan menggunakan 2 library seperti referensi pada modul).

  - A. Apakah Anda setuju dengan klaim tersebut?

    Setuju, karena
    
    <img width="223" alt="image" src="https://user-images.githubusercontent.com/86004023/170864898-71408114-19ec-4d85-92af-c91e08e90283.png">
    
    </br>

  - B. Jelaskan maksud dari output yang dihasilkan!
       Diketahui n = 100, Rata-Rata (X̄) = 23500, dan standar deviasi(σ) = 3900 Maka null hipotesis adalah
       Maka null hipotesis adalah 
          ```
          H0 : μ = 20000
          ```
          Alternatif hipotesisnya yaitu
          ```
          H1 : μ > 20000
          ```

       <img width="472" alt="image" src="https://user-images.githubusercontent.com/86004023/170864744-4f24236a-662f-4b7c-a92e-c253bd78cb65.png">
       
       </br>

  - C. Buatlah kesimpulan berdasarkan P-Value yang dihasilkan!
  
       Untuk mencari nilai z nya yaitu 
       </br>
       ![image-removebg-preview](https://user-images.githubusercontent.com/70510279/170823253-92e9ca27-09f7-4d40-a51c-9fd4392bb742.png)

       Lalu mencari nilai p-value nya sebagai berikut
               
       ![image-removebg-preview (2)](https://user-images.githubusercontent.com/70510279/170823338-3d86d1f2-14dc-458c-af6a-eb06f0fd8333.png)

       Sehingga kesimpulan yang didapat adalah bahwa mobil dikemudikan rata-rata lebih dari 20.000 kilometer per tahun

       </br>
  
## Soal 3
> Diketahui perusahaan memiliki seorang data analyst ingin memecahkan permasalahan pengambilan keputusan dalam perusahaan tersebut. Selanjutnya didapatkanlah data berikut dari perusahaan saham tersebut.

 ![image](https://user-images.githubusercontent.com/70510279/170834251-73d308da-69c9-4e86-b2b8-4917e598efae.png)
 
   Dari data diatas berilah keputusan serta kesimpulan yang didapatkan dari hasil diatas. Asumsikan nilai variancenya sama, apakah ada perbedaan pada rata-ratanya (α= 0.05)? Buatlah :
   
    A. H0 dan H1
  
    B. Hitung Sampel Statistik
  
    C. Lakukan Uji Statistik (df = 2) 
  
    D. Nilai Kritikal
  
    E. Keputusan
  
    F. Kesimpulan

  </br>
  
  - A. H0 dan H1
    dilakukan perhitungan H0 sebagai berikut
    </br>
    ![image](https://user-images.githubusercontent.com/70510279/170837176-254c2846-c1b7-47c0-aa9f-c3b2e5db149a.png)
    </br>
    
    dilakukan perhitungan H1 sebagai berikut
    </br>
    ![image](https://user-images.githubusercontent.com/70510279/170837297-542b8a9e-309b-41be-92c5-880e284beef4.png)
    
    </br>

  - B. Hitung Sampel Statistik
      Untuk menghitung sampel statistik dapat menggunakan fungsi `tsum.test` yaitu sebagai berikut

        ```
        tsum.test(mean.x=3.64, s.x = 1.67, n.x = 19, mean.y =2.79 , s.y = 1.32, n.y = 27, alternative = "greater", var.equal = TRUE)
        ```
  
      <img width="604" alt="image" src="https://user-images.githubusercontent.com/86004023/170865478-78c8a8b0-6542-4473-ac95-97d6a5b29471.png">
      
      </br>

  - C. Lakukan Uji Statistik (df = 2) 
      Menggunakan bantuan library `mosaic`
      
      <img width="396" alt="image" src="https://user-images.githubusercontent.com/86004023/170865651-d9e6448e-6e54-4820-89a4-b188babe3fc8.png">
      
      Sehingga Hasilnya sebagai berikut:
     <img width="1118" alt="image" src="https://user-images.githubusercontent.com/86004023/170865622-20a96143-5e9d-480e-9803-896a4d94e7aa.png">

      </br>
  
  - D. Nilai Kritikal 
       Untuk menghitung sampel statistik dapat menggunakan fungsi `qchisq` dengan `df=2` yaitu sebagai berikut

       Sehingga Hasilnya sebagai berikut:

       <img width="401" alt="image" src="https://user-images.githubusercontent.com/86004023/170865886-1926e058-fe48-48d9-971e-dc2a9788c6b7.png">

       </br>
       
  - E. Keputusan
       Untuk mendapatkan keputusan diperlukan bantuan dengan Teori Keputusan

       Teori keputusan adalah teori formal pengambilan keputusan di bawah ketidakpastian. 
       Aksinya adalah : `({a}_{a∈A})`
       Kemungkinan konsekuensi : `({c}_{c∈C})` (tergantung pada keadaan dan tindakan)
       Maka keputusan dapat dibuat dengan `t.test`

       </br>
       
  - F. Kesimpulan
       Kesimpulan yang didapatkan yaitu perbedaan rata-rata yang terjadi tidak ada jika dilihat dari uji statistik dan akan ada tetapi tidak signifikan jika dipengaruhi nilai kritikal.


       </br>

## Soal 4
> Seorang Peneliti sedang meneliti spesies dari kucing di ITS . Dalam penelitiannya ia mengumpulkan data tiga spesies kucing yaitu kucing oren, kucing hitam dan kucing putih dengan panjangnya masing-masing.

   Jika : diketahui dataset https://intip.in/datasetprobstat1
   H0 : Tidak ada perbedaan panjang antara ketiga spesies atau rata-rata panjangnya sama

   Maka Kerjakan atau Carilah: 
    A. Buatlah masing masing jenis spesies menjadi 3 subjek "Grup" (grup 1, grup 2, grup 3). Lalu Gambarkan plot kuantil normal untuk setiap kelompok dan lihat apakah ada outlier utama dalam homogenitas varians.
    B. Carilah atau periksalah Homogeneity of variances nya , Berapa nilai p yang didapatkan? Apa hipotesis dan kesimpulan yang dapat diambil?
    C. Untuk uji ANOVA (satu arah), buatlah model linier dengan Panjang versus Grup dan beri nama model tersebut model 1.
    D. Dari Hasil Poin C, Berapakah nilai-p ? , Apa yang dapat Anda simpulkan dari H0?
    E. Verifikasilah jawaban model 1 dengan Post-hoc test Tukey HSD, dari nilai p yang didapatkan apakah satu jenis kucing lebih panjang dari yang lain? Jelaskan.
    F. Visualisasikan data dengan ggplot2
    
   </br>

   - A. Buatlah masing masing jenis spesies menjadi 3 subjek "Grup" (grup 1, grup 2, grup 3). Lalu Gambarkan plot kuantil normal untuk setiap kelompok dan lihat apakah ada outlier utama dalam homogenitas varians.
   
     Langkah pertama mengambil data dari link yang telah disediadakan

      ```
        myFile  <- read.table(url("https://rstatisticsandresearch.weebly.com/uploads/1/0/2/6/1026585/onewayanova.txt")) 
        dim(myFile)
        head(myFile)
      ```
      <img width="167" alt="image" src="https://user-images.githubusercontent.com/86004023/170866715-540535c8-7d2f-44f9-8a7e-79182e6e02c5.png">

      Selanjutnya membuat myFile menjadi group 
      
      ```
        myFile$Group <- as.factor(myFile$Group)
        myFile$Group = factor(myFile$Group,labels = c("Kucing Oren","Kucing Hitam","Kucing Putih"))
      ```

      Setelah itu, dicek apakah dia menyimpan nilai di groupnya
      
      ```
        class(myFile$Group)
      ```

      Lalu bagi tiap valuer menjadi 3 bagian ke 3 grup
      
      ```
        group1 <- subset(myFile, Group=="Kucing Oren")
        group2 <- subset(myFile, Group=="Kucing Hitam")
        group3 <- subset(myFile, Group=="Kucing Putih")
      ```
      
      </br>

   - B. Carilah atau periksalah Homogeneity of variances nya , Berapa nilai p yang didapatkan? Apa hipotesis dan kesimpulan yang dapat diambil?

        Mencari Homogeneity of variances bisa menggunakan command sebagai berikut
        
        ```
        bartlett.test(Length~Group, data=dataoneway)
        ```
        
        Didapatkan nilai dari p-value yaitu = 0.8054. 
        Kesimpulan yang didapatkan yaitu Bartlett's K-squared memiliki nilai sebesar 0.43292 dan df bernilai 2
      
   - C. Untuk uji ANOVA (satu arah), buatlah model linier dengan Panjang versus Grup dan beri nama model tersebut model 1.
        Mencari Homogeneity of variances bisa menggunakan command sebagai berikut
        
        ```
        qqnorm(group1$Length)
        qqline(group1$Length)
        ```

        ![image](https://user-images.githubusercontent.com/70510279/170848819-3b70668f-ba55-4d57-b297-a14cb7d7218a.png)
        
        </br>

   - D. Dari Hasil Poin C, Berapakah nilai-p ? , Apa yang dapat Anda simpulkan dari H0?
        
        Didapatkan nilai dari p-value yaitu = 0.8054. 
        
        </br>
   
   - E. Verifikasilah jawaban model 1 dengan Post-hoc test Tukey HSD, dari nilai p yang didapatkan apakah satu jenis kucing lebih panjang dari yang lain? Jelaskan.

        ```
        model1 <- lm(Length~Group, data=myFile)
        ```
        
        Selanjutnya menggunakan command 
        
        ```
        anova(model1)
        ```
        
        Lalu menggunakan model Post-hoc Tukey HSD sebagai berikut
        
        ```
        TukeyHSD(aov(model1))
        ```
        </br>

   - F. Visualisasikan data dengan ggplot2
  
        ```
        library(ggplot2)
        ggplot(dataoneway, aes(x = Group, y = Length)) + geom_boxplot(fill = "grey80", colour = "black") + scale_x_discrete() + xlab("Treatment Group") +  ylab("Length (cm)")
        ```
        
        </br>

## Soal 5
> Data yang digunakan merupakan hasil eksperimen yang dilakukan untuk mengetahui pengaruh suhu operasi (100 ̊C, 125 ̊C dan 150 ̊C) dan tiga jenis kaca pelat muka (A, B dan C) pada keluaran cahaya tabung osiloskop. Percobaan dilakukan sebanyak 27 kali dan didapat data sebagai berikut: 

  Data Hasil Eksperimen. 
  
   <img width="332" alt="image" src="https://user-images.githubusercontent.com/86004023/170867530-b11cf2dc-f084-403b-9028-f38097bb1d40.png">

   Dengan data tersebut:
   
     A. Buatlah plot sederhana untuk visualisasi data
     
     B. Lakukan uji ANOVA dua arah
     
     C. Tampilkan tabel dengan mean dan standar deviasi keluaran cahaya untuk setiap perlakuan (kombinasi kaca pelat muka dan suhu operasi)
     
     D. Lakukan uji Tukey
     
     E. Gunakan compact letter display untuk menunjukkan perbedaan signifikan antara uji Anova dan uji Tukey
     
   Berikut adalah contoh daftar package dan fungsi yang dapat digunakan (dapat pula menggunakan contoh lainnya)
   
     - Packages: readr, ggplot2, multcompView, dplyr
     - Function: aov, TukeyHSD, qplot, group_by, summarise, multcompLetters4

   - A. Buatlah plot sederhana untuk visualisasi data
   
        Run semua library yang diperlukan
        
        ```
        install.packages("multcompView")
        library(readr)
        library(ggplot2)
        library(multcompView)
        library(dplyr)
        ```

        Selanjutnya membaca file GTL.csv dari documents
        
        ```
        GTL <- read_csv("GTL.csv")
        head(GTL)
        ```
        
        ![image](https://user-images.githubusercontent.com/70510279/170851339-6020c531-8d07-4a20-a9ab-4db04a1110e0.png)

        Lakukan observasi pada data
        
        ```
        str(GTL)
        ```
        
        ![image](https://user-images.githubusercontent.com/70510279/170851373-4512e70e-81ed-4a12-bf5e-5408d4403678.png)
        
        </br>

        Selanjutnya lakukan viasualisasi menggunakan simple plot yaitu sebagai berikut
        
        ```
        qplot(x = Temp, y = Light, geom = "point", data = GTL) +
          facet_grid(.~Glass, labeller = label_both)
        ```
        
        ![image](https://user-images.githubusercontent.com/70510279/170851403-3b91fe4f-ab41-4b3e-8aca-066a27607971.png)

        </br>
        
   - B. Lakukan uji ANOVA dua arah
        
        Langkah pertama adalah membuat variabel as factor sebagai ANOVA
        
        ```
        GTL$Glass <- as.factor(GTL$Glass)
        GTL$Temp_Factor <- as.factor(GTL$Temp)
        str(GTL)
        ```
        
        ![image](https://user-images.githubusercontent.com/70510279/170851438-509ae870-a9a1-420e-adb9-3239f6a6dfb6.png)

        </br>

        Selanjutnya melakukan analisis of variance (aov) yaitu sebagai berikut 
        
        ```
        anova <- aov(Light ~ Glass*Temp_Factor, data = GTL)
        summary(anova)
        ```
        
        ![image](https://user-images.githubusercontent.com/70510279/170851507-b318c577-8c71-4a3c-b391-1c406e364abb.png)
        
   - C. Tampilkan tabel dengan mean dan standar deviasi keluaran cahaya untuk setiap perlakuan (kombinasi kaca pelat muka dan suhu operasi)
        
        Menggunakan `group_by` lalu melakukan `summarise` sesuai mean dan standar deviasi yang berlaku sehingga scriptnya adalah sebagai berikut
        
          ```
          data_summary <- group_by(GTL, Glass, Temp) %>%
            summarise(mean=mean(Light), sd=sd(Light)) %>%
            arrange(desc(mean))
          print(data_summary)
          ```
        ![image](https://user-images.githubusercontent.com/70510279/170851578-fee77749-6fff-4abf-ad36-62ef2ec84c3d.png)

        </br>
        
     - D. Lakukan uji Tukey
          Menggunakan fungsi `TukeyHSD` sebagai berikut
          
          ```
          tukey <- TukeyHSD(anova)
          print(tukey)
          ```
          
          ![image](https://user-images.githubusercontent.com/70510279/170851658-f097be04-5017-404e-99b6-0ebdebb284d9.png)
          ![image](https://user-images.githubusercontent.com/70510279/170851669-260742aa-75b0-47e2-9d8a-dabf318b5082.png)

     - E. Gunakan compact letter display untuk menunjukkan perbedaan signifikan antara uji Anova dan uji Tukey

          Awalnya yaitu membuat compact letter display sebagai berikut
          
          ```
          tukey.cld <- multcompLetters4(anova, tukey)
          print(tukey.cld)
          ```
          
          ![image](https://user-images.githubusercontent.com/70510279/170851727-729875df-5aaf-4897-b97f-08b91127347e.png)

          </br>
          
          Tambahkan compact letter display tersebut ke tabel dengan means(rata-rata) dan sd

          ```
          cld <- as.data.frame.list(tukey.cld$`Glass:Temp_Factor`)
          data_summary$Tukey <- cld$Letters
          print(data_summary)
          ```
          
          ![image](https://user-images.githubusercontent.com/70510279/170851749-d1e4fd97-1020-4f52-bb1a-7d020a508093.png)

# Referensi :
  - 
