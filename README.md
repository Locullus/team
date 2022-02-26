const app = {
    init: function()
    {
        apiBaseUrl = 'http://localhost:5000',
        console.log("app.init()");
        app.addAllEventListeners();
    },
    addAllEventListeners: function()
    {
        // récupération de tous les boutons categories et ajout de capteurs
        document.querySelectorAll("#category .categories").forEach(category => category.addEventListener("click", app.handleClickCategoryBtn))
    },
    handleClickCategoryBtn: function(event)
    {
        // gestion de la classe active sur le bouton cliqué
        const currentActiveBtn = document.querySelector(".active");
        if (currentActiveBtn)
        {
            currentActiveBtn.classList.remove("active");
        }
        event.currentTarget.classList.add("active");

        // fetch des données de la catégorie sélectionnée
        app.fetchCategory(event);
    },
    fetchCategory: async function(event)
    {
        const $category = event.target.innerHTML;
        console.log($category);
        let fetchOptions = {
            method: 'GET',
            mode: 'cors',
            cache: 'no-cache'
        };
        $response = await fetch('http://localhost:5000/api/' + $category, fetchOptions);
        $data = await $response.json();
        console.log("le résultat renvoyé par l'api est " + $data);
    }
}
document.addEventListener("DOMContentLoaded", app.init);

// au clic sur une catégorie on fait un fetch pour récupérer les events de cette catégorie

// TODO: récupérer le bouton avec la classe active pour passer la catégorie au controller api (si null => default)


