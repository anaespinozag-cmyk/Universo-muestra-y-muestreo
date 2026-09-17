<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Elección de los Participantes</title>
  <meta name="description" content="Guía interactiva para la elección de los participantes en investigación: conceptos, calculadora con fórmulas paso a paso, tipos de muestreo y generador aleatorio sin reemplazo." />
  
  <!-- Tailwind CSS por CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- KaTeX para fórmulas matemáticas -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.8/dist/katex.min.css" />
  <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.8/dist/katex.min.js"></script>
  
  <!-- jsPDF para exportar PDF -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
  
  <!-- Lucide Icons -->
  <script src="https://unpkg.com/lucide@latest"></script>
  
  <!-- Canvas Confetti -->
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

  <style>
    .math-font { font-family: 'Times New Roman', Times, serif; }
  </style>
</head>
<body class="bg-slate-100/80 text-slate-900 antialiased min-h-screen flex flex-col selection:bg-indigo-500 selection:text-white">

  <!-- BARRA SUPERIOR -->
  <header class="bg-white border-b border-slate-200 sticky top-0 z-30 shadow-xs">
    <div class="bg-slate-900 text-slate-100 text-xs py-1.5 px-4 sm:px-6">
      <div class="max-w-7xl mx-auto flex flex-wrap items-center justify-between gap-2">
        <div class="flex items-center gap-2">
          <span class="inline-flex items-center px-1.5 py-0.5 bg-indigo-500/20 text-indigo-300 rounded font-semibold text-[10px] tracking-wide uppercase">
            Guía Metodológica
          </span>
          <span class="text-slate-400">•</span>
          <span class="text-slate-300">Elección de los Participantes en Investigación</span>
        </div>
        <button onclick="toggleHistoryModal(true)" class="inline-flex items-center gap-1.5 hover:text-white cursor-pointer text-xs">
          <i data-lucide="history" class="w-3.5 h-3.5 text-indigo-400"></i>
          <span>Historial (<span id="historyCountBadge">0</span>)</span>
        </button>
      </div>
    </div>

    <div class="max-w-7xl mx-auto px-4 sm:px-6 py-3.5 flex flex-col lg:flex-row lg:items-center justify-between gap-4">
      <div class="flex items-center gap-3">
        <div class="w-10 h-10 rounded-xl bg-indigo-600 flex items-center justify-center text-white shadow-md">
          <i data-lucide="graduation-cap" class="w-5 h-5"></i>
        </div>
        <div>
          <h1 class="text-lg font-bold text-slate-900 leading-tight">Elección de los Participantes</h1>
          <p class="text-xs text-slate-500">De la teoría estadística a la selección aleatoria en campo</p>
        </div>
      </div>

      <!-- Navegación de Módulos -->
      <nav class="flex items-center gap-2 overflow-x-auto pb-1 lg:pb-0">
        <button onclick="switchTab(1)" id="tabBtn1" class="flex items-center gap-2 px-3.5 py-2 rounded-xl text-xs font-semibold bg-indigo-600 text-white transition-all cursor-pointer">
          <i data-lucide="book-open" class="w-4 h-4"></i>
          <span>1. Conceptos</span>
        </button>
        <button onclick="switchTab(2)" id="tabBtn2" class="flex items-center gap-2 px-3.5 py-2 rounded-xl text-xs font-semibold bg-slate-100 text-slate-600 hover:bg-slate-200 transition-all cursor-pointer">
          <i data-lucide="calculator" class="w-4 h-4"></i>
          <span>2. Cálculo</span>
        </button>
        <button onclick="switchTab(3)" id="tabBtn3" class="flex items-center gap-2 px-3.5 py-2 rounded-xl text-xs font-semibold bg-slate-100 text-slate-600 hover:bg-slate-200 transition-all cursor-pointer">
          <i data-lucide="layers" class="w-4 h-4"></i>
          <span>3. Tipos de Muestreo</span>
        </button>
        <button onclick="switchTab(4)" id="tabBtn4" class="flex items-center gap-2 px-3.5 py-2 rounded-xl text-xs font-semibold bg-slate-100 text-slate-600 hover:bg-slate-200 transition-all cursor-pointer">
          <i data-lucide="dices" class="w-4 h-4"></i>
          <span>4. Generador Aleatorio</span>
        </button>
      </nav>
    </div>
  </header>

  <!-- CONTENEDOR PRINCIPAL -->
  <main class="max-w-7xl w-full mx-auto px-4 sm:px-6 py-6 flex-1 space-y-6">

    <!-- ==================== PESTAÑA 1: CONCEPTOS ==================== -->
    <section id="panel1" class="space-y-6">
      <div class="bg-white rounded-2xl border border-slate-200 p-6 sm:p-7 shadow-xs">
        <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 pb-5 border-b border-slate-100">
          <div>
            <span class="inline-flex items-center gap-1 text-xs font-semibold text-indigo-700 bg-indigo-50 px-2 py-0.5 rounded-md mb-1 uppercase tracking-wider">
              Paso 1: Conceptos
            </span>
            <h2 class="text-xl font-bold text-slate-900">Delimitación de Población y Muestra</h2>
            <p class="text-xs text-slate-600 mt-1 max-w-2xl">
              Comprende los fundamentos estadísticos de la representatividad y el impacto matemático del factor de corrección por finitud.
            </p>
          </div>
          <button onclick="switchTab(2)" class="inline-flex items-center gap-2 px-4 py-2 bg-indigo-600 hover:bg-indigo-700 text-white rounded-xl text-xs font-semibold cursor-pointer shrink-0">
            <span>Ir a la Calculadora</span>
            <i data-lucide="arrow-right" class="w-3.5 h-3.5"></i>
          </button>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-5">
          <div class="bg-slate-50 p-4 rounded-xl border border-slate-200">
            <div class="flex items-center gap-2 mb-2">
              <span class="w-7 h-7 bg-blue-100 text-blue-700 font-bold rounded flex items-center justify-center text-xs">N</span>
              <h3 class="font-bold text-sm text-slate-900">Universo o Población Objetivo</h3>
            </div>
            <p class="text-xs text-slate-600 leading-relaxed">
              Totalidad de elementos o sujetos que comparten características observables comunes delimitadas en tiempo y espacio (parámetros poblacionales como la media μ o proporción P).
            </p>
          </div>

          <div class="bg-slate-50 p-4 rounded-xl border border-slate-200">
            <div class="flex items-center gap-2 mb-2">
              <span class="w-7 h-7 bg-emerald-100 text-emerald-700 font-bold rounded flex items-center justify-center text-xs">n</span>
              <h3 class="font-bold text-sm text-slate-900">Muestra Representativa</h3>
            </div>
            <p class="text-xs text-slate-600 leading-relaxed">
              Subconjunto extraído rigurosamente del universo que reproduce en pequeña escala su variabilidad intrínseca para efectuar inferencias con nivel de confianza y error predeterminados.
            </p>
          </div>
        </div>

        <!-- Demostrador FPC -->
        <div class="mt-6 bg-slate-900 text-white rounded-xl p-5">
          <h3 class="text-sm font-bold text-indigo-300 uppercase tracking-wider mb-1">
            Impacto del Factor de Corrección por Finitud (f.p.c.)
          </h3>
          <p class="text-xs text-slate-300 mb-4">
            ¿Por qué una población se considera infinita a partir de N ≥ 100,000? Mueve el deslizador y observa cómo n se estabiliza.
          </p>

          <div class="grid grid-cols-1 md:grid-cols-3 gap-4 items-center">
            <div>
              <label class="text-xs text-slate-400 block mb-1">Universo de prueba (N): <span id="fpcLabelN" class="text-white font-mono font-bold">5,000</span></label>
              <input type="range" id="fpcSliderN" min="200" max="200000" step="500" value="5000" oninput="updateFpcDemo(this.value)" class="w-full accent-indigo-500 cursor-pointer" />
              <div class="text-[11px] text-slate-400 mt-2" id="fpcMessage">Régimen finito: corrección activa.</div>
            </div>

            <div class="bg-slate-800 p-3 rounded-lg text-center">
              <span class="text-[10px] text-slate-400 uppercase block">Muestra Finita (n)</span>
              <span class="text-2xl font-black text-indigo-400 font-mono" id="fpcValueN">357</span>
              <span class="text-[10px] text-slate-400 block" id="fpcExactN">Exacto: 356.81</span>
            </div>

            <div class="bg-slate-800 p-3 rounded-lg text-center">
              <span class="text-[10px] text-slate-400 uppercase block">Muestra Infinita Base (n₀)</span>
              <span class="text-2xl font-black text-slate-200 font-mono">385</span>
              <span class="text-[10px] text-slate-400 block">Z=1.96, e=5%, p=0.50</span>
            </div>
          </div>
        </div>

        <!-- Chequeo de Comprensión con corrección lógica de retroalimentación -->
        <div class="mt-6 pt-5 border-t border-slate-100">
          <h3 class="text-sm font-bold text-slate-900 mb-3 flex items-center gap-2">
            <i data-lucide="help-circle" class="w-4 h-4 text-indigo-600"></i>
            Chequeo Rápido de Comprensión Metodológica
          </h3>

          <div class="space-y-4" id="quizContainer">
            <!-- Preguntas inyectadas por JS -->
          </div>
        </div>
      </div>
    </section>

    <!-- ==================== PESTAÑA 2: CÁLCULO ==================== -->
    <section id="panel2" class="space-y-6 hidden">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
        
        <!-- Controles (5 cols) -->
        <div class="lg:col-span-5 bg-white rounded-2xl border border-slate-200 p-5 sm:p-6 shadow-xs space-y-4">
          <div class="flex items-center justify-between pb-3 border-b border-slate-100">
            <h2 class="font-bold text-base text-slate-900">Calculadora de Muestra</h2>
            <span class="text-[11px] font-semibold text-indigo-600 bg-indigo-50 px-2 py-0.5 rounded">Rigor Matemático</span>
          </div>

          <!-- Tipo de variable -->
          <div>
            <label class="block text-xs font-semibold text-slate-700 mb-1.5">Enfoque Estadístico:</label>
            <div class="grid grid-cols-2 gap-2">
              <button onclick="setApproach('proportions')" id="approachPropBtn" class="py-2 px-3 text-xs font-bold rounded-lg border border-indigo-600 bg-indigo-50 text-indigo-700 cursor-pointer">
                Proporciones (%)
              </button>
              <button onclick="setApproach('means')" id="approachMeanBtn" class="py-2 px-3 text-xs font-bold rounded-lg border border-slate-200 bg-white text-slate-600 hover:bg-slate-50 cursor-pointer">
                Medias (x̄)
              </button>
            </div>
          </div>

          <!-- Nombre de escenario -->
          <div>
            <label class="block text-xs font-semibold text-slate-700 mb-1">Nombre del Estudio:</label>
            <input type="text" id="scenarioNameInput" value="Estudio de Campo Principal" class="w-full px-3 py-1.5 text-xs border border-slate-300 rounded-lg bg-slate-50" />
          </div>

          <!-- Población finita vs infinita -->
          <div class="p-3 bg-slate-50 rounded-xl border border-slate-200 space-y-2">
            <div class="flex items-center justify-between">
              <label class="text-xs font-bold text-slate-900">Universo / Población (N):</label>
              <label class="text-[11px] flex items-center gap-1.5 cursor-pointer text-slate-600">
                <input type="checkbox" id="finiteCheckbox" checked onchange="toggleFinite(this.checked)" class="accent-indigo-600 rounded" />
                Población Finita
              </label>
            </div>
            <div id="populationInputWrapper" class="flex items-center gap-2">
              <input type="number" id="populationInput" value="3500" min="10" oninput="recalculate()" class="w-full px-3 py-1.5 text-xs font-mono font-bold border border-slate-300 rounded-lg bg-white" />
              <span class="text-xs text-slate-500">sujetos</span>
            </div>
            <div id="finiteWarning" class="hidden text-[11px] text-amber-800 bg-amber-50 p-2 rounded border border-amber-200">
              Con N ≥ 100,000, la diferencia de finitud es menor al 0.05% (converge a infinita).
            </div>
          </div>

          <!-- Nivel de Confianza -->
          <div class="space-y-1.5">
            <div class="flex justify-between text-xs">
              <label class="font-bold text-slate-900">Nivel de Confianza (1 - α):</label>
              <span id="confidenceLabel" class="font-mono font-bold text-indigo-700">95% (Z = 1.96)</span>
            </div>
            <div class="grid grid-cols-3 gap-1.5 text-xs">
              <button onclick="setConfidence(90, 1.645)" class="py-1.5 rounded border border-slate-200 bg-white hover:bg-slate-50 font-semibold cursor-pointer">90%</button>
              <button onclick="setConfidence(95, 1.96)" class="py-1.5 rounded border border-indigo-600 bg-indigo-600 text-white font-semibold cursor-pointer">95%</button>
              <button onclick="setConfidence(99, 2.576)" class="py-1.5 rounded border border-slate-200 bg-white hover:bg-slate-50 font-semibold cursor-pointer">99%</button>
            </div>
          </div>

          <!-- Margen de Error -->
          <div class="space-y-1.5" id="propErrorWrapper">
            <div class="flex justify-between text-xs">
              <label class="font-bold text-slate-900">Margen de Error (e):</label>
              <span id="errorPropLabel" class="font-mono font-bold text-indigo-700">± 5.0%</span>
            </div>
            <input type="range" id="errorPropRange" min="0.01" max="0.15" step="0.005" value="0.05" oninput="recalculate()" class="w-full accent-indigo-600 cursor-pointer" />
          </div>

          <!-- Parámetro p para proporciones -->
          <div class="p-3 bg-amber-50 rounded-xl border border-amber-200 space-y-1.5" id="propPWrapper">
            <div class="flex justify-between text-xs font-bold text-amber-950">
              <span>Probabilidad de éxito (p):</span>
              <span id="propPLabel" class="font-mono">p = 0.50 | q = 0.50</span>
            </div>
            <input type="range" id="propPRange" min="0.05" max="0.95" step="0.05" value="0.50" oninput="recalculate()" class="w-full accent-amber-600 cursor-pointer" />
            <p class="text-[10px] text-amber-900 leading-tight">
              <strong>Máxima varianza:</strong> Ante la falta de literatura previa, fijar p = 0.50 otorga el tamaño muestral más seguro y protector.
            </p>
          </div>

          <!-- Parámetros para medias (ocultos inicialmente) -->
          <div class="p-3 bg-blue-50 rounded-xl border border-blue-200 space-y-2 hidden" id="meanParamsWrapper">
            <div class="grid grid-cols-2 gap-2 text-xs">
              <div>
                <label class="font-bold text-blue-950 block mb-1">Margen Error (e):</label>
                <input type="number" id="errorMeanInput" value="2.5" step="0.1" oninput="recalculate()" class="w-full px-2 py-1 border border-blue-200 rounded font-mono" />
              </div>
              <div>
                <label class="font-bold text-blue-950 block mb-1">Desv. Estándar (σ):</label>
                <input type="number" id="stdDevInput" value="12.0" step="0.1" oninput="recalculate()" class="w-full px-2 py-1 border border-blue-200 rounded font-mono" />
              </div>
            </div>
            <input type="text" id="unitInput" value="puntos" placeholder="Unidad de medida (ej. kg, puntos)" class="w-full px-2 py-1 text-xs border border-blue-200 rounded bg-white" />
          </div>
        </div>

        <!-- Resultados y Fórmulas en Vivo (7 cols) -->
        <div class="lg:col-span-7 space-y-5">
          <!-- Tarjeta de Dictamen -->
          <div class="bg-gradient-to-br from-indigo-900 via-slate-900 to-indigo-950 text-white rounded-2xl p-6 shadow-md border border-indigo-800">
            <div class="flex items-center justify-between pb-3 border-b border-indigo-700/60">
              <span class="text-xs text-indigo-300 font-bold uppercase tracking-wider">Dictamen Oficial de Tamaño Muestral</span>
              <span class="text-[10px] bg-indigo-800 px-2 py-0.5 rounded text-indigo-200 font-mono" id="approachBadge">Variable Cualitativa</span>
            </div>

            <div class="mt-4 flex flex-col sm:flex-row sm:items-end justify-between gap-3">
              <div>
                <span class="text-xs text-slate-300 uppercase font-medium tracking-wide">Muestra Formal Recomendada:</span>
                <div class="text-5xl font-black font-mono my-1 text-white" id="roundedNOutput">n = 347</div>
                <div class="text-xs text-indigo-200 font-mono" id="exactNOutput">Exacto continuo: 346.28 sujetos</div>
              </div>
              <div class="text-xs text-slate-300 bg-indigo-950/80 px-3 py-2 rounded-lg border border-indigo-700">
                <span class="font-bold block text-emerald-400">Redondeo obligatorio ceil(n)</span>
                Redondear hacia arriba evita sobrepasar el error fijado.
              </div>
            </div>

            <!-- Previsión no respuesta -->
            <div class="grid grid-cols-2 gap-2 mt-4 pt-3 border-t border-indigo-800/60 text-xs text-slate-300">
              <div class="bg-slate-800/80 p-2 rounded">
                <span class="text-[10px] text-slate-400 block">Previsión +10% pérdidas:</span>
                <span class="font-bold text-white font-mono" id="adjusted10Output">n* = 386</span>
              </div>
              <div class="bg-slate-800/80 p-2 rounded">
                <span class="text-[10px] text-slate-400 block">Previsión +20% pérdidas:</span>
                <span class="font-bold text-white font-mono" id="adjusted20Output">n* = 434</span>
              </div>
            </div>

            <!-- Botones de Acción -->
            <div class="mt-5 flex flex-wrap items-center gap-2">
              <button onclick="downloadPDFReport()" class="px-3.5 py-2 bg-white text-slate-900 hover:bg-slate-100 rounded-xl text-xs font-bold transition-all cursor-pointer inline-flex items-center gap-1.5">
                <i data-lucide="file-text" class="w-3.5 h-3.5 text-indigo-600"></i>
                <span>Descargar Dictamen PDF</span>
              </button>
              <button onclick="downloadCSVReport()" class="px-3 py-2 bg-indigo-800 hover:bg-indigo-700 text-white rounded-xl text-xs font-semibold transition-all cursor-pointer inline-flex items-center gap-1.5">
                <i data-lucide="file-spreadsheet" class="w-3.5 h-3.5"></i>
                <span>CSV</span>
              </button>
              <button onclick="saveCurrentScenario()" class="px-3 py-2 bg-indigo-700/60 hover:bg-indigo-700 text-white rounded-xl text-xs font-semibold transition-all cursor-pointer inline-flex items-center gap-1.5">
                <i data-lucide="history" class="w-3.5 h-3.5"></i>
                <span>Guardar Escenario</span>
              </button>
              <button onclick="sendToGenerator()" class="ml-auto px-3.5 py-2 bg-indigo-500 hover:bg-indigo-400 text-white rounded-xl text-xs font-bold transition-all cursor-pointer">
                Generador Aleatorio →
              </button>
            </div>
          </div>

          <!-- Fórmulas renderizadas en vivo con KaTeX -->
          <div class="bg-white rounded-2xl border border-slate-200 p-5 shadow-xs space-y-3">
            <h3 class="text-xs font-bold text-slate-800 uppercase tracking-wider">Fórmula Teórica y Sustitución Numérica en Vivo</h3>
            
            <div id="katexFormulaTeorica" class="py-3 text-center bg-slate-50 rounded-xl border border-slate-200 text-sm overflow-x-auto"></div>
            
            <div id="katexSustitucion" class="py-3 text-center bg-slate-50 rounded-xl border border-slate-200 text-sm overflow-x-auto"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- ==================== PESTAÑA 3: TIPOS DE MUESTREO ==================== -->
    <section id="panel3" class="space-y-6 hidden">
      <div class="bg-white rounded-2xl border border-slate-200 p-6 shadow-xs space-y-5">
        <div class="pb-3 border-b border-slate-100 flex items-center justify-between">
          <div>
            <span class="text-xs font-semibold text-emerald-700 bg-emerald-50 px-2 py-0.5 rounded">Paso 3: Metodología</span>
            <h2 class="text-xl font-bold text-slate-900 mt-1">Tipos de Muestreo</h2>
          </div>
          <div class="flex gap-1.5">
            <button onclick="setSamplingSubTab('prob')" id="subTabProb" class="px-3 py-1.5 text-xs font-bold bg-indigo-600 text-white rounded-lg cursor-pointer">
              Probabilísticos
            </button>
            <button onclick="setSamplingSubTab('nonprob')" id="subTabNonProb" class="px-3 py-1.5 text-xs font-bold bg-slate-100 text-slate-600 hover:bg-slate-200 rounded-lg cursor-pointer">
              No Probabilísticos
            </button>
          </div>
        </div>

        <!-- Muestreo Probabilístico -->
        <div id="probSection" class="space-y-5">
          <!-- Simulador Estratificado Interactivo -->
          <div class="p-4 bg-indigo-50/50 rounded-xl border border-indigo-200 space-y-3">
            <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-2">
              <div>
                <h3 class="font-bold text-sm text-indigo-950">Simulador de Muestreo Estratificado (Afijación Proporcional)</h3>
                <p class="text-xs text-indigo-900/80">Homogeneidad interna y heterogeneidad externa: divide por facultades, carreras o turnos.</p>
              </div>
              <div class="flex items-center gap-1.5 text-xs">
                <span class="font-semibold text-slate-700">Muestra total (n):</span>
                <input type="number" id="targetStrataN" value="347" oninput="recalculateStrata()" class="w-20 px-2 py-1 border border-indigo-300 rounded bg-white font-mono font-bold" />
              </div>
            </div>

            <div class="overflow-x-auto bg-white rounded-lg border border-slate-200">
              <table class="w-full text-xs text-left">
                <thead class="bg-slate-50 border-b border-slate-200 font-semibold text-slate-700">
                  <tr>
                    <th class="p-2.5">Estrato / Facultad</th>
                    <th class="p-2.5">Población (Nₕ)</th>
                    <th class="p-2.5">Proporción (%)</th>
                    <th class="p-2.5">Muestra Asignada (nₕ)</th>
                  </tr>
                </thead>
                <tbody id="strataTableBody" class="divide-y divide-slate-100 font-mono">
                  <!-- Rellenado dinámicamente -->
                </tbody>
              </table>
            </div>
          </div>

          <!-- Cuadro de técnicas probabilísticas -->
          <div class="grid grid-cols-1 md:grid-cols-3 gap-3 text-xs">
            <div class="p-3.5 bg-slate-50 rounded-xl border border-slate-200 space-y-1">
              <span class="font-bold text-slate-900 block">Aleatorio Simple (MAS)</span>
              <p class="text-slate-600">Todos los elementos tienen la misma probabilidad (1/N). Requiere un marco muestral estricto del 1 al N.</p>
            </div>
            <div class="p-3.5 bg-slate-50 rounded-xl border border-slate-200 space-y-1">
              <span class="font-bold text-slate-900 block">Sistemático (k = N/n)</span>
              <p class="text-slate-600">Selección por salto regular a partir de un arranque aleatorio equiprobable (a ∈ [1, k]).</p>
            </div>
            <div class="p-3.5 bg-slate-50 rounded-xl border border-slate-200 space-y-1">
              <span class="font-bold text-slate-900 block">Por Conglomerados</span>
              <p class="text-slate-600">Se eligen agrupaciones naturales completas (aulas, clínicas). Heterogeneidad interna y homogeneidad externa.</p>
            </div>
          </div>
        </div>

        <!-- Muestreo No Probabilístico -->
        <div id="nonProbSection" class="grid grid-cols-1 md:grid-cols-2 gap-3 text-xs hidden">
          <div class="p-3.5 bg-slate-50 rounded-xl border border-slate-200 space-y-1.5">
            <span class="font-bold text-slate-900 block">Por Conveniencia</span>
            <p class="text-slate-600">Sujetos seleccionados por proximidad y facilidad de acceso del investigador. Sesgo de voluntariado alto.</p>
            <span class="text-[10px] text-amber-800 font-semibold block">Válido en: pruebas piloto y estudios cualitativos.</span>
          </div>
          <div class="p-3.5 bg-slate-50 rounded-xl border border-slate-200 space-y-1.5">
            <span class="font-bold text-slate-900 block">Por Cuotas</span>
            <p class="text-slate-600">Fija metas por variables demográficas pero la selección final dentro del grupo queda a criterio del encuestador.</p>
            <span class="text-[10px] text-amber-800 font-semibold block">Válido en: sondeos comerciales rápidos.</span>
          </div>
          <div class="p-3.5 bg-slate-50 rounded-xl border border-slate-200 space-y-1.5">
            <span class="font-bold text-slate-900 block">Bola de Nieve (Snowball)</span>
            <p class="text-slate-600">Los participantes iniciales refieren a conocidos sucesivos. Sesgo de red social y homofilia.</p>
            <span class="text-[10px] text-amber-800 font-semibold block">Válido en: poblaciones ocultas o de difícil acceso.</span>
          </div>
          <div class="p-3.5 bg-slate-50 rounded-xl border border-slate-200 space-y-1.5">
            <span class="font-bold text-slate-900 block">Por Juicio o Intencional</span>
            <p class="text-slate-600">Selección deliberada de personas según la experiencia del evaluador (ej. panel de expertos Delphi).</p>
            <span class="text-[10px] text-amber-800 font-semibold block">Válido en: validación de instrumentos por jueces.</span>
          </div>
        </div>
      </div>
    </section>

    <!-- ==================== PESTAÑA 4: GENERADOR ALEATORIO ==================== -->
    <section id="panel4" class="space-y-6 hidden">
      <div class="bg-white rounded-2xl border border-slate-200 p-6 shadow-xs space-y-5">
        <div>
          <span class="text-xs font-semibold text-amber-800 bg-amber-50 px-2 py-0.5 rounded">Paso 4: Trabajo de Campo</span>
          <h2 class="text-xl font-bold text-slate-900 mt-1">Generador Aleatorio</h2>
          <p class="text-xs text-slate-600">Selección probabilística de elementos sin reemplazo para garantizar equiprobabilidad.</p>
        </div>

        <!-- ADVERTENCIA METODOLÓGICA Y GUÍA DE INICIO -->
        <div class="p-4 bg-amber-50 border-2 border-amber-300 rounded-xl text-amber-950 flex gap-3 text-xs leading-relaxed">
          <i data-lucide="alert-octagon" class="w-5 h-5 text-amber-700 shrink-0 mt-0.5"></i>
          <div class="space-y-1">
            <h4 class="font-bold text-amber-900 uppercase">Condición Metodológica Obligatoria</h4>
            <p>
              ¡Ningún sorteo es válido sin un <strong>Marco Muestral previo</strong>! Antes de generar números, debes tener una lista numerada del <strong>1 al N</strong> de todas las unidades del universo.
            </p>
            <div class="p-2 bg-white/70 rounded border border-amber-200 mt-1 space-y-0.5 text-[11px]">
              <div>• <strong>Muestreo Aleatorio Simple:</strong> Empieza directamente en el <strong>Paso 2</strong> (Sorteo de Participantes).</div>
              <div>• <strong>Muestreo Estratificado:</strong> Empieza en el <strong>Paso 1</strong> para seleccionar primero qué estratos o aulas formarán parte del estudio.</div>
            </div>
          </div>
        </div>

        <!-- Selector de Pasos -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-2 text-xs">
          <button onclick="setGenMode('strata')" id="genModeStrata" class="p-3 rounded-xl border border-slate-200 bg-white hover:bg-slate-50 text-left transition-all cursor-pointer">
            <span class="font-bold block text-slate-900">Paso 1: Sorteo de Estratos o Aulas</span>
            <span class="text-[10px] text-amber-800 font-semibold">Solo para Muestreo Estratificado</span>
          </button>
          <button onclick="setGenMode('participants')" id="genModePart" class="p-3 rounded-xl border border-indigo-600 bg-indigo-50 text-left transition-all cursor-pointer">
            <span class="font-bold block text-slate-900">Paso 2: Sorteo de Participantes</span>
            <span class="text-[10px] text-indigo-800 font-semibold">Inicio para Muestreo Aleatorio Simple</span>
          </button>
          <button onclick="setGenMode('systematic')" id="genModeSys" class="p-3 rounded-xl border border-slate-200 bg-white hover:bg-slate-50 text-left transition-all cursor-pointer">
            <span class="font-bold block text-slate-900">Paso 3: Sorteo Sistemático</span>
            <span class="text-[10px] text-emerald-800 font-semibold">Salto regular k = N/n</span>
          </button>
        </div>

        <!-- Controles y Resultados -->
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-6">
          <div class="lg:col-span-5 space-y-3 bg-slate-50 p-4 rounded-xl border border-slate-200">
            <div class="grid grid-cols-2 gap-2 text-xs">
              <div>
                <label class="font-bold text-slate-800 block mb-1">Universo Marco (N):</label>
                <input type="number" id="genNInput" value="3500" min="2" class="w-full px-2 py-1.5 border rounded font-mono font-bold" />
              </div>
              <div>
                <label class="font-bold text-slate-800 block mb-1">Muestra a Extraer (n):</label>
                <input type="number" id="genSampleInput" value="50" min="1" class="w-full px-2 py-1.5 border border-indigo-300 rounded font-mono font-bold text-indigo-700" />
              </div>
            </div>

            <div class="flex items-center justify-between text-xs py-1">
              <span class="text-slate-700 font-semibold">Sin Reemplazo (Sin duplicados):</span>
              <input type="checkbox" id="genWithoutRep" checked class="accent-indigo-600" />
            </div>

            <button onclick="executeDraw()" class="w-full py-2.5 bg-indigo-600 hover:bg-indigo-700 text-white rounded-xl text-xs font-bold transition-all cursor-pointer flex items-center justify-center gap-1.5">
              <i data-lucide="dices" class="w-4 h-4"></i>
              <span>Ejecutar Sorteo Aleatorio</span>
            </button>
          </div>

          <!-- Cuadrícula de números extraídos -->
          <div class="lg:col-span-7 bg-white p-4 rounded-xl border border-slate-200 space-y-3">
            <div class="flex items-center justify-between pb-2 border-b border-slate-100 text-xs">
              <span class="font-bold text-slate-800">Números Extraídos (<span id="drawCount">0</span>)</span>
              <div class="flex gap-1.5">
                <button onclick="toggleDrawSort()" class="px-2 py-1 bg-slate-100 hover:bg-slate-200 rounded text-[11px] font-semibold cursor-pointer">
                  <span id="sortBtnLabel">Ascendente (1...N)</span>
                </button>
                <button onclick="exportDrawCSV()" class="px-2 py-1 bg-emerald-50 text-emerald-800 border border-emerald-300 rounded text-[11px] font-semibold cursor-pointer">
                  CSV
                </button>
              </div>
            </div>

            <div id="drawGrid" class="grid grid-cols-4 sm:grid-cols-6 md:grid-cols-8 gap-1.5 max-h-64 overflow-y-auto p-1 font-mono text-xs">
              <div class="col-span-full py-8 text-center text-slate-400 text-xs">
                Presiona «Ejecutar Sorteo Aleatorio» para obtener los elementos equiprobables.
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

  </main>

  <!-- MODAL DE HISTORIAL -->
  <div id="historyModal" class="fixed inset-0 z-50 bg-slate-900/40 backdrop-blur-xs flex justify-end hidden">
    <div class="w-full max-w-md bg-white h-full shadow-2xl flex flex-col border-l border-slate-200 p-5">
      <div class="flex items-center justify-between pb-3 border-b border-slate-100">
        <h3 class="font-bold text-slate-900 text-sm flex items-center gap-2">
          <i data-lucide="history" class="w-4 h-4 text-indigo-600"></i>
          Historial de Consultas Guardadas
        </h3>
        <button onclick="toggleHistoryModal(false)" class="p-1 text-slate-400 hover:text-slate-600 cursor-pointer">
          <i data-lucide="x" class="w-4 h-4"></i>
        </button>
      </div>

      <div id="historyListContainer" class="flex-1 overflow-y-auto py-3 space-y-2 text-xs">
        <!-- Inyectado por JS -->
      </div>

      <div class="pt-3 border-t border-slate-100 flex justify-between">
        <button onclick="exportFullHistoryCSV()" class="px-3 py-1.5 text-xs font-semibold bg-slate-100 hover:bg-slate-200 rounded cursor-pointer">
          Exportar CSV
        </button>
        <button onclick="clearHistory()" class="px-3 py-1.5 text-xs text-rose-600 hover:bg-rose-50 rounded cursor-pointer">
          Vaciar
        </button>
      </div>
    </div>
  </div>

  <!-- JAVASCRIPT VANILLA -->
  <script>
    // Inicialización de iconos
    lucide.createIcons();

    // Estado global de la aplicación
    let activeTab = 1;
    let currentApproach = 'proportions';
    let currentConfidence = 95;
    let currentZ = 1.96;
    let isFinitePop = true;
    let historyScenarios = JSON.parse(localStorage.getItem('app_muestreo_history') || '[]');

    // Preguntas del Quiz
    const quizData = [
      {
        id: 1,
        question: '¿Por qué la literatura estadística fija N >= 100,000 como umbral para considerar una población infinita?',
        options: [
          'Porque en poblaciones de 100,000 o más personas ya no existen censos posibles.',
          'Porque matemáticamente el factor de corrección por finitud converge hacia 1 y la diferencia en n es de menos de 1 persona.',
          'Porque los softwares estadísticos no admiten números mayores a cinco dígitos.'
        ],
        correct: 1,
        explanation: 'Al evaluar N = 100,000 con confianza del 95% y margen de error del 5%, la muestra calculada con corrección finita es 383 y para N infinito es 384. La diferencia es de apenas una persona, por lo que la corrección por finitud deja de tener impacto práctico en la precisión.'
      },
      {
        id: 2,
        question: 'Si una investigación no cuenta con un marco muestral (lista exhaustiva y numerada del universo):',
        options: [
          'Se puede aplicar muestreo aleatorio simple siempre que se use una calculadora científica.',
          'No es posible ejecutar un muestreo probabilístico estricto; se debe recurrir a muestreos no probabilísticos o construir el marco.',
          'Se asume que la población es infinita y se calcula la muestra sin inconveniente alguno.'
        ],
        correct: 1,
        explanation: 'El marco muestral es el requisito indispensable de todo muestreo probabilístico. Sin una lista numerada del 1 al N, es imposible garantizar que todas las unidades tengan una probabilidad conocida y no nula de ser seleccionadas.'
      },
      {
        id: 3,
        question: 'Si un investigador no tiene literatura previa ni estudio piloto sobre la prevalencia de su variable cualitativa, ¿qué valor debe asignar a p?',
        options: [
          'p = 0.05, correspondiente al margen de error habitual.',
          'p = 0.50, adoptando el supuesto de máxima varianza o incertidumbre metodológica.',
          'p = 1.00, para abarcar la totalidad del fenómeno estudiado.'
        ],
        correct: 1,
        explanation: 'El valor p = 0.50 maximiza el producto p · q = 0.25, lo cual genera el tamaño muestral más conservador y robusto posible, protegiendo la investigación contra subestimaciones de la muestra requerida.'
      }
    ];

    let userQuizAnswers = {};

    // Renderizar Quiz
    function renderQuiz() {
      const container = document.getElementById('quizContainer');
      container.innerHTML = '';

      quizData.forEach(q => {
        const userAnswer = userQuizAnswers[q.id];
        const isAnswered = userAnswer !== undefined;
        const isCorrect = isAnswered && userAnswer === q.correct;

        let optionsHtml = q.options.map((opt, idx) => {
          let style = "border-slate-200 hover:bg-slate-50 text-slate-700";
          if (isAnswered) {
            if (idx === q.correct) style = "border-emerald-500 bg-emerald-50 text-emerald-900 font-semibold";
            else if (idx === userAnswer) style = "border-rose-400 bg-rose-50 text-rose-900";
          }

          return `
            <button onclick="answerQuiz(${q.id}, ${idx})" ${isAnswered ? 'disabled' : ''} class="w-full text-left p-2.5 rounded-lg border text-xs transition-all cursor-pointer flex items-start gap-2 ${style}">
              <span class="w-4 h-4 rounded-full border border-current flex items-center justify-center text-[10px] shrink-0 mt-0.5">${String.fromCharCode(65 + idx)}</span>
              <span>${opt}</span>
            </button>
          `;
        }).join('');

        let feedbackHtml = '';
        if (isAnswered) {
          feedbackHtml = `
            <div class="mt-2.5 p-3 rounded-lg text-xs leading-relaxed border ${isCorrect ? 'bg-emerald-50 text-emerald-950 border-emerald-300' : 'bg-rose-50 text-rose-950 border-rose-300'}">
              <div class="flex items-center justify-between mb-1">
                <span class="font-bold ${isCorrect ? 'text-emerald-800' : 'text-rose-800'}">
                  ${isCorrect ? '¡Respuesta correcta!' : 'Respuesta incorrecta'}
                </span>
                <button onclick="retryQuiz(${q.id})" class="text-[11px] underline cursor-pointer text-slate-600 hover:text-indigo-600">Reintentar</button>
              </div>
              ${!isCorrect ? `<p class="font-medium text-rose-900 mb-1">La opción correcta es la <strong>${String.fromCharCode(65 + q.correct)}:</strong> ${q.options[q.correct]}</p>` : ''}
              <p class="${isCorrect ? 'text-emerald-900' : 'text-slate-700'}"><strong>${isCorrect ? 'Explicación: ' : 'Fundamento: '}</strong>${q.explanation}</p>
            </div>
          `;
        }

        const card = document.createElement('div');
        card.className = "bg-white p-4 rounded-xl border border-slate-200 shadow-2xs";
        card.innerHTML = `
          <div class="font-bold text-xs text-slate-900 mb-2">${q.id}. ${q.question}</div>
          <div class="space-y-1.5">${optionsHtml}</div>
          ${feedbackHtml}
        `;
        container.appendChild(card);
      });
      lucide.createIcons();
    }

    function answerQuiz(qId, optionIdx) {
      userQuizAnswers[qId] = optionIdx;
      renderQuiz();
    }

    function retryQuiz(qId) {
      delete userQuizAnswers[qId];
      renderQuiz();
    }

    // Navegación de pestañas
    function switchTab(tabNum) {
      activeTab = tabNum;
      for (let i = 1; i <= 4; i++) {
        document.getElementById(`panel${i}`).classList.toggle('hidden', i !== tabNum);
        const btn = document.getElementById(`tabBtn${i}`);
        if (i === tabNum) {
          btn.className = "flex items-center gap-2 px-3.5 py-2 rounded-xl text-xs font-semibold bg-indigo-600 text-white transition-all cursor-pointer";
        } else {
          btn.className = "flex items-center gap-2 px-3.5 py-2 rounded-xl text-xs font-semibold bg-slate-100 text-slate-600 hover:bg-slate-200 transition-all cursor-pointer";
        }
      }
      lucide.createIcons();
    }

    // Demostrador FPC en Pestaña 1
    function updateFpcDemo(val) {
      const N = Number(val);
      document.getElementById('fpcLabelN').innerText = N.toLocaleString('es-ES');
      const z = 1.96, p = 0.5, q = 0.5, e = 0.05;
      const n0 = (z * z * p * q) / (e * e);
      const exact = (N * z * z * p * q) / (e * e * (N - 1) + z * z * p * q);
      const ceil = Math.ceil(exact);

      document.getElementById('fpcValueN').innerText = ceil;
      document.getElementById('fpcExactN').innerText = `Exacto: ${exact.toFixed(2)}`;
      const msg = document.getElementById('fpcMessage');
      if (N >= 100000) {
        msg.innerHTML = "<span class='text-emerald-400 font-semibold'>✓ Régimen infinito: la diferencia es de apenas 1 sujeto.</span>";
      } else {
        msg.innerHTML = "<span class='text-amber-300 font-semibold'>⚡ Régimen finito: corrección sustancial activa.</span>";
      }
    }

    // Control de Enfoque en Calculadora
    function setApproach(app) {
      currentApproach = app;
      document.getElementById('approachPropBtn').className = app === 'proportions' ? "py-2 px-3 text-xs font-bold rounded-lg border border-indigo-600 bg-indigo-50 text-indigo-700 cursor-pointer" : "py-2 px-3 text-xs font-bold rounded-lg border border-slate-200 bg-white text-slate-600 hover:bg-slate-50 cursor-pointer";
      document.getElementById('approachMeanBtn').className = app === 'means' ? "py-2 px-3 text-xs font-bold rounded-lg border border-indigo-600 bg-indigo-50 text-indigo-700 cursor-pointer" : "py-2 px-3 text-xs font-bold rounded-lg border border-slate-200 bg-white text-slate-600 hover:bg-slate-50 cursor-pointer";

      document.getElementById('propErrorWrapper').classList.toggle('hidden', app !== 'proportions');
      document.getElementById('propPWrapper').classList.toggle('hidden', app !== 'proportions');
      document.getElementById('meanParamsWrapper').classList.toggle('hidden', app !== 'means');
      document.getElementById('approachBadge').innerText = app === 'proportions' ? 'Variable Cualitativa' : 'Variable Cuantitativa';

      recalculate();
    }

    function toggleFinite(val) {
      isFinitePop = val;
      document.getElementById('populationInputWrapper').classList.toggle('hidden', !val);
      recalculate();
    }

    function setConfidence(conf, z) {
      currentConfidence = conf;
      currentZ = z;
      document.getElementById('confidenceLabel').innerText = `${conf}% (Z = ${z})`;
      recalculate();
    }

    // Cálculo y renderizado de fórmulas KaTeX
    let lastCalculatedData = {};

    function recalculate() {
      const N = isFinitePop ? Math.max(1, Number(document.getElementById('populationInput').value)) : null;
      document.getElementById('finiteWarning').classList.toggle('hidden', !isFinitePop || N < 100000);

      let exactN = 0;
      let n0 = 0;
      let formulaTeoricaTex = '';
      let sustitucionTex = '';

      if (currentApproach === 'proportions') {
        const e = Number(document.getElementById('errorPropRange').value);
        const p = Number(document.getElementById('propPRange').value);
        const q = 1 - p;

        document.getElementById('errorPropLabel').innerText = `± ${(e * 100).toFixed(1)}%`;
        document.getElementById('propPLabel').innerText = `p = ${p.toFixed(2)} | q = ${q.toFixed(2)}`;

        n0 = (currentZ * currentZ * p * q) / (e * e);

        if (isFinitePop && N) {
          const num = N * currentZ * currentZ * p * q;
          const den = e * e * (N - 1) + currentZ * currentZ * p * q;
          exactN = num / den;

          formulaTeoricaTex = "n = \\frac{N \\cdot Z^2 \\cdot p \\cdot q}{e^2 \\cdot (N - 1) + Z^2 \\cdot p \\cdot q}";
          sustitucionTex = `n = \\frac{${N} \\cdot (${currentZ})^2 \\cdot ${p} \\cdot ${q.toFixed(2)}}{(${e})^2 \\cdot (${N} - 1) + (${currentZ})^2 \\cdot ${p} \\cdot ${q.toFixed(2)}} = ${exactN.toFixed(2)}`;
        } else {
          exactN = n0;
          formulaTeoricaTex = "n_0 = \\frac{Z^2 \\cdot p \\cdot q}{e^2}";
          sustitucionTex = `n_0 = \\frac{(${currentZ})^2 \\cdot ${p} \\cdot ${q.toFixed(2)}}{(${e})^2} = ${exactN.toFixed(2)}`;
        }
      } else {
        const e = Number(document.getElementById('errorMeanInput').value);
        const sigma = Number(document.getElementById('stdDevInput').value);

        n0 = (currentZ * currentZ * sigma * sigma) / (e * e);

        if (isFinitePop && N) {
          const num = N * currentZ * currentZ * sigma * sigma;
          const den = e * e * (N - 1) + currentZ * currentZ * sigma * sigma;
          exactN = num / den;

          formulaTeoricaTex = "n = \\frac{N \\cdot Z^2 \\cdot \\sigma^2}{e^2 \\cdot (N - 1) + Z^2 \\cdot \\sigma^2}";
          sustitucionTex = `n = \\frac{${N} \\cdot (${currentZ})^2 \\cdot (${sigma})^2}{(${e})^2 \\cdot (${N} - 1) + (${currentZ})^2 \\cdot (${sigma})^2} = ${exactN.toFixed(2)}`;
        } else {
          exactN = n0;
          formulaTeoricaTex = "n_0 = \\frac{Z^2 \\cdot \\sigma^2}{e^2}";
          sustitucionTex = `n_0 = \\frac{(${currentZ})^2 \\cdot (${sigma})^2}{(${e})^2} = ${exactN.toFixed(2)}`;
        }
      }

      const ceilN = Math.ceil(exactN);
      document.getElementById('roundedNOutput').innerText = `n = ${ceilN}`;
      document.getElementById('exactNOutput').innerText = `Exacto continuo: ${exactN.toFixed(2)} sujetos`;
      document.getElementById('adjusted10Output').innerText = `n* = ${Math.ceil(ceilN / 0.90)}`;
      document.getElementById('adjusted20Output').innerText = `n* = ${Math.ceil(ceilN / 0.80)}`;

      // Renderizar KaTeX
      if (window.katex) {
        katex.render(formulaTeoricaTex, document.getElementById('katexFormulaTeorica'), { throwOnError: false });
        katex.render(sustitucionTex, document.getElementById('katexSustitucion'), { throwOnError: false });
      }

      lastCalculatedData = {
        name: document.getElementById('scenarioNameInput').value,
        approach: currentApproach,
        isFinite: isFinitePop,
        populationN: N,
        confidence: currentConfidence,
        z: currentZ,
        roundedN: ceilN,
        exactN: exactN,
        timestamp: Date.now()
      };
    }

    // Exportar PDF con membrete
    function downloadPDFReport() {
      const { jsPDF } = window.jspdf;
      const doc = new jsPDF({ orientation: 'portrait', unit: 'mm', format: 'a4' });
      const margin = 20;

      // Encabezado
      doc.setFillColor(30, 41, 59);
      doc.rect(margin, 20, 170, 22, 'F');
      doc.setTextColor(255, 255, 255);
      doc.setFontSize(12);
      doc.setFont('helvetica', 'bold');
      doc.text('ELECCIÓN DE LOS PARTICIPANTES - GUÍA DE MUESTREO', margin + 5, 29);
      doc.setFontSize(8);
      doc.setFont('helvetica', 'normal');
      doc.text('DICTAMEN TÉCNICO Y MEMORIA DE CÁLCULO DE TAMAÑO MUESTRAL', margin + 5, 36);

      // Metadatos
      doc.setTextColor(51, 65, 85);
      doc.setFontSize(9);
      doc.text(`Estudio: ${lastCalculatedData.name}`, margin, 52);
      doc.text(`Fecha: ${new Date().toLocaleString('es-ES')}`, margin, 58);
      doc.text(`Enfoque: ${lastCalculatedData.approach === 'proportions' ? 'Proporciones (Cualitativa)' : 'Medias (Cuantitativa)'}`, margin, 64);
      doc.text(`Universo (N): ${lastCalculatedData.isFinite ? lastCalculatedData.populationN.toLocaleString('es-ES') : 'Infinita / Desconocida'}`, margin, 70);
      doc.text(`Confianza: ${lastCalculatedData.confidence}% (Z = ${lastCalculatedData.z})`, margin, 76);

      // Resultado
      doc.setFillColor(238, 242, 255);
      doc.rect(margin, 85, 170, 25, 'F');
      doc.setTextColor(49, 46, 129);
      doc.setFontSize(14);
      doc.setFont('helvetica', 'bold');
      doc.text(`TAMAÑO MUESTRAL FORMAL RECOMENDADO: n = ${lastCalculatedData.roundedN}`, margin + 5, 98);
      doc.setFontSize(8.5);
      doc.setFont('helvetica', 'normal');
      doc.text(`Valor analítico continuo: ${lastCalculatedData.exactN.toFixed(2)} | Regla metodológica: Redondeo superior ceil(n).`, margin + 5, 104);

      doc.save(`Dictamen_Muestra_n${lastCalculatedData.roundedN}.pdf`);
    }

    // Exportar CSV
    function downloadCSVReport() {
      const csvContent = "data:text/csv;charset=utf-8,\uFEFF"
        + "Parametro;Valor\n"
        + `Estudio;${lastCalculatedData.name}\n`
        + `Enfoque;${lastCalculatedData.approach}\n`
        + `Muestra recomendada ceil(n);${lastCalculatedData.roundedN}\n`
        + `Muestra continua exacto;${lastCalculatedData.exactN.toFixed(4)}\n`
        + `Nivel de confianza;${lastCalculatedData.confidence}%\n`
        + `Valor Z;${lastCalculatedData.z}\n`
        + `Universo N;${lastCalculatedData.isFinite ? lastCalculatedData.populationN : 'Infinita'}\n`;

      const encodedUri = encodeURI(csvContent);
      const link = document.createElement("a");
      link.setAttribute("href", encodedUri);
      link.setAttribute("download", `Calculo_Muestra_${Date.now()}.csv`);
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    }

    // Historial
    function saveCurrentScenario() {
      historyScenarios.unshift(lastCalculatedData);
      localStorage.setItem('app_muestreo_history', JSON.stringify(historyScenarios));
      updateHistoryBadge();
      alert('¡Escenario guardado en el historial del navegador!');
    }

    function updateHistoryBadge() {
      document.getElementById('historyCountBadge').innerText = historyScenarios.length;
    }

    function toggleHistoryModal(show) {
      document.getElementById('historyModal').classList.toggle('hidden', !show);
      if (show) renderHistoryList();
    }

    function renderHistoryList() {
      const c = document.getElementById('historyListContainer');
      if (historyScenarios.length === 0) {
        c.innerHTML = '<div class="py-8 text-center text-slate-400">No hay registros guardados.</div>';
        return;
      }
      c.innerHTML = historyScenarios.map((item, idx) => `
        <div class="p-3 bg-slate-50 rounded-lg border border-slate-200">
          <div class="flex justify-between font-bold text-slate-800">
            <span>${item.name}</span>
            <span class="text-indigo-600 font-mono">n = ${item.roundedN}</span>
          </div>
          <div class="text-[11px] text-slate-500 mt-1">${new Date(item.timestamp).toLocaleString('es-ES')} • Conf. ${item.confidence}%</div>
        </div>
      `).join('');
    }

    function clearHistory() {
      if (confirm('¿Vaciar todo el historial?')) {
        historyScenarios = [];
        localStorage.removeItem('app_muestreo_history');
        updateHistoryBadge();
        renderHistoryList();
      }
    }

    function exportFullHistoryCSV() {
      if (historyScenarios.length === 0) return;
      let csv = "data:text/csv;charset=utf-8,\uFEFFNombre;Enfoque;Muestra;Confianza;Universo\n";
      historyScenarios.forEach(h => {
        csv += `"${h.name}";"${h.approach}";${h.roundedN};"${h.confidence}%";"${h.isFinite ? h.populationN : 'Infinita'}"\n`;
      });
      const link = document.createElement("a");
      link.setAttribute("href", encodeURI(csv));
      link.setAttribute("download", `Historial_Muestreo_${Date.now()}.csv`);
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    }

    function sendToGenerator() {
      document.getElementById('genSampleInput').value = lastCalculatedData.roundedN;
      if (lastCalculatedData.isFinite) {
        document.getElementById('genNInput').value = lastCalculatedData.populationN;
      }
      switchTab(4);
    }

    // Pestaña 3: Muestreo Estratificado
    const defaultStrata = [
      { name: 'Facultad de Ciencias de la Salud', size: 1450 },
      { name: 'Facultad de Ingeniería y Arquitectura', size: 1100 },
      { name: 'Facultad de Ciencias Económicas', size: 850 },
      { name: 'Facultad de Ciencias Sociales', size: 600 }
    ];

    function recalculateStrata() {
      const targetN = Math.max(1, Number(document.getElementById('targetStrataN').value));
      const totalN = defaultStrata.reduce((acc, s) => acc + s.size, 0);
      const tbody = document.getElementById('strataTableBody');
      tbody.innerHTML = '';

      defaultStrata.forEach(s => {
        const prop = (s.size / totalN);
        const nh = Math.round(prop * targetN);
        const tr = document.createElement('tr');
        tr.innerHTML = `
          <td class="p-2.5 font-sans font-medium text-slate-800">${s.name}</td>
          <td class="p-2.5">${s.size.toLocaleString('es-ES')}</td>
          <td class="p-2.5 text-slate-500">${(prop * 100).toFixed(1)}%</td>
          <td class="p-2.5 font-bold text-indigo-700">nₕ = ${nh}</td>
        `;
        tbody.appendChild(tr);
      });
    }

    function setSamplingSubTab(type) {
      document.getElementById('probSection').classList.toggle('hidden', type !== 'prob');
      document.getElementById('nonProbSection').classList.toggle('hidden', type !== 'nonprob');
      document.getElementById('subTabProb').className = type === 'prob' ? "px-3 py-1.5 text-xs font-bold bg-indigo-600 text-white rounded-lg cursor-pointer" : "px-3 py-1.5 text-xs font-bold bg-slate-100 text-slate-600 hover:bg-slate-200 rounded-lg cursor-pointer";
      document.getElementById('subTabNonProb').className = type === 'nonprob' ? "px-3 py-1.5 text-xs font-bold bg-indigo-600 text-white rounded-lg cursor-pointer" : "px-3 py-1.5 text-xs font-bold bg-slate-100 text-slate-600 hover:bg-slate-200 rounded-lg cursor-pointer";
    }

    // Pestaña 4: Generador Aleatorio
    let genMode = 'participants';
    let drawnNumbers = [];
    let isSortAsc = true;

    function setGenMode(mode) {
      genMode = mode;
      document.getElementById('genModeStrata').className = mode === 'strata' ? "p-3 rounded-xl border border-indigo-600 bg-indigo-50 text-left transition-all cursor-pointer" : "p-3 rounded-xl border border-slate-200 bg-white hover:bg-slate-50 text-left transition-all cursor-pointer";
      document.getElementById('genModePart').className = mode === 'participants' ? "p-3 rounded-xl border border-indigo-600 bg-indigo-50 text-left transition-all cursor-pointer" : "p-3 rounded-xl border border-slate-200 bg-white hover:bg-slate-50 text-left transition-all cursor-pointer";
      document.getElementById('genModeSys').className = mode === 'systematic' ? "p-3 rounded-xl border border-indigo-600 bg-indigo-50 text-left transition-all cursor-pointer" : "p-3 rounded-xl border border-slate-200 bg-white hover:bg-slate-50 text-left transition-all cursor-pointer";

      if (mode === 'strata') {
        document.getElementById('genNInput').value = 10;
        document.getElementById('genSampleInput').value = 3;
      }
    }

    function executeDraw() {
      const N = Math.max(1, Number(document.getElementById('genNInput').value));
      const n = Math.max(1, Number(document.getElementById('genSampleInput').value));
      const withoutRep = document.getElementById('genWithoutRep').checked;

      if (withoutRep && n > N) {
        alert('En sorteo sin reemplazo n no puede ser mayor a N.');
        return;
      }

      if (genMode === 'systematic') {
        const k = Math.floor(N / n);
        const a = Math.floor(Math.random() * k) + 1;
        drawnNumbers = Array.from({ length: n }, (_, i) => a + i * k);
      } else {
        if (withoutRep) {
          const pool = Array.from({ length: N }, (_, i) => i + 1);
          for (let i = pool.length - 1; i > 0; i--) {
            const j = Math.floor(Math.random() * (i + 1));
            [pool[i], pool[j]] = [pool[j], pool[i]];
          }
          drawnNumbers = pool.slice(0, n);
        } else {
          drawnNumbers = Array.from({ length: n }, () => Math.floor(Math.random() * N) + 1);
        }
      }

      renderDrawGrid();
      if (window.confetti) confetti({ particleCount: 40, spread: 60 });
    }

    function renderDrawGrid() {
      const grid = document.getElementById('drawGrid');
      document.getElementById('drawCount').innerText = drawnNumbers.length;
      grid.innerHTML = '';

      const list = isSortAsc ? [...drawnNumbers].sort((a, b) => a - b) : drawnNumbers;
      list.forEach((num, idx) => {
        const div = document.createElement('div');
        div.className = "p-2 bg-slate-50 hover:bg-indigo-50 rounded border border-slate-200 text-center";
        div.innerHTML = `<span class="text-[9px] text-slate-400 block">#${idx + 1}</span><span class="font-bold text-indigo-950">${num}</span>`;
        grid.appendChild(div);
      });
    }

    function toggleDrawSort() {
      isSortAsc = !isSortAsc;
      document.getElementById('sortBtnLabel').innerText = isSortAsc ? 'Ascendente (1...N)' : 'Extracción';
      renderDrawGrid();
    }

    function exportDrawCSV() {
      if (drawnNumbers.length === 0) return;
      const csv = "data:text/csv;charset=utf-8,\uFEFFOrden;ID_Marco_Muestral\n"
        + drawnNumbers.map((num, i) => `${i + 1};${num}`).join('\n');
      const link = document.createElement("a");
      link.setAttribute("href", encodeURI(csv));
      link.setAttribute("download", `Sorteo_Aleatorio_${Date.now()}.csv`);
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    }

    // Inicialización al cargar la página
    window.addEventListener('DOMContentLoaded', () => {
      renderQuiz();
      recalculate();
      updateFpcDemo(5000);
      recalculateStrata();
      updateHistoryBadge();
    });
  </script>
</body>
</html>
