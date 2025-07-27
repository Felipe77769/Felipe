<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu App de Sustentabilidade</title>
    <link rel="stylesheet" href="src/css/style.css">
    <link rel="stylesheet" href="src/css/components.css">
</head>
<body>
    <header>
        <h1>Ideias para um Planeta Melhor</h1>
    </header>

    <main id="app-container">
        <section class="ideas-list">
            <h2>Dicas de Reciclagem</h2>
            <div id="recycling-ideas-cards">
                </div>
        </section>

        <section class="ecosystem-tips">
            <h2>Salvando Nosso Ecossistema</h2>
            <div id="ecosystem-tips-cards">
                </div>
        </section>

        <div class="icon-section">
            <svg width="50" height="50" viewBox="0 0 100 100">
                <use href="assets/icons/circle-icon.svg#S--circle" class="app-icon green-icon"></use>
            </svg>
            <p>Seu impacto ambiental:</p>
            <div id="impact-indicator"></div>
        </div>
    </main>

    <footer>
        <p>&copy; 2025 - App Sustentabilidade</p>
    </footer>

    <script src="src/js/app.js"></script>
    <script src="src/js/ui.js"></script>
    <script src="src/js/data.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f0f0f0;
    color: #333;
}

header {
    background-color: #4CAF50; /* Verde sustentável */
    color: white;
    padding: 1rem;
    text-align: center;
}

main {
    padding: 20px;
}

.ideas-list, .ecosystem-tips {
    background-color: white;
    margin-bottom: 20px;
    padding: 15px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

/* Estilo para o ícone SVG */
.app-icon {
    width: 30px;
    height: 30px;
    vertical-align: middle;
}

.green-icon {
    fill: #4CAF50; /* Preenche o SVG de verde */
}

/* Exemplo de classe para o SVG reutilizado */
.g--circle {
    /* Estilos específicos para o grupo g, se necessário */
}

.u--circle {
    /* Estilos específicos para o elemento use, se necessário */
    transition: transform 0.3s ease-in-out;
}
.u--circle:hover {
    transform: scale(1.1); /* Exemplo de animação ao passar o mouse */
}
const sustainabilityData = {
    recyclingIdeas: [
        { id: 'r1', title: 'Compostagem Doméstica', description: 'Transforme lixo orgânico em adubo rico.', icon: 'circle-icon.svg' },
        { id: 'r2', title: 'Separação de Plásticos', description: 'Identifique os tipos de plástico para descarte correto.', icon: 'circle-icon.svg' },
        // ... mais ideias
    ],
    ecosystemTips: [
        { id: 'e1', title: 'Plante uma Árvore', description: 'Ajuda na purificação do ar e biodiversidade.', icon: 'circle-icon.svg' },
        { id: 'e2', title: 'Economize Água', description: 'Pequenas mudanças fazem grande diferença no consumo.', icon: 'circle-icon.svg' },
        // ... mais dicas
    ]
};
// Função para criar um card de ideia/dica
function createIdeaCard(idea) {
    const card = document.createElement('div');
    card.className = 'idea-card'; // Classe CSS para o estilo do card
    card.innerHTML = `
        <h3>${idea.title}</h3>
        <p>${idea.description}</p>
        <svg width="30" height="30" viewBox="0 0 100 100" class="app-icon">
             <use href="assets/icons/${idea.icon}#S--circle" class="green-icon"></use>
        </svg>
        <button class="learn-more-btn">Saiba Mais</button>
    `;
    return card;
}

// Função para renderizar as ideias em um contêiner
function renderIdeas(containerId, ideas) {
    const container = document.getElementById(containerId);
    if (container) {
        container.innerHTML = ''; // Limpa o conteúdo existente
        ideas.forEach(idea => {
            container.appendChild(createIdeaCard(idea));
        });
    }
}
// Importa os dados e funções de UI (em um projeto real, usaria módulos ES6 ou CommonJS)
// Por simplicidade aqui, assumimos que data.js e ui.js já estão carregados
document.addEventListener('DOMContentLoaded', () => {
    // Renderiza as ideias de reciclagem
    renderIdeas('recycling-ideas-cards', sustainabilityData.recyclingIdeas);

    // Renderiza as dicas de ecossistema
    renderIdeas('ecosystem-tips-cards', sustainabilityData.ecosystemTips);

    // Adiciona interatividade, como cliques em botões
    document.querySelectorAll('.learn-more-btn').forEach(button => {
        button.addEventListener('click', (event) => {
            const cardTitle = event.target.closest('.idea-card').querySelector('h3').textContent;
            alert(`Você clicou em "Saiba Mais" para: ${cardTitle}`);
            // Aqui você poderia redirecionar para uma página de detalhes ou mostrar um modal
        });
    });

    // Atualiza o indicador de impacto (apenas um exemplo simples)
    const impactIndicator = document.getElementById('impact-indicator');
    if (impactIndicator) {
        impactIndicator.textContent = 'Bom! Continue reciclando!';
    }
});
<svg width="100" height="100" viewBox="0 0 100 100"
     xmlns="http://www.w3.org/2000/svg"
     xmlns:xlink="http://www.w3.org/1999/xlink"> <defs>
    <circle id="S--circle" cx="50" cy="50" r="40" fill="#add8e6" stroke="#2196F3" stroke-width="2"/>
    </defs>

  </svg>

