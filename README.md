<h1>UAS PEMOGRAMAN MOBILE</h1>

![p](https://github.com/zidanperdana/AndroidProject/assets/116040175/254d0480-a506-44b9-bcb0-83ba54263167)

    Nama        : Maulana Zidan Perdana
    NIM         : 312210463
    Mata Kuliah : Pemrograman Mobile 1
    Dosen       : Donny Maulana, S.Kom., M.M.S.I.

Daftar Aktivitas yg Dibuat
| [Hello](#Hello) | [Scrolling](#Scrolling(IceCold)) |[Fibonacci](#Fibonacci) | 
| :---| :---------- | :-------|

| [Pesan](#Pesan) | [Menu](#Menu)  | [Map](#Map) |[Splash](#Splash) |
| :---| :------- | :----- | :-------|

| [Fragment](#Fragment) | [Sinopsis & Trailer](#Sinopsis_Trailer)  | 
| :---| :-----------

## <h1 align="center">Hello<h1>

Activity Hello adalah aktivitas pertama yang dibuat, menampilkan teks pada tampilan aktvitas.
      
      <TextView
        android:id="@+id/txthello"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:text="Hello World!!"
        android:textColor="@color/dongker"
        android:textSize="20pt"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.503"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.413"
        tools:ignore="TextSizeCheck" />

## <h1 align="center">Scrolling(IceCold)<h1>

Menampilkan teks berita yang dapat di scroll. Menggunakan metode <b>scrollview</b> yang didalamnya diisi dengan textview berita.

        <ScrollView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/article_heading">
        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical">
            <TextView
                android:id="@+id/article_subheading"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:padding="@dimen/padding_regular"
                android:text="@string/article_subtitle"
                android:textAlignment="center"
                android:textAppearance="@android:style/TextAppearance.DeviceDefault"
                android:textColor="@color/colorPrimary" />
            <TextView
                android:id="@+id/article"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:autoLink="web"
                android:lineSpacingExtra="@dimen/line_spacing"
                android:padding="@dimen/padding_regular"
                android:text="@string/article_text"
                tools:ignore="VisualLintLongText" />
        </LinearLayout>
    </ScrollView>

## <h1 align="center">Fibonacci<h1>

<h2>Metode CountUp</h2>

    public void countUp(View view) {
        if (count == 0) {
            show_count.setText("0");
        }
        else if (count == 1) {
            show_count.setText("1");
        }
        else {
            if (limit != -1 && count > limit) {
                // Jika count melebihi limit, atur ulang perhitungan
                count = 0;
                fibNMinus1 = 1;
                fibNMinus2 = 0;
                show_count.setText(getString(R.string.count_initial_value));

Metode ini terfokus pada perhitungan deret Fibonacci dan pembaruan tampilan pada suatu aplikasi. Pertama, nilai batas diambil dari komponen EditText dengan ID "input_limit". Proses ini melibatkan pengecekan apakah nilai batas tidak kosong. Jika tidak kosong, nilai tersebut dikonversi ke tipe data int. Selanjutnya, dilakukan pengecekan apakah nilai saat ini (mCount) lebih besar atau sama dengan batas yang telah ditetapkan. Jika kondisi ini terpenuhi, metode akan menampilkan pesan Toast dan menghentikan eksekusi lebih lanjut.

Jika batas tidak tercapai, metode akan melanjutkan dengan melakukan perhitungan deret Fibonacci dan mengupdate tampilan aplikasi sesuai dengan nilai yang dihitung. Selain itu, metode ini juga mengatur warna teks pada tampilan menggunakan metode setColor(). Dengan pendekatan ini, aplikasi dapat memberikan respons yang sesuai terhadap input pengguna dan memastikan bahwa perhitungan deret Fibonacci dan pembaruan tampilan berjalan dengan tepat.

<h2>Metode Input Warna</h2>

        else {
                long fibCurrent = fibNMinus1 + fibNMinus2;
                fibNMinus2 = fibNMinus1;
                fibNMinus1 = fibCurrent;
                //Mengatur warna teks berdasarkan angka Fibonacci
                int colorResId = R.color.blue; // Warna Default
                switch (count % 11) {
                    case 1:
                        colorResId = R.color.aqua; // Warna Pink Tua
                        break;
                    case 2:
                        colorResId = R.color.birumuda; // Warna Hijau Muda
                        break;
                    case 3:
                        colorResId = R.color.birulangit; // Warna Ungu
                        break;
                    case 4:
                        colorResId = R.color.dongker; // Warna Salem
                        break;
                    case 5:
                        colorResId = R.color.biru; // Warna Biru
                        break;
                    case 6 :
                        colorResId = R.color.soft; // Warna Kuning
                        break;
                    case 7:
                        colorResId = R.color.pastel; // Warna Hijau
                        break;
                    case 8:
                        colorResId = R.color.mediumblue; // Warna Cream
                        break;
                    case 9:
                        colorResId = R.color.gold; // Warna Gold
                        break;
                    case 10:
                        colorResId = R.color.biru; // Warna Biru
                        break;
                    case 11:
                        colorResId = R.color.white; // Warna Orange
                        break;
                }
                show_count.setTextColor(getResources().getColor(colorResId));
                show_count.setText(String.valueOf(fibCurrent));
            }
        }
        count++;
    }

Metode ini menawarkan fungsionalitas perubahan warna yang sesuai dengan setiap pemanggilannya. Untuk melacak urutan pemanggilan, digunakan variabel currentFib. Ketika currentFib memiliki nilai genap, metode ini mengembalikan warna hitam; sebaliknya, jika nilai currentFib adalah ganjil, warna yang dikembalikan adalah warna putih. Implementasi warna ini memanfaatkan fungsi ContextCompat.getColor() dengan merujuk pada sumber daya warna dari file resource (R.color). Dengan demikian, metode ini memberikan dinamika visual yang menarik, menciptakan variasi warna yang berubah sesuai dengan karakteristik bilangan dalam deret Fibonacci.

## <h1 align="center">Pesan<h1>

