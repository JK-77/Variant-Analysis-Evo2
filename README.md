# 🧬 Biotech AI - Variant Analysis with Evo2

A state-of-the-art web application for predicting the pathogenicity of genetic variants using the Evo2 large language model. This project combines cutting-edge AI with clinical genomics data to provide actionable insights for variant analysis.

![Project Thumbnail](thumbnail.png)

## 🚀 Live Demo

- **Frontend**: http://localhost:3000 (when running locally)
- **Backend API**: Deployed on Modal with H100 GPU acceleration
- **Video Demo**: [Watch on YouTube](https://youtu.be/3dCZxmd5bvs)

## ✨ Features

- 🧬 **Evo2 Model** for variant effect prediction
- 🩺 **Pathogenicity Prediction** (pathogenic/benign) with confidence scores
- ⚖️ **ClinVar Integration** for comparison with existing classifications
- 🌍 **Genome Assembly Support** (hg38, hg19, etc.)
- 🗺️ **Gene Discovery** via chromosome browsing or search (e.g., BRCA1)
- 🌐 **Interactive Sequence Viewer** with clickable nucleotides
- 💻 **Python Backend** deployed with Modal on H100 GPU
- 🚀 **FastAPI Endpoint** for real-time variant analysis
- 📱 **Modern UI** built with Next.js, React, TypeScript, and Tailwind CSS

## 🏗️ Architecture

### Backend (Python + Modal + H100 GPU)
- **FastAPI** server deployed on Modal
- **Evo2 7B model** for variant effect prediction
- **UCSC Genome Browser API** integration
- **NCBI ClinVar API** for known variant classifications
- **GPU acceleration** for lightning-fast inference

### Frontend (Next.js + TypeScript)
- **Modern React** application with TypeScript
- **Tailwind CSS** + **Shadcn UI** for beautiful interface
- **Real-time variant analysis** with interactive genome browsing
- **Responsive design** for all devices

## 🛠️ Setup & Installation

### Prerequisites
- Python 3.10+
- Node.js 18+
- Modal account (free)

### Backend Setup

1. **Navigate to backend directory:**
   ```bash
   cd evo2-backend
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Setup Modal:**
   ```bash
   modal setup
   ```

4. **Deploy backend:**
   ```bash
   modal deploy main.py
   ```

### Frontend Setup

1. **Navigate to frontend directory:**
   ```bash
   cd evo2-frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure environment:**
   ```bash
   echo 'NEXT_PUBLIC_ANALYZE_SINGLE_VARIANT_BASE_URL=YOUR_MODAL_URL' > .env
   ```

4. **Start development server:**
   ```bash
   npm run dev
   ```

5. **Open browser:**
   Navigate to `http://localhost:3000`

## 🧬 How It Works

1. **Select Genome Assembly** (e.g., hg38)
2. **Search for Genes** (e.g., BRCA1) or browse chromosomes
3. **View Gene Sequence** with interactive nucleotide display
4. **Click on Nucleotides** or enter positions manually
5. **Get AI Predictions** (pathogenic/benign) with confidence scores
6. **Compare with ClinVar** classifications

## 🔬 Scientific Workflow

The application uses the Evo2 model to:
- Analyze DNA sequence windows around variant positions
- Calculate delta likelihood scores between reference and variant sequences
- Predict pathogenicity based on statistical thresholds
- Provide confidence estimates for predictions
- Compare results with existing clinical classifications

## 📊 API Endpoints

### Variant Analysis
```http
POST /analyze_single_variant
Content-Type: application/json

{
  "variant_position": 43119628,
  "alternative": "G",
  "genome": "hg38",
  "chromosome": "chr17"
}
```

**Response:**
```json
{
  "reference": "T",
  "alternative": "G",
  "delta_score": -1.0132789611816406e-06,
  "prediction": "Likely benign",
  "classification_confidence": 1.0,
  "position": 43119628
}
```

## 🧪 Example Usage

1. **Search for BRCA1** gene
2. **Click on nucleotide** at position 43119628
3. **Enter alternative** nucleotide (e.g., G)
4. **Get prediction** with confidence score
5. **Compare with ClinVar** if available

## 🔗 External APIs

- **UCSC Genome Browser API** - Genome sequence data
- **NCBI ClinVar API** - Known variant classifications
- **NCBI E-utilities** - Gene information and details

## 📚 References

- **Evo2 Paper**: [BioRxiv](https://www.biorxiv.org/content/10.1101/2025.02.18.638918v1)
- **Evo2 GitHub**: [ArcInstitute/evo2](https://github.com/ArcInstitute/evo2)
- **Modal Platform**: [Modal.com](https://modal.com)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE.MD](LICENSE.MD) file for details.

## 🙏 Acknowledgments

- **Arc Institute** for the Evo2 model
- **Modal** for GPU infrastructure
- **UCSC** for genome data
- **NCBI** for clinical variant data

---

**Built with ❤️ by Jayesh Kriplani for the bioinformatics community**
