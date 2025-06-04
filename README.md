# 📱 PhoneMate - Smart Smartphone Recommendation App

PhoneMate AI adalah aplikasi web berbasis AI yang membantu pengguna menemukan smartphone yang tepat sesuai kebutuhan dan budget mereka. Aplikasi ini menggunakan pemrosesan bahasa natural (NLP) untuk memahami permintaan pengguna dalam bahasa sehari-hari dan memberikan rekomendasi yang akurat.

**🌐 Live Demo**: https://phonemate-app-khjv6uqhhi4ij9fvx2jzhj.streamlit.app/?embed_options=light_theme,show_toolbar

## 🚀 Fitur Utama

### 🤖 AI-Powered Natural Language Search
- **Input Natural**: "HP gaming RAM 8GB harga 5 juta"
- **AI Understanding**: Mistral AI menganalisis dan mengekstrak parameter
- **Smart Filtering**: Otomatis menerapkan filter berdasarkan pemahaman AI
- **Intelligent Fallback**: Sistem fallback berbasis keyword jika AI gagal

### 📊 Advanced Analytics & Visualization
- **Market Trends**: Analisis tren pasar smartphone per tahun
- **Brand Analysis**: Market share dan perbandingan brand
- **Price Analysis**: Distribusi harga dan korelasi spesifikasi
- **Performance Metrics**: Sistem scoring dan ranking performa

### 🔍 Dual Search System
- **AI Search**: Pencarian menggunakan bahasa natural
- **Manual Filter**: Filter tradisional dengan form dan slider

### 📈 Interactive Visualizations
- **Comparison Charts**: Perbandingan spesifikasi detail
- **Scatter Plots**: Analisis harga vs performa
- **Bar Charts & Pie Charts**: Berbagai metrik dan statistik

## 🛠️ Teknologi Stack

### Backend & AI
- **Python 3.8+**: Bahasa pemrograman utama
- **Streamlit**: Framework web app
- **Mistral AI (via OpenRouter)**: Large Language Model untuk NLP
- **Pandas**: Data manipulation dan analysis
- **NumPy**: Numerical computing

### Frontend & Visualization
- **Plotly**: Interactive charts dan visualizations
- **Streamlit Components**: UI components dan layouts
- **CSS Custom Styling**: Enhanced UI/UX design

### Data Processing
- **Regex**: Pattern matching untuk ekstraksi data
- **JSON Processing**: Structured data handling
- **Data Cleaning**: Outlier removal dan normalization

## 🏗️ Arsitektur Sistem

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   User Input    │───▶│   AI Engine     │───▶│  Smart Filter   │
│ (Natural Lang.) │    │ (Mistral AI)    │    │   System       │
└─────────────────┘    └──────────────────┘    └─────────────────┘
                                │                        │
                                ▼                        ▼
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│  Visualization  │◀───│  Data Manager   │◀───│   Results      │
│    Engine       │    │   & Cache       │    │ Processing     │
└─────────────────┘    └──────────────────┘    └─────────────────┘
```

## 📊 Workflow AI System

### 1. Input Processing
**User**: "HP gaming RAM 8GB harga 5 juta"

### 2. AI Analysis (Mistral AI)
```json
{
  "ram": 8,
  "price": {"approx": 5000000},
  "category": "gaming"
}
```

### 3. Smart Filtering
- Apply extracted parameters to dataset
- Progressive filtering for optimal results
- Rank by relevance and specifications

### 4. Result Generation
- AI-generated recommendation summary
- Interactive visualizations
- Detailed comparison charts

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- pip (Python package manager)

### Installation

#### 1. Clone Repository
```bash
git clone https://github.com/valentmamesah/phonemate-app.git
cd phonemate-app
```

#### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

#### 3. Prepare Dataset
```bash
# Dataset sudah tersedia di root directory
# File: "Mobiles Dataset (2025).csv"
```

#### 4. Setup API Key (For Local Development)
Untuk development lokal, buat file konfigurasi secrets:

```bash
# Create .streamlit/secrets.toml
mkdir .streamlit
echo 'OPENROUTER_API_KEY = "your-openrouter-api-key"' > .streamlit/secrets.toml
```

#### 5. Run Application
```bash
streamlit run app.py
```

## 🔑 API Configuration

### Local Development
Aplikasi menggunakan OpenRouter API dengan Mistral AI Nemo (Free):

1. Sign up di [OpenRouter.ai](https://openrouter.ai)
2. Dapatkan API key Anda
3. Tambahkan ke `.streamlit/secrets.toml`:
```toml
OPENROUTER_API_KEY = "sk-or-v1-your-api-key-here"
```

### Production Deployment (Streamlit Cloud)
Untuk deployment di Streamlit Cloud:

1. Fork repository ini
2. Deploy ke [Streamlit Cloud](https://share.streamlit.io)
3. Di dashboard Streamlit Cloud, tambahkan **Secrets** dengan format:
```toml
OPENROUTER_API_KEY = "sk-or-v1-your-api-key-here"
```

**Catatan**: API key untuk production sudah dikonfigurasi melalui Streamlit Cloud secrets, bukan file lokal.

## 📁 Project Structure

```
phonemate-app/
├── .devcontainer/         # Development container configuration
├── app.py                 # Main application file
├── requirements.txt       # Python dependencies
├── README.md             # Project documentation
├── Mobiles Dataset (2025).csv  # Dataset file
└── .streamlit/           # Streamlit configuration (local development)
    └── secrets.toml      # API keys (local development only)
