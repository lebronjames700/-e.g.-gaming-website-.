# -e.g.-gaming-website-.const games = [
    { name: "Fortnite", image: "https://via.placeholder.com/200", link: "#" },
    { name: "Minecraft", image: "https://via.placeholder.com/200", link: "#" },
    { name: "Call of Duty", image: "https://via.placeholder.com/200", link: "#" },
    { name: "GTA V", image: "https://via.placeholder.com/200", link: "#" },
    { name: "League of Legends", image: "https://via.placeholder.com/200", link: "#" },
    { name: "Happy Wheels", image: "https://totaljerkface.com/happy_wheels.tjf", link: "https://totaljerkface.com/happy_wheels.tjf" },
    { name: "SWAT 4", image: "https://via.placeholder.com/200", link: "https://www.gog.com/game/swat_4_gold_edition" },
    { name: "Tomb of the Mask", image: "https://via.placeholder.com/200", link: "https://tomb-of-the-mask.com/" },
    { name: "Drift Hunters", image: "https://via.placeholder.com/200", link: "https://drift-hunters.io/" }
];

const gameList = document.getElementById("game-list");

// Function to display games
function displayGames(filter = "") {
    gameList.innerHTML = "";
    games.filter(game => game.name.toLowerCase().includes(filter.toLowerCase()))
         .forEach(game => {
        const gameCard = document.createElement("div");
        gameCard.classList.add("game-card");
        gameCard.innerHTML = `
            <img src="${game.image}" alt="${game.name}">
            <h3>${game.name}</h3>
            <a href="${game.link}" target="_blank">Play Now</a>
        `;
        gameList.appendChild(gameCard);
    });
}

// Search functionality
document.getElementById("search-bar").addEventListener("input", (e) => {
    displayGames(e.target.value);
});

// Load games on page load
displayGames();
