# project_ai
## Cum să rulezi proiectul

### 1. Clonează Repozitoriul

Clonează repo-ul acestui proiect
```bash
git clone <link-to-your-repository>
cd <repository-directory>
```
### 2. Creează și Activează un Mediu Virtual
Este recomandat să folosești un mediu virtual pentru a izola dependențele proiectului:
```bash
python -m venv env
source env/bin/activate  # Pentru Windows: env\Scripts\activate
```

### 3. Instalează Dependențele


pip install -r requirements.txt
```
### 4. Organizează Fișierele .docx
Asigură-te că fișierele .docx sunt în directorul Oferte test. Acesta ar trebui să conțină fișierele de intrare din care se vor extrage cerințele și ofertele.

 ### 5. Rulează Scriptul
```bash
python main.py
```

## Pașii folosiți pentru a antrena AI-ul
### 1. Citirea Fișierelor .docx
Funcția read_docx(folder_path) citește fișierele .docx din directorul specificat și extrage textul relevant din acestea.

### 2. Preprocesarea Datelor
Funcția preprocess_data(requirements, offers) combină cerințele și ofertele într-un format adecvat pentru antrenarea modelului.

### 3. Tokenizarea Datelor
Datele sunt tokenizate folosind funcția tokenize_function(examples), care pregătește textul pentru modelul de limbaj.

### 4. Împărțirea Datelor
Setul de date este împărțit în seturi de antrenare și evaluare folosind funcția split_dataset(dataset, split_ratio=0.1).

### 5. Antrenarea Modelului
Modelul este antrenat folosind Trainer din biblioteca transformers. Parametrii de antrenare sunt specificați în TrainingArguments.

### 6. Salvarea Modelului
După antrenare, modelul și tokenizer-ul sunt salvați în directorul fine-tuned-gpt-neo.

### 7. Generarea Textului
Funcția generate_text(prompt, max_length=500, max_new_tokens=500) este folosită pentru a genera text pe baza unui prompt specificat.