```

## 🎯 Core Classes & Functions

### PhoneDataManager
- Dataset loading dan preprocessing
- Data cleaning dan normalization
- Sample data generation untuk demo

### AIRecommendationEngine
- Natural language processing
- Parameter extraction dari user input
- API communication dengan Mistral AI
- Intelligent fallback system

### SmartFilter
- Advanced filtering algorithms
- Progressive result optimization
- Multi-criteria decision making

### VisualizationEngine
- Interactive chart generation
- Comparison visualizations
- Performance analytics

## 📊 Dataset Requirements

Dataset harus mengandung kolom:
- **Company Name**: Brand smartphone
- **Model Name**: Nama model
- **RAM**: Kapasitas RAM
- **Back Camera**: Spesifikasi kamera
- **Battery Capacity**: Kapasitas baterai
- **Launched Price (USA)**: Harga dalam USD
- **Mobile Weight**: Berat perangkat
- **Screen Size**: Ukuran layar
- **Launched Year**: Tahun rilis

## 🔧 Configuration Options

### AI Model Settings
```python
MODEL = "mistralai/mistral-nemo:free"  # Free tier
# MODEL = "mistralai/mistral-7b-instruct"  # Paid alternative
```

### Filtering Parameters
- `min_results`: Minimum hasil yang ditampilkan
- `max_retries`: Maximum retry untuk API calls
- `cache_enabled`: Enable/disable result caching

## 🚦 Usage Examples

### Natural Language Queries
✅ "HP gaming RAM 8GB harga 5 juta"  
✅ "Smartphone murah tapi kamera bagus"  
✅ "HP flagship terbaru dengan baterai awet"  
✅ "Handphone ringan untuk travel di bawah 3 juta"  
✅ "HP untuk content creator dengan kamera 50MP"  

### Manual Filter Options
- **RAM**: 4GB, 6GB, 8GB, 12GB, 16GB+
- **Budget**: Range atau maksimal
- **Kamera**: Minimum megapixel
- **Baterai**: Minimum mAh
- **Layar**: Minimum inch
- **Tahun**: Range tahun rilis

## 🔍 API Integration

### OpenRouter Integration
```python
headers = {
    "Authorization": f"Bearer {API_KEY}",
    "Content-Type": "application/json"
}

body = {
    "model": "mistralai/mistral-nemo:free",
    "messages": [...],
    "temperature": 0.3,
    "max_tokens": 500
}
```

### Error Handling
- Rate limiting dengan exponential backoff
- JSON parsing dengan multiple patterns
- Graceful fallback ke keyword-based search
- Comprehensive logging dan error reporting

## 📈 Performance Optimization

- **Caching**: Result caching untuk query yang sama
- **Lazy Loading**: Data loading on-demand
- **Progressive Filtering**: Efficient dataset filtering
- **Session State**: Persistent state management

## 🚀 Deployment

### Streamlit Cloud (Recommended)
1. Fork repository ini
2. Connect dengan GitHub account di [Streamlit Cloud](https://share.streamlit.io)
3. Deploy aplikasi
4. Tambahkan API key melalui **Secrets** di dashboard Streamlit Cloud

### Local Development
1. Clone repository
2. Install dependencies: `pip install -r requirements.txt`
3. Setup API key di `.streamlit/secrets.toml`
4. Run: `streamlit run app.py`

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- **Mistral AI** for the powerful language model
- **OpenRouter** for API infrastructure
- **Streamlit** for the amazing web framework
- **Plotly** for interactive visualizations

---
