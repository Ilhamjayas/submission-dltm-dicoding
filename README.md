# Prediksi Harga Bitcoin dengan LSTM

Proyek Dicoding oleh Ilham Jaya Saputra. Notebook ini memakai 72 observasi historis untuk memprediksi harga penutupan Bitcoin (`Close`) pada 24 langkah berikutnya. Dua model dibandingkan: LSTM baseline dengan attention dan LSTM encoder-decoder Seq2Seq autoregresif.

## Alur eksperimen

Data dibagi sesuai urutan waktu: 70% untuk pelatihan, 15% untuk validasi, dan 15% untuk pengujian. Fitur mencakup rerata dan simpangan baku bergulir dari harga penutupan. `StandardScaler` dipasang pada data latih saja, lalu dipakai untuk mentransformasi data validasi dan uji.

## Hasil pada set uji

| Model | MAE (skala standar) | RMSE (skala standar) |
| --- | ---: | ---: |
| LSTM baseline | 0.022679 | 0.031963 |
| Checkpoint terbaik Seq2Seq autoregresif | 0.229510 | 1.004207 |

LSTM baseline menghasilkan galat lebih kecil daripada Seq2Seq pada percobaan ini. Kedua model belum mencapai target MAE di bawah 0.015 yang tercatat di notebook. Metrik di atas dihitung setelah standardisasi, jadi angkanya tidak menunjukkan besar selisih harga dalam dolar.

## Mulai dari sini

Pasang dependensi dari [`requirements.txt`](requirements.txt), lalu buka [notebook eksperimen](Ilham_Jaya_Saputra_Submission_Akhir_DLTM.ipynb) di Jupyter atau Colab. Notebook memuat sumber data dan urutan pengerjaan. Model tersimpan tersedia sebagai [baseline](model_baseline_LSTM.keras), [Seq2Seq](model_seq2seq_LSTM.keras), dan [checkpoint terbaik Seq2Seq](best_model_seq2seq_LSTM.keras).

[Proyek Bitcoin di portofolio Ilham Jaya Saputra](https://www.ilhamjayas.my.id/#pc-iflows)
