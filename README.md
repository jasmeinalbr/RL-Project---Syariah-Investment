
# 📈 DRQN untuk Prediksi Investasi Saham Syariah Indonesia

Proyek ini mengeksplorasi penerapan algoritma Deep Reinforcement Learning, khususnya **Deep Recurrent Q-Network (DRQN)**, untuk membangun agen trading saham pada indeks **IDX Shariah (JKISSI)**. Model dilatih untuk membuat keputusan beli, jual, atau tahan berdasarkan data historis harga harian menggunakan pendekatan pembelajaran penguatan (reinforcement learning).

---

## 📂 Struktur Proyek

```bash
RL-Project---Syariah-Investment/
├── idx_shariah_daily.csv           # Dataset harian IDX Shariah (2020 - 2025)
├── RL_DRQN_syariah_investment.ipynb # Notebook utama: preprocessing, model, training & evaluasi
```

---

## 🔍 Deskripsi Dataset

- **Sumber**: [Investing.com - IDX Shariah Historical Data](https://in.investing.com/indices/idx-shariah-historical-data)
- **Periode**: Januari 2020 – Mei 2025
- **Fitur**: Open, High, Low, Close, Volume, Change (%)

---

## ⚙️ Metodologi

- **Model**: Deep Recurrent Q-Network (DRQN) dengan LSTM
- **Input**: 5 hari terakhir (sliding window) dari 6 fitur harga
- **Aksi**: Buy (0), Sell (1), Hold (2)
- **Reward Function**: Dirancang untuk menghukum aksi pasif dan memberi bonus saat aksi menghasilkan profit
- **Framework**: TensorFlow, NumPy, Pandas, Matplotlib

---

## 📊 Hasil Utama

- **Training**:
  - Cumulative Profit: Rp14.056,43
  - Reward: -37.915,73
  - Epsilon akhir: 0.0100

- **Testing**:
  - Profit: 0.00%
  - Reward: -114.00
  - Aksi Dominan: Hold (380 dari 380 langkah)

---

## ❗ Insight

Meskipun model DRQN menunjukkan kemampuan menghasilkan profit selama pelatihan, performanya menurun drastis saat diuji. Agen cenderung memilih aksi "Hold" secara eksklusif. Hal ini mengindikasikan kemungkinan **overfitting**, reward function yang belum optimal, atau **ketidaksesuaian pola data** antara train dan test set.

---

## 📌 Catatan Pengembangan Selanjutnya

- Eksperimen dengan window size yang lebih besar (misalnya 10 atau 20 hari)
- Tuning reward function agar lebih agresif terhadap aksi beli/jual
- Menambahkan indikator teknikal (RSI, MACD, dll.)
- Mengganti model dengan PPO, A2C, atau Transformer-based RL

