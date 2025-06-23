# Explorando-la-Teor-a-Sexual-de-Freud
<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Explorador Minimalista de Freud</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">

    <!-- Chosen Palette: Minimalist Gray-Teal -->
    <!-- Application Structure Plan: La aplicación mantiene una estructura de secciones temáticas (Inicio, Conceptos, Desarrollo, Clínica/Críticas, Síntesis) navegables desde un menú fijo. Se enfoca en una presentación concisa y directa, priorizando la legibilidad y la facilidad de exploración. Cada sección presenta su contenido de forma condensada, utilizando interacciones simples para revelar detalles clave sin abrumar al usuario. -->
    <!-- Visualization & Content Choices: 1. Pulsiones (Eros/Thanatos): Meta: Ilustrar dualidad. Visualización: Gráfico de dona (Chart.js). Interacción: Tooltip básico. Justificación: Representación visual directa y concisa de dos conceptos opuestos. 2. Desarrollo Psicosexual: Meta: Mostrar fases secuenciales. Visualización: Botones de etapa con contenido dinámico (HTML/JS). Interacción: Clic para alternar la vista de detalles. Justificación: Permite al usuario explorar cada fase a su ritmo, manteniendo el diseño limpio. 3. Clínica/Legado/Críticas: Meta: Organizar información multifacética. Visualización: Pestañas de contenido (HTML/JS). Interacción: Clic para cambiar entre vistas. Justificación: Compacta grandes bloques de texto en un espacio reducido, mejorando la navegación. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->

    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8f8f8;
            color: #333333;
        }
        .nav-link {
            transition: all 0.2s ease-in-out;
            border-bottom: 2px solid transparent;
        }
        .nav-link.active, .nav-link:hover {
            color: #88a0a0;
            border-bottom-color: #88a0a0;
        }
        .stage-button, .tab-button {
            transition: all 0.2s ease-in-out;
            border-color: #e0e0e0;
        }
        .stage-button.active, .tab-button.active, .stage-button:hover, .tab-button:hover {
            background-color: #88a0a0;
            color: white;
            border-color: #88a0a0;
        }
        .content-card {
            background-color: white;
            border-radius: 0.5rem;
            box-shadow: 0 1px 3px 0 rgb(0 0 0 / 0.1), 0 1px 2px -1px rgb(0 0 0 / 0.1);
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 300px; /* Smaller max-width for minimalism */
            margin-left: auto;
            margin-right: auto;
            height: 250px; /* Smaller height */
            max-height: 300px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 300px;
            }
        }
    </style>
</head>
<body class="antialiased">

    <header class="bg-white/80 backdrop-blur-md shadow-sm sticky top-0 z-50">
        <nav class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-14">
                <div class="flex-shrink-0">
                    <span class="text-lg font-bold text-gray-800">Freud Minimal</span>
                </div>
                <div class="hidden md:block">
                    <div class="ml-10 flex items-baseline space-x-3">
                        <a href="#inicio" class="nav-link px-2 py-1 rounded-md text-sm font-medium">Inicio</a>
                        <a href="#conceptos" class="nav-link px-2 py-1 rounded-md text-sm font-medium">Conceptos</a>
                        <a href="#desarrollo" class="nav-link px-2 py-1 rounded-md text-sm font-medium">Desarrollo</a>
                        <a href="#clinica" class="nav-link px-2 py-1 rounded-md text-sm font-medium">Clínica & Críticas</a>
                        <a href="#sintesis" class="nav-link px-2 py-1 rounded-md text-sm font-medium">Síntesis</a>
                    </div>
                </div>
            </div>
        </nav>
    </header>

    <main>
        <section id="inicio" class="py-16 md:py-20">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8 text-center">
                <h1 class="text-3xl md:text-5xl font-bold tracking-tight text-gray-900">Explorando la Teoría de Freud</h1>
                <p class="mt-4 max-w-2xl mx-auto text-base md:text-lg text-gray-600">
                    Una vista concisa de los "Tres ensayos para una teoría sexual". Navega para descubrir sus ideas clave.
                </p>
            </div>
        </section>

        <section id="conceptos" class="py-12 bg-white">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-10">
                    <h2 class="text-2xl font-bold tracking-tight text-gray-900 sm:text-3xl">Conceptos Clave</h2>
                    <p class="mt-3 text-base text-gray-600">Fundamentos de la visión freudiana de la sexualidad.</p>
                </div>
                <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <div class="content-card p-5">
                        <h3 class="text-lg font-semibold mb-2 text-gray-800">Libido: Energía Psíquica</h3>
                        <p class="text-gray-600 text-sm">Fuerza motriz de la vida psíquica, más allá de la reproducción. Amor y construcción.</p>
                    </div>
                    <div class="content-card p-5">
                        <h3 class="text-lg font-semibold mb-2 text-gray-800">Instintos Parciales</h3>
                        <p class="text-gray-600 text-sm">Impulsos innatos (succión, prensión) ligados a zonas erógenas. Gratificación clave para la personalidad.</p>
                    </div>
                    <div class="content-card p-5">
                        <h3 class="text-lg font-semibold mb-2 text-gray-800">Eros y Thanatos</h3>
                        <p class="text-gray-600 text-sm">Dualidad pulsional: Eros (vida, amor) y Thanatos (muerte, agresión, autodestrucción).</p>
                        <div class="chart-container mt-4">
                            <canvas id="drivesChart"></canvas>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="desarrollo" class="py-12">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-10">
                    <h2 class="text-2xl font-bold tracking-tight text-gray-900 sm:text-3xl">Desarrollo Psicosexual</h2>
                    <p class="mt-3 text-base text-gray-600">Etapas del desarrollo de la personalidad freudiana. Haz clic para ver detalles.</p>
                </div>
                
                <div class="w-full mb-6">
                    <div class="flex flex-col md:flex-row justify-between items-center space-y-3 md:space-y-0 md:space-x-3">
                        <button class="stage-button w-full md:w-auto flex-1 px-3 py-1.5 border rounded-md text-sm font-semibold">Oral (0-1)</button>
                        <button class="stage-button w-full md:w-auto flex-1 px-3 py-1.5 border rounded-md text-sm font-semibold">Anal (1-3)</button>
                        <button class="stage-button w-full md:w-auto flex-1 px-3 py-1.5 border rounded-md text-sm font-semibold">Fálica (3-6)</button>
                        <button class="stage-button w-full md:w-auto flex-1 px-3 py-1.5 border rounded-md text-sm font-semibold">Latencia (6-pub.)</button>
                        <button class="stage-button w-full md:w-auto flex-1 px-3 py-1.5 border rounded-md text-sm font-semibold">Genital (pub. +)</button>
                    </div>
                </div>

                <div id="stage-content" class="content-card p-6 min-h-[15rem] flex items-center justify-center text-center">
                    <div>
                        <h3 id="stage-title" class="text-xl font-bold text-gray-800 mb-2">Selecciona una etapa</h3>
                        <p id="stage-description" class="text-gray-600 text-sm">La información de la etapa aparecerá aquí.</p>
                        <div id="stage-details" class="mt-3 text-left text-sm"></div>
                    </div>
                </div>
            </div>
        </section>
        
        <section id="clinica" class="py-12 bg-white">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                 <div class="text-center mb-10">
                    <h2 class="text-2xl font-bold tracking-tight text-gray-900 sm:text-3xl">Clínica, Legado y Críticas</h2>
                    <p class="mt-3 text-base text-gray-600">Impacto, métodos y debates en torno a la teoría freudiana.</p>
                </div>

                <div class="w-full max-w-3xl mx-auto">
                    <div class="mb-4 flex space-x-1 p-0.5 bg-gray-200 rounded-lg">
                        <button class="tab-button w-full py-1.5 text-sm font-medium leading-5 text-gray-700 rounded-md" data-tab="clinica">Clínica</button>
                        <button class="tab-button w-full py-1.5 text-sm font-medium leading-5 text-gray-700 rounded-md" data-tab="legado">Legado</button>
                        <button class="tab-button w-full py-1.5 text-sm font-medium leading-5 text-gray-700 rounded-md" data-tab="criticas">Críticas</button>
                    </div>
                    <div id="tab-content-container" class="mt-2">
                        <div id="tab-clinica" class="tab-content content-card p-6 text-sm"></div>
                        <div id="tab-legado" class="tab-content hidden content-card p-6 text-sm"></div>
                        <div id="tab-criticas" class="tab-content hidden content-card p-6 text-sm"></div>
                    </div>
                </div>
            </div>
        </section>
        
        <section id="sintesis" class="py-12">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-10">
                    <h2 class="text-2xl font-bold tracking-tight text-gray-900 sm:text-3xl">Síntesis Crítica</h2>
                    <p class="mt-3 text-base text-gray-600">Balance de aportes y limitaciones de la teoría freudiana.</p>
                </div>

                <div class="content-card overflow-x-auto">
                    <table class="min-w-full divide-y divide-gray-200">
                        <thead class="bg-gray-50">
                            <tr>
                                <th scope="col" class="px-5 py-2 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Aporte Central</th>
                                <th scope="col" class="px-5 py-2 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Limitaciones / Críticas</th>
                            </tr>
                        </thead>
                        <tbody id="sintesis-table-body" class="bg-white divide-y divide-gray-200 text-sm">
                        </tbody>
                    </table>
                </div>
            </div>
        </section>

    </main>

    <footer class="bg-white mt-12 border-t">
        <div class="container mx-auto py-4 px-4 sm:px-6 lg:px-8 text-center text-gray-500 text-xs">
            <p>&copy; 2025 Explorador de Freud. Fines educativos.</p>
        </div>
    </footer>

    <script>
        const appData = {
            stages: {
                oral: {
                    title: 'Fase Oral (0-1 año)',
                    description: 'Placer en boca: succión, alimentación.',
                    details: `<ul>
                        <li>Zona: Boca.</li>
                        <li>Actividad: Succión, morder.</li>
                        <li>Fijaciones: Dependencia, agresividad oral.</li>
                    </ul>`
                },
                anal: {
                    title: 'Fase Anal (1-3 años)',
                    description: 'Placer en control de esfínteres.',
                    details: `<ul>
                        <li>Zona: Ano.</li>
                        <li>Actividad: Retención/expulsión.</li>
                        <li>Fijaciones: Rigidez, tacañería o desorden.</li>
                    </ul>`
                },
                falica: {
                    title: 'Fase Fálica (3-6 años)',
                    description: 'Interés en genitales; Complejo de Edipo.',
                    details: `<ul>
                        <li>Zona: Genitales.</li>
                        <li>Conflicto: Complejo de Edipo.</li>
                        <li>Fijaciones: Problemas de identidad, vanidad.</li>
                    </ul>`
                },
                latencia: {
                    title: 'Período de Latencia (6-pubertad)',
                    description: 'Energía redirigida a aprendizaje y socialización.',
                    details: `<p>Calma sexual. Desarrollo de pudor, moral.</p>`
                },
                genital: {
                    title: 'Fase Genital (Pubertad en adelante)',
                    description: 'Libido hacia objetos externos, relaciones maduras.',
                    details: `<p>Búsqueda de gratificación mutua. Equilibrio amor/trabajo.</p>`
                }
            },
            tabs: {
                clinica: `
                    <h3 class="text-base font-semibold mb-3 text-gray-800">Clínica Psicoanalítica</h3>
                    <div class="space-y-2 text-gray-600">
                        <div><strong>Edipo:</strong> Deseo inconsciente por progenitor opuesto.</div>
                        <div><strong>Sexualidad Infantil:</strong> "Perversión polimorfa" en niños.</div>
                        <div><strong>Neurosis:</strong> Represión de pulsiones causa síntomas.</div>
                        <div><strong>Métodos:</strong> Asociación libre, análisis de sueños.</div>
                    </div>`,
                legado: `
                    <h3 class="text-base font-semibold mb-3 text-gray-800">Legado Multidisciplinar</h3>
                    <div class="space-y-2 text-gray-600">
                        <div><strong>Psicología:</strong> Fundó el psicoanálisis (pulsión, inconsciente).</div>
                        <div><strong>Sociología:</strong> Instituciones moldean sexualidad, tabúes.</div>
                        <div><strong>Filosofía:</strong> Conflicto instinto vs. norma social.</div>
                    </div>`,
                criticas: `
                    <h3 class="text-base font-semibold mb-3 text-gray-800">Principales Críticas</h3>
                    <div class="space-y-2 text-gray-600">
                         <div><strong>Homosexualidad:</strong> Vista como variante, no patología actual.</div>
                        <div><strong>Feministas:</strong> Androcentrismo (envidia del pene).</div>
                        <div><strong>Posestructuralismo:</strong> Criticó medicalización sexual.</div>
                    </div>`
            },
            sintesis: [
                { aporte: 'Sexualidad: motor psíquico', critica: 'Modelos iniciales heteronormativos' },
                { aporte: 'Pulsiones (Eros/Thanatos)', critica: 'Thanatos: introducción tardía' },
                { aporte: 'Desarrollo y fijaciones', critica: 'Universalización excesiva' },
                { aporte: 'Inconsciente y defensas', critica: 'Subestimación del rol cultural' },
                { aporte: 'Tabúes y normas sociales', critica: 'Androcentrismo femenino' }
            ]
        };

        document.addEventListener('DOMContentLoaded', () => {
            const drivesChartCtx = document.getElementById('drivesChart').getContext('2d');
            new Chart(drivesChartCtx, {
                type: 'doughnut',
                data: {
                    labels: ['Eros', 'Thanatos'],
                    datasets: [{
                        label: 'Pulsiones',
                        data: [50, 50],
                        backgroundColor: ['#88a0a0', '#bdbdbd'], /* Muted teal and light gray */
                        borderColor: ['#f8f8f8'],
                        borderWidth: 3
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            position: 'bottom',
                            labels: {
                                color: '#555555'
                            }
                        },
                        tooltip: {
                            callbacks: {
                                label: function(context) {
                                    return context.label + ': Fuerza psíquica.';
                                }
                            }
                        }
                    }
                }
            });

            const stageButtons = document.querySelectorAll('.stage-button');
            const stageTitle = document.getElementById('stage-title');
            const stageDescription = document.getElementById('stage-description');
            const stageDetails = document.getElementById('stage-details');
            const initialContent = {
                title: 'Seleccione una etapa',
                description: 'Explore el desarrollo psicosexual.',
                details: ''
            };

            function updateStageContent(stageKey) {
                const stageData = appData.stages[stageKey] || initialContent;
                stageTitle.textContent = stageData.title;
                stageDescription.textContent = stageData.description;
                stageDetails.innerHTML = stageData.details;

                stageButtons.forEach(btn => {
                    btn.classList.toggle('active', btn.dataset.stage === stageKey);
                });
            }
            
            // Set first stage as active by default, and update its content
            const firstStageButton = document.querySelector('.stage-button');
            if (firstStageButton) {
                firstStageButton.classList.add('active');
                updateStageContent(firstStageButton.dataset.stage);
            } else {
                updateStageContent(''); // Fallback if no buttons
            }


            stageButtons.forEach(button => {
                button.addEventListener('click', () => {
                    updateStageContent(button.dataset.stage);
                });
            });

            const tabButtons = document.querySelectorAll('.tab-button');
            const tabContents = document.querySelectorAll('.tab-content');
            
            document.getElementById('tab-clinica').innerHTML = appData.tabs.clinica;
            document.getElementById('tab-legado').innerHTML = appData.tabs.legado;
            document.getElementById('tab-criticas').innerHTML = appData.tabs.criticas;

            function updateTabContent(activeTab) {
                tabContents.forEach(content => {
                    content.classList.toggle('hidden', content.id !== `tab-${activeTab}`);
                });
                 tabButtons.forEach(button => {
                    button.classList.toggle('active', button.dataset.tab === activeTab);
                });
            }

            tabButtons.forEach(button => {
                button.addEventListener('click', () => {
                   updateTabContent(button.dataset.tab);
                });
            });
            
            // Set first tab as active by default
            const firstTabButton = document.querySelector('.tab-button');
            if (firstTabButton) {
                firstTabButton.classList.add('active');
                updateTabContent(firstTabButton.dataset.tab);
            } else {
                updateTabContent('clinica'); // Default to 'clinica' if no buttons
            }

            const sintesisTableBody = document.getElementById('sintesis-table-body');
            appData.sintesis.forEach(item => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td class="px-5 py-3 whitespace-nowrap text-gray-800">${item.aporte}</td>
                    <td class="px-5 py-3 whitespace-nowrap text-gray-600">${item.critica}</td>
                `;
                sintesisTableBody.appendChild(row);
            });

            const navLinks = document.querySelectorAll('.nav-link');
            const sections = document.querySelectorAll('main section');
            
            window.addEventListener('scroll', () => {
                let current = '';
                sections.forEach(section => {
                    const sectionTop = section.offsetTop;
                    if(pageYOffset >= sectionTop - 70) { /* Adjusted offset for smaller header */
                        current = section.getAttribute('id');
                    }
                });

                navLinks.forEach(link => {
                    link.classList.remove('active');
                    if(link.getAttribute('href') === `#${current}`) {
                        link.classList.add('active');
                    }
                })
            });

        });
    </script>

</body>
</html>
