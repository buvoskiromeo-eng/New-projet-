// Gestion de la navigation
document.querySelectorAll('.nav-btn').forEach(button => {
    button.addEventListener('click', function() {
        // Retirer la classe active de tous les boutons
        document.querySelectorAll('.nav-btn').forEach(btn => {
            btn.classList.remove('active');
        });
        
        // Ajouter la classe active au bouton cliqué
        this.classList.add('active');
        
        // Afficher la page correspondante
        const pageId = this.getAttribute('data-page');
        showPage(pageId);
    });
});

function showPage(pageId) {
    // Cacher toutes les pages
    document.querySelectorAll('.page').forEach(page => {
        page.classList.remove('active');
    });
    
    // Afficher la page demandée
    document.getElementById(pageId).classList.add('active');
}

// Gestion du formulaire de virement
document.querySelector('.transfer-form').addEventListener('submit', function(e) {
    e.preventDefault();
    
    const amount = document.getElementById('amount').value;
    const toAccount = document.getElementById('toAccount').value;
    
    if (!amount || !toAccount) {
        alert('Veuillez remplir tous les champs');
        return;
    }
    
    if (confirm(`Confirmez-vous le virement de ${amount}€ vers ${toAccount} ?`)) {
        alert('Virement effectué avec succès (démonstration)');
        this.reset();
    }
});

// Déconnexion
document.getElementById('logoutBtn').addEventListener('click', function() {
    if (confirm('Êtes-vous sûr de vouloir vous déconnecter ?')) {
        alert('Déconnexion réussie (démonstration)');
        // Redirection vers la page de login en réalité
    }
});

// Simulation de données
console.log('Application bancaire de démonstration chargée');
console.warn('ATTENTION : Ceci est une démonstration éducative, ne pas utiliser pour de vraies transactions');
