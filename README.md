<!-- Formulaire d'inscription WhatsApp -->
<div style="text-align: center; margin: 20px;">
  <h2>Inscription</h2>
  
  <form id="signupForm">
    <div style="margin-bottom: 10px;">
      <label for="fullName">Nom et Prénom :</label><br>
      <input type="text" id="fullName" placeholder="Entrez votre nom" required style="padding: 8px; width: 80%;">
    </div>

    <div style="margin-bottom: 15px;">
      <label for="phone">Numéro de téléphone :</label><br>
      <input type="tel" id="phone" placeholder="Ex: 37000000" required style="padding: 8px; width: 80%;">
    </div>

    <button type="button" onclick="voyeSouWhatsApp()" style="padding: 10px 20px; background-color: #25D366; color: white; border: none; border-radius: 5px; font-weight: bold;">
      Envoyer
    </button>
  </form>
</div>

<script>
  function voyeSouWhatsApp() {
    // ⚠️ Remplacez le numéro ci-dessous par votre numéro WhatsApp (ex: 50937000000)
    var monNumero = "50933343511"; 

    var non = document.getElementById("fullName").value.trim();
    var telefon = document.getElementById("phone").value.trim();

    if (non === "" || telefon === "") {
      alert("Veuillez remplir tous les champs !");
      return;
    }

    var message = "Bonjour ! Je souhaite m'inscrire.%0A%0A" +
                  "*Nom :* " + encodeURIComponent(non) + "%0A" +
                  "*Téléphone :* " + encodeURIComponent(telefon);

    var url = "https://wa.me/" + monNumero + "?text=" + message;
    window.open(url, '_blank');
  }
</script>
