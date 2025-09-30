# odev
"Fotosentez aşamaları eğitim sayfası"
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Fotosentez Aşamaları - İnteraktif Eğitim</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --primary-color: #2e7d32;
      --secondary-color: #81c784;
      --accent-color: #ffeb3b;
      --light-bg: #f1f8e9;
      --dark-text: #1b5e20;
      --shadow: 0 4px 8px rgba(0,0,0,0.1);
      --transition: all 0.3s ease;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #e8f5e9, #c8e6c9);
      color: var(--dark-text);
      line-height: 1.6;
      padding: 20px;
      min-height: 100vh;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
    }

    header {
      text-align: center;
      margin-bottom: 40px;
      padding: 30px;
      background-color: white;
      border-radius: 20px;
      box-shadow: var(--shadow);
      position: relative;
      overflow: hidden;
    }

    header::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 5px;
      background: linear-gradient(90deg, #4caf50, #ffeb3b, #4caf50);
    }

    h1 {
      font-size: 2.8rem;
      margin-bottom: 15px;
      color: var(--primary-color);
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 15px;
    }

    .subtitle {
      font-size: 1.3rem;
      color: #4caf50;
      max-width: 800px;
      margin: 0 auto 20px;
    }

    .intro-text {
      max-width: 900px;
      margin: 0 auto;
      font-size: 1.1rem;
      color: #555;
    }

    .stats-container {
      display: flex;
      justify-content: center;
      gap: 30px;
      margin: 25px 0;
      flex-wrap: wrap;
    }

    .stat-box {
      background: white;
      padding: 15px 25px;
      border-radius: 10px;
      box-shadow: var(--shadow);
      text-align: center;
      min-width: 150px;
    }

    .stat-value {
      font-size: 1.8rem;
      font-weight: bold;
      color: var(--primary-color);
    }

    .stat-label {
      font-size: 0.9rem;
      color: #666;
    }

    .tabs {
      display: flex;
      justify-content: center;
      margin-bottom: 30px;
      gap: 10px;
    }

    .tab {
      padding: 12px 25px;
      background: white;
      border-radius: 30px;
      cursor: pointer;
      font-weight: bold;
      transition: var(--transition);
      box-shadow: var(--shadow);
    }

    .tab.active {
      background: var(--primary-color);
      color: white;
    }

    .process-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 25px;
      margin-bottom: 40px;
    }

    .phase {
      flex: 1;
      min-width: 300px;
      background-color: white;
      border-radius: 20px;
      overflow: hidden;
      box-shadow: var(--shadow);
      transition: var(--transition);
    }

    .phase:hover {
      transform: translateY(-10px);
      box-shadow: 0 12px 20px rgba(0,0,0,0.15);
    }

    .phase-header {
      background: linear-gradient(135deg, var(--primary-color), #4caf50);
      color: white;
      padding: 20px;
      text-align: center;
      font-size: 1.4rem;
      font-weight: bold;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
    }

    .steps-container {
      padding: 25px;
    }

    .step {
      background-color: var(--light-bg);
      border-radius: 12px;
      padding: 20px;
      margin-bottom: 20px;
      cursor: pointer;
      transition: var(--transition);
      border-left: 5px solid var(--secondary-color);
      position: relative;
      overflow: hidden;
    }

    .step:hover {
      background-color: var(--secondary-color);
      transform: translateX(5px);
    }

    .step.active {
      background-color: var(--secondary-color);
      border-left-color: var(--primary-color);
    }

    .step-header {
      display: flex;
      align-items: center;
      font-weight: bold;
      margin-bottom: 10px;
      font-size: 1.1rem;
    }

    .step-number {
      background: var(--primary-color);
      color: white;
      width: 30px;
      height: 30px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-right: 15px;
      font-size: 0.9rem;
    }

    .step-icon {
      margin-right: 15px;
      font-size: 1.8rem;
    }

    .step-info {
      display: none;
      padding-top: 15px;
      border-top: 1px dashed #a5d6a7;
      animation: fadeIn 0.5s ease;
    }

    .step.active .step-info {
      display: block;
    }

    .chemical-equation {
      background: rgba(255,255,255,0.7);
      padding: 10px;
      border-radius: 8px;
      margin: 10px 0;
      font-family: 'Courier New', monospace;
      text-align: center;
      font-weight: bold;
    }

    .visualization {
      background-color: white;
      border-radius: 20px;
      padding: 35px;
      box-shadow: var(--shadow);
      margin-bottom: 40px;
      text-align: center;
    }

    .vis-title {
      font-size: 1.7rem;
      margin-bottom: 25px;
      color: var(--primary-color);
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
    }

    .vis-container {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-wrap: wrap;
      gap: 25px;
      margin: 30px 0;
    }

    .vis-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 140px;
      transition: var(--transition);
    }

    .vis-item:hover {
      transform: scale(1.1);
    }

    .vis-circle {
      width: 100px;
      height: 100px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 2.2rem;
      margin-bottom: 15px;
      box-shadow: var(--shadow);
      transition: var(--transition);
    }

    .vis-label {
      font-size: 1rem;
      text-align: center;
      font-weight: bold;
    }

    .arrow {
      font-size: 2.5rem;
      color: var(--primary-color);
      transition: var(--transition);
    }

    .quiz-section {
      background: white;
      border-radius: 20px;
      padding: 30px;
      box-shadow: var(--shadow);
      margin-bottom: 40px;
    }

    .quiz-title {
      font-size: 1.7rem;
      margin-bottom: 20px;
      color: var(--primary-color);
      text-align: center;
    }

    .quiz-question {
      font-size: 1.2rem;
      margin-bottom: 20px;
    }

    .quiz-options {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 15px;
      margin-bottom: 25px;
    }

    .quiz-option {
      padding: 15px;
      background: var(--light-bg);
      border-radius: 10px;
      cursor: pointer;
      transition: var(--transition);
    }

    .quiz-option:hover {
      background: var(--secondary-color);
    }

    .quiz-option.correct {
      background: #4caf50;
      color: white;
    }

    .quiz-option.incorrect {
      background: #f44336;
      color: white;
    }

    .quiz-result {
      text-align: center;
      font-size: 1.2rem;
      margin-top: 20px;
      display: none;
    }

    footer {
      text-align: center;
      padding: 25px;
      background-color: white;
      border-radius: 15px;
      box-shadow: var(--shadow);
      font-size: 1rem;
      color: #666;
    }

    .footer-links {
      display: flex;
      justify-content: center;
      gap: 20px;
      margin-top: 15px;
    }

    .footer-link {
      color: var(--primary-color);
      text-decoration: none;
      transition: var(--transition);
    }

    .footer-link:hover {
      text-decoration: underline;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.05); }
      100% { transform: scale(1); }
    }

    .pulse {
      animation: pulse 2s infinite;
    }

    @media (max-width: 768px) {
      .phase {
        min-width: 100%;
      }

      .arrow {
        transform: rotate(90deg);
      }

      .vis-container {
        flex-direction: column;
      }

      .quiz-options {
        grid-template-columns: 1fr;
      }

      .stats-container {
        flex-direction: column;
        align-items: center;
      }

      h1 {
        font-size: 2.2rem;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <h1><i class="fas fa-leaf"></i> Fotosentez Aşamaları <i class="fas fa-leaf"></i></h1>
      <p class="subtitle">Bitkilerin güneş enerjisini kimyasal enerjiye dönüştürme sürecini keşfedin</p>
      <p class="intro-text">Fotosentez, yeşil bitkilerin, alglerin ve bazı bakterilerin güneş ışığını kullanarak karbondioksit ve suyu glikoza dönüştürdüğü hayati bir biyolojik süreçtir. Bu işlem sırasında oksijen açığa çıkar.</p>

      <div class="stats-container">
        <div class="stat-box">
          <div class="stat-value">%70</div>
          <div class="stat-label">Dünya Oksijeni</div>
        </div>
        <div class="stat-box">
          <div class="stat-value">6CO₂ + 6H₂O</div>
          <div class="stat-label">Reaktantlar</div>
        </div>
        <div class="stat-box">
          <div class="stat-value">C₆H₁₂O₆ + 6O₂</div>
          <div class="stat-label">Ürünler</div>
        </div>
      </div>
    </header>

    <div class="tabs">
      <div class="tab active" data-tab="process">Süreç Aşamaları</div>
      <div class="tab" data-tab="quiz">Bilgi Testi</div>
    </div>

    <div id="process-tab" class="tab-content">
      <div class="process-container">
        <div class="phase">
          <div class="phase-header">
            <i class="fas fa-sun"></i> Işığa Bağlı Evreler
          </div>
          <div class="steps-container">
            <div class="step">
              <div class="step-header">
                <div class="step-number">1</div>
                <span class="step-icon">🌞</span>
                Işık Emilimi
              </div>
              <div class="step-info">
                Klorofil ve diğer pigmentler güneş ışığını emer ve elektronları uyarır. Işık enerjisi kimyasal enerjiye dönüştürülür.
                <div class="chemical-equation">Işık + Klorofil → Uyarılmış Elektronlar</div>
              </div>
            </div>

            <div class="step">
              <div class="step-header">
                <div class="step-number">2</div>
                <span class="step-icon">⚡</span>
                Elektron Taşıma Sistemi
              </div>
              <div class="step-info">
                Yüksek enerjili elektronlar elektron taşıma zincirinden geçer ve enerjileri ATP ve NADPH sentezi için kullanılır.
                <div class="chemical-equation">Uyarılmış e⁻ + NADP⁺ + H⁺ → NADPH</div>
              </div>
            </div>

            <div class="step">
              <div class="step-header">
                <div class="step-number">3</div>
                <span class="step-icon">🔋</span>
                ATP Sentezi
              </div>
              <div class="step-info">
                Fotofosforilasyon ile ADP'ye fosfat eklenerek ATP sentezlenir. Bu, proton gradienti sayesinde ATP sentaz enzimi tarafından gerçekleştirilir.
                <div class="chemical-equation">ADP + Pi + Enerji → ATP</div>
              </div>
            </div>

            <div class="step">
              <div class="step-header">
                <div class="step-number">4</div>
                <span class="step-icon">💧</span>
                Suyun Parçalanması
              </div>
              <div class="step-info">
                Su molekülleri parçalanarak oksijen, proton ve elektron açığa çıkar. Bu işlem fotoliz olarak adlandırılır.
                <div class="chemical-equation">2H₂O → 4H⁺ + 4e⁻ + O₂</div>
              </div>
            </div>
          </div>
        </div>

        <div class="phase">
          <div class="phase-header">
            <i class="fas fa-moon"></i> Işıktan Bağımsız Evreler
          </div>
          <div class="steps-container">
            <div class="step">
              <div class="step-header">
                <div class="step-number">5</div>
                <span class="step-icon">🌱</span>
                Calvin Döngüsü
              </div>
              <div class="step-info">
                Karbon fiksasyonu, indirgenme ve ribuloz-1,5-bifosfatın yenilenmesi aşamalarından oluşur. Işığa bağlı evrelerde üretilen ATP ve NADPH kullanılır.
              </div>
            </div>

            <div class="step">
              <div class="step-header">
                <div class="step-number">6</div>
                <span class="step-icon">🍃</span>
                Karbon Fiksasyonu
              </div>
              <div class="step-info">
                CO₂, ribuloz-1,5-bifosfat (RuBP) ile birleşerek kararsız 6-karbonlu ara ürün oluşturur, bu da iki molekül 3-fosfogliserata (3-PGA) ayrılır.
                <div class="chemical-equation">CO₂ + RuBP → 2 × 3-PGA</div>
              </div>
            </div>

            <div class="step">
              <div class="step-header">
                <div class="step-number">7</div>
                <span class="step-icon">🔄</span>
                İndirgenme
              </div>
              <div class="step-info">
                3-fosfogliserat, ATP ve NADPH kullanılarak gliseraldehit-3-fosfata (G3P) dönüştürülür. G3P, glikoz ve diğer karbonhidratların sentezi için temel yapı taşıdır.
                <div class="chemical-equation">3-PGA + ATP + NADPH → G3P</div>
              </div>
            </div>

            <div class="step">
              <div class="step-header">
                <div class="step-number">8</div>
                <span class="step-icon">🔄</span>
                Ribulozun Yenilenmesi
              </div>
              <div class="step-info">
                Gliseraldehit-3-fosfatın bir kısmı ribuloz-1,5-bifosfatı yenilemek için kullanılır, böylece döngü devam eder.
                <div class="chemical-equation">5 G3P + 3 ATP → 3 RuBP</div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="visualization">
        <h2 class="vis-title"><i class="fas fa-project-diagram"></i> Fotosentez Süreci Görselleştirmesi</h2>
        <div class="vis-container">
          <div class="vis-item">
            <div class="vis-circle pulse" style="background-color: #ffeb3b;">
              🌞
            </div>
            <div class="vis-label">Işık Enerjisi</div>
          </div>

          <div class="arrow">→</div>

          <div class="vis-item">
            <div class="vis-circle" style="background-color: #4caf50;">
              💧
            </div>
            <div class="vis-label">Su (H₂O)</div>
          </div>

          <div class="arrow">→</div>

          <div class="vis-item">
            <div class="vis-circle" style="background-color: #2196f3;">
              🌿
            </div>
            <div class="vis-label">Klorofil</div>
          </div>

          <div class="arrow">→</div>

          <div class="vis-item">
            <div class="vis-circle" style="background-color: #ff9800;">
              🍃
            </div>
            <div class="vis-label">Glikoz (C₆H₁₂O₆)</div>
          </div>

          <div class="arrow">→</div>

          <div class="vis-item">
            <div class="vis-circle" style="background-color: #f44336;">
              💨
            </div>
            <div class="vis-label">Oksijen (O₂)</div>
          </div>
        </div>

        <div class="chemical-equation" style="font-size: 1.3rem; margin-top: 20px;">
          6CO₂ + 6H₂O + Işık Enerjisi → C₆H₁₂O₆ + 6O₂
        </div>
      </div>
    </div>

    <div id="quiz-tab" class="tab-content" style="display: none;">
      <div class="quiz-section">
        <h2 class="quiz-title"><i class="fas fa-question-circle"></i> Fotosentez Bilgi Testi</h2>

        <div class="quiz-question" id="question">Fotosentez hangi organelde gerçekleşir?</div>

        <div class="quiz-options" id="options">
          <div class="quiz-option" data-correct="false">Mitokondri</div>
          <div class="quiz-option" data-correct="true">Kloroplast</div>
          <div class="quiz-option" data-correct="false">Ribozom</div>
          <div class="quiz-option" data-correct="false">Golgi cisimciği</div>
        </div>

        <button id="next-question" style="display: block; margin: 0 auto; padding: 12px 25px; background: var(--primary-color); color: white; border: none; border-radius: 8px; cursor: pointer; font-size: 1rem;">Sonraki Soru</button>

        <div class="quiz-result" id="result"></div>
      </div>
    </div>

    <footer>
      <p>Fotosentez, bitkilerin güneş enerjisini kimyasal enerjiye dönüştürerek besin ürettiği hayati bir biyolojik süreçtir.</p>
      <p>© 2025 Fotosentez Eğitim Sayfası | Tüm hakları ARAL RÜZGAR DOĞAN Tarafından saklıdır.</p>
      <div class="footer-links">
        <a href="#" class="footer-link">Hakkında</a>
        <a href="#" class="footer-link">Kaynaklar</a>
        <a href="#" class="footer-link">İletişim</a>
      </div>
    </footer>
  </div>

  <script>
    // Aşamaların tıklanabilir olmasını sağlayan JavaScript
    document.querySelectorAll('.step').forEach(step => {
      step.addEventListener('click', () => {
        step.classList.toggle('active');
      });
    });

    // Sekme değiştirme işlevi
    document.querySelectorAll('.tab').forEach(tab => {
      tab.addEventListener('click', () => {
        // Tüm sekmeleri ve içerikleri sıfırla
        document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
        document.querySelectorAll('.tab-content').forEach(content => content.style.display = 'none');

        // Aktif sekme ve içeriği göster
        tab.classList.add('active');
        const tabId = tab.getAttribute('data-tab') + '-tab';
        document.getElementById(tabId).style.display = 'block';
      });
    });

    // Quiz işlevselliği
    const questions = [
      {
        question: "Fotosentez hangi organelde gerçekleşir?",
        options: ["Mitokondri", "Kloroplast", "Ribozom", "Golgi cisimciği"],
        correct: 1
      },
      {
        question: "Fotosentez sırasında açığa çıkan gaz nedir?",
        options: ["Karbondioksit", "Azot", "Oksijen", "Hidrojen"],
        correct: 2
      },
      {
        question: "Fotosentezin ışığa bağımlı reaksiyonlarında üretilen enerji molekülleri hangileridir?",
        options: ["ATP ve NADPH", "Glikoz ve Oksijen", "ADP ve NADP+", "Karbondioksit ve Su"],
        correct: 0
      },
      {
        question: "Fotosentezin genel kimyasal denklemi nedir?",
        options: [
          "6O₂ + 6H₂O → C₆H₁₂O₆ + 6CO₂",
          "6CO₂ + 6H₂O → C₆H₁₂O₆ + 6O₂",
          "C₆H₁₂O₆ + 6O₂ → 6CO₂ + 6H₂O",
          "6CO₂ + 6O₂ → C₆H₁₂O₆ + 6H₂O"
        ],
        correct: 1
      }
    ];

    let currentQuestion = 0;
    let score = 0;

    function loadQuestion() {
      const question = questions[currentQuestion];
      document.getElementById('question').textContent = question.question;

      const optionsContainer = document.getElementById('options');
      optionsContainer.innerHTML = '';

      question.options.forEach((option, index) => {
        const optionElement = document.createElement('div');
        optionElement.className = 'quiz-option';
        optionElement.textContent = option;
        optionElement.setAttribute('data-correct', index === question.correct ? 'true' : 'false');

        optionElement.addEventListener('click', function() {
          if (this.getAttribute('data-correct') === 'true') {
            this.classList.add('correct');
            score++;
          } else {
            this.classList.add('incorrect');
            // Doğru cevabı göster
            document.querySelectorAll('.quiz-option')[question.correct].classList.add('correct');
          }

          // Tüm seçenekleri tıklanamaz yap
          document.querySelectorAll('.quiz-option').forEach(opt => {
            opt.style.pointerEvents = 'none';
          });
        });

        optionsContainer.appendChild(optionElement);
      });

      document.getElementById('result').style.display = 'none';
    }

    document.getElementById('next-question').addEventListener('click', function() {
      currentQuestion++;

      if (currentQuestion < questions.length) {
        loadQuestion();
      } else {
        // Test bitti, sonucu göster
        document.getElementById('question').textContent = "Test Tamamlandı!";
        document.getElementById('options').innerHTML = '';
        document.getElementById('next-question').style.display = 'none';

        const result = document.getElementById('result');
        result.textContent = `Skorunuz: ${score} / ${questions.length}`;
        result.style.display = 'block';
      }
    });

    // İlk soruyu yükle
    loadQuestion();
  </script>
</body>
</html>
