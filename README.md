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

Kode ini adalah bagian dari sebuah aplikasi Android yang terdiri dari dua aktivitas (MainActivityOne dan MainActivitySecond) dan digunakan untuk berinteraksi antaraktivitas.



Kode ini menciptakan pengalaman pengguna di mana pengguna dapat memasukkan pesan di MainActivityOne, mengirimkannya ke MainActivitySecond melalui tombol, dan menampilkan balasan di MainActivityOne setelah aktivitas kedua selesai.

## <h1 align="center">Menu<h1>

Menu ini adalah bagian dari sebuah aplikasi Android yang mengimplementasikan aktivitas menu dengan menggunakan CardView untuk setiap opsi menu. Kita dapat memilih aplikasi-aplikasi yang kita buat, dengan menggunakan metode intent. Berikut adalah penjelasannya:

    Deklarasi Variabel: tombolSatu, tombolDua, ..., tombolDelapan: Variabel yang merepresentasikan CardView untuk setiap opsi menu.

Pengaturan Tombol:

Setiap tombol (tombolSatu hingga tombolDelapan) memiliki OnClickListener yang memulai aktivitas tertentu ketika tombol tersebut diklik. Aktivitas yang dimulai bervariasi dari MainActivity hingga ViewPagerActivity, dan bahkan membuka aplikasi Google Maps untuk menavigasi ke "Universitas Pelita Bangsa" pada tombol tujuh. Kode ini memberikan pengguna akses ke berbagai fitur dan aktivitas dalam aplikasi melalui menu dengan menggunakan CardView sebagai elemen UI yang responsif terhadap sentuhan.

## <h1 align="center">Map<h1>

Tulis kode berikut di dalam MainActivity

    findViewById(R.id.cdMenu6).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Example location: Jakarta, Indonesia
                Uri geoLocation = Uri.parse("geo:-6.2088,106.8456");
                openMaps(geoLocation);
            }
Maka ketika di buka, langsung mengarah ke google map

## <h1 align="center">Splash<h1>

Implementasi dari sebuah Splash Screen pada aplikasi, berguna sebagai intro aplikasi. Berikut adalah deskripsi singkat bagian-vbagian kode:

    public class SplashScreen extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        new Handler().postDelayed(new Runnable() {
            @Override
            public void run() {
                startActivity(new Intent(SplashScreen.this, MainActivity.class));
                finish();
            }
        }, 2500);
    }
    }



## <h1 align="center">Fragment<h1>

ViewPagerAdapter ViewPagerAdapter adalah sebuah kelas yang mengimplementasikan FragmentPagerAdapter pada aplikasi Android. Fungsi utamanya adalah mengelola dan menyediakan tampilan fragmen untuk ditampilkan dalam suatu ViewPager.

ViewPagerActivity ViewPagerActivity mengelola daftar fragmen yang akan ditampilkan dalam ViewPager. Ini bisa termasuk membuat instance fragmen, menambahkan fragmen ke dalam ViewPagerAdapter, dan mengatur judul/judul halaman untuk setiap fragmen.

        @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_movie);

        Objects.requireNonNull(getSupportActionBar()).setBackgroundDrawable(new ColorDrawable(getColor(R.color.white)));

        tabLayout = findViewById(R.id.tab);
        viewPager2 = findViewById(R.id.view);
        adapter = new ViewAdapter(this);
        viewPager2.setAdapter(adapter);

        tabLayout.addOnTabSelectedListener(new TabLayout.OnTabSelectedListener() {
            @Override
            public void onTabSelected(TabLayout.Tab tab) {
                viewPager2.setCurrentItem(tab.getPosition());
            }

            @Override
            public void onTabUnselected(TabLayout.Tab tab) {

            }

            @Override
            public void onTabReselected(TabLayout.Tab tab) {

            }
        });

        class Halaman extends FragmentStatePagerAdapter {
            Context context;
            int jumlah_tab;

            Halaman(Context context, FragmentManager fm, int jml_tab)
            {
                super(fm);
                this.context=context;
                this.jumlah_tab=jml_tab;
            }

            @NonNull
            @Override
            public Fragment getItem(int posisition){
                switch (posisition){
                    case 0:return new ActionFragment();
                    case 1:return new HororFragment();
                    case 2:return new RomanceFragment();
                }
                return null;
            }

            @Override
            public int getCount(){
                return jumlah_tab;
            }
        }

        viewPager2.registerOnPageChangeCallback(new ViewPager2.OnPageChangeCallback() {
            @Override
            public void onPageSelected(int position) {
                super.onPageSelected(position);
                tabLayout.getTabAt(position).select();
            }
        });

    }
    }

## <h1 align="center">Sinopsis_Trailer<h1>

    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_vidio_player);

        // Get the video URI from the intent
        String videoPath = getIntent().getStringExtra("VIDEO_PATH");
        Uri uri = Uri.parse(videoPath);

        // Set up VideoView
        videoView = findViewById(R.id.videoView); // Inisialisasi variabel videoView
        videoView.setVideoURI(uri);

        // Set up MediaController
        MediaController mediaController = new MediaController(this);
        mediaController.setAnchorView(videoView);
        videoView.setMediaController(mediaController);

        // Start playing the video
        videoView.start();

        // Get the original orientation
        originalOrientation = getResources().getConfiguration().orientation;

        // Adjust video layout based on the original orientation
        adjustVideoLayout(originalOrientation);
    }

    @Override
    protected void onResume() {
        super.onResume();
        // Detect orientation changes and adjust VideoView layout
        int currentOrientation = getResources().getConfiguration().orientation;
        if (currentOrientation != originalOrientation) {
            adjustVideoLayout(currentOrientation);
            originalOrientation = currentOrientation;
        }
    }

    private void adjustVideoLayout(int orientation) {
        if (orientation == ActivityInfo.SCREEN_ORIENTATION_LANDSCAPE ||
                orientation == ActivityInfo.SCREEN_ORIENTATION_REVERSE_LANDSCAPE) {
            // Landscape mode
            setFullscreen(true);
        } else {
            // Portrait or other orientations
            setFullscreen(false);
        }
    }

    private void setFullscreen(boolean fullscreen) {
        if (fullscreen) {
            // Hide action bar
            if (getSupportActionBar() != null) {
                getSupportActionBar().hide();
            }

            // Set VideoView layout parameters for fullscreen
            RelativeLayout.LayoutParams params = new RelativeLayout.LayoutParams(
                    ViewGroup.LayoutParams.MATCH_PARENT,
                    ViewGroup.LayoutParams.MATCH_PARENT
            );
            params.addRule(RelativeLayout.CENTER_IN_PARENT);
            videoView.setLayoutParams(params);

            // Hide navigation bar and status bar
            getWindow().getDecorView().setSystemUiVisibility(
                    View.SYSTEM_UI_FLAG_FULLSCREEN |
                            View.SYSTEM_UI_FLAG_HIDE_NAVIGATION |
                            View.SYSTEM_UI_FLAG_IMMERSIVE_STICKY);
        } else {
            // Show action bar
            if (getSupportActionBar() != null) {
                getSupportActionBar().show();
            }

            // Set VideoView layout parameters for normal mode
            RelativeLayout.LayoutParams params = new RelativeLayout.LayoutParams(
                    ViewGroup.LayoutParams.MATCH_PARENT,
                    ViewGroup.LayoutParams.WRAP_CONTENT
            );
            params.addRule(RelativeLayout.CENTER_IN_PARENT);
            videoView.setLayoutParams(params);

            // Show navigation bar and status bar
            getWindow().getDecorView().setSystemUiVisibility(
                    View.SYSTEM_UI_FLAG_VISIBLE);
        }
    }

    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        getMenuInflater().inflate(R.menu.menu_vidio_player, menu);
        return true;
    }

    @Override
    public boolean onOptionsItemSelected(@NonNull MenuItem item) {
        if (item.getItemId() == R.id.action_back) {
            // Tambahkan logika untuk kembali ke halaman sebelumnya atau finish activity
            finish();
            return true;
        }
        return super.onOptionsItemSelected(item);


## <h1 align="center">THANK YOU<h1>
