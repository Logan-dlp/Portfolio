<script>
    import '../../assets/projects/ProjectDetail.css'
</script>

<template>
    <div class="project-container">
        <div class="project-container-info">
                <h1>CelShading for Unity6+</h1>
                <div class="project-container-button">
                    <a class="git" href="https://github.com/Logan-dlp/Cel-Shading" target="_blank">
                        <button>Github</button>
                    </a>
                    <a class="download" href="https://github.com/Logan-dlp/Cel-Shading/releases" target="_blank">
                        <button>Téléchargement</button>
                    </a>
                </div>
            </div>
        <div class="project-container-element">
            <iframe class="project-container-video" src="https://www.youtube.com/embed/KIB68oq7cV8?si=Nsn2D-Iz5e8pBoaE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
        </div>
        <div class="project-info">
            <h3>Introduction :</h3>
            <p>Avec les changements de Unity 6 et leurs nouvelles gestions des lumières nous avons eu, mon équipe et moi une problématique avec les packages de CelShading déjà fait.<br>J'ai donc décidé de le réécrire, en le rendant le plus modulable possible et de faire en sorte qu'il réponde à nos besoins.</p>
            <h3>Mes tâches et mon impact :</h3>
            <p>J'ai dû écrire la gestion des lumières dans un fichier Shader natif en HLSL, pour ensuite pouvoir l'adapter dans un Shader Graph pour être plus facilement intégrable et modulaire.</p>
            <h3>Équipe :</h3>
            <div class="li-container">
                <div>
                    <li>Logan Delachapelle</li>
                </div>
            </div>
            <h3>Moteur de jeu, outils et langue :</h3>
            <div class="li-container">
                <div>
                    <li>HLSL</li>
                    <li>Unity 6</li>
                    <li>Fork</li>
                    <li>Jetbrain Rider</li>
                </div>
            </div>
        </div>
    </div>
</template>