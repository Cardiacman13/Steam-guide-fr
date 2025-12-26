# Steam Linux post installation

Découvrez comment configurer Steam sur Linux après l’installation pour profiter au mieux de vos jeux. Ce guide vous propose des étapes simples et illustrées pour personnaliser votre expérience.

<br>

# Table des Matières

1. [Changer la Langue](#changer-la-langue)
3. [Ajout de Disque](#ajout-de-disque)
4. [Désactiver Remote Play](#désactiver-remote-play)
5. [Afficher les FPS](#afficher-les-fps)
6. [Trouver le chemin d'installation de vos jeux](#trouver-le-chemin-d-installation-de-vos-jeux)
7. [Astuce pour améliorer la vitesse de téléchargement](#astuce-pour-améliorer-la-vitesse-de-téléchargement)
8. [Problème de compatibilité](#problème-de-compatibilité)

<br>

## Changer la Langue

Changez la langue de l'interface Steam :

<p align="center">
  <img width="850" src="https://codeberg.org/Gaming-Linux-FR/steam-post-install/raw/branch/main/Steam%20langue.png" alt="langue">
</p>

<br>

## Ajout de disque

Ajoutez des emplacements de stockage pour vos jeux en configurant des dossiers supplémentaires de bibliothèque de jeux :

<p align="center">
  <img width="850" src="https://codeberg.org/Gaming-Linux-FR/steam-post-install/raw/branch/main/Steam%20ajout%20de%20disque.png" alt="ajout-disque">
</p>

**Astuce pour monter un disque secondaire :** Si vous rencontrez des difficultés pour monter vos Disques / SSDs secondaires au démarrage, consultez [ce guide](https://codeberg.org/Gaming-Linux-FR/guide-formater-monter).

**Astuce pour Flatpak :** Si vous utilisez Steam en version Flatpak, consultez [ce guide](https://codeberg.org/Gaming-Linux-FR/glf-astuces#acc%C3%A9der-%C3%A0-un-disque-secondaire-avec-une-application-flatpak) pour ajouter des disques secondaires.

<br>

## Désactiver remote play

Si vous n'utilisez pas la fonctionnalité Remote Play, qui permet de streamer des jeux sur d'autres appareils, vous pouvez facilement la désactiver pour éviter que le service ne tourne en tache de fond :

<p align="center">
  <img width="850" src="https://codeberg.org/Gaming-Linux-FR/steam-post-install/raw/branch/main/D%C3%A9sactiver%20remote%20play.png" alt="désactiver-remote-play">
</p>

## Afficher les FPS

Option pour afficher les fps en jeu, il existe d'autres solutions plus complètes mais passer par Steam reste le plus simple et surtout le plus stable.

<p align="center">
  <img width="850" src="https://codeberg.org/Gaming-Linux-FR/steam-post-install/raw/branch/main/steamfps.png" alt="steamfps">
</p>

## Trouver le chemin d'installation de vos jeux

Si par exemple vous voulez moder vos jeux, sur Linux les chemins d'installation de vos jeux ne sont pas les mêmes que sur Windows, mais pas de tracas, plutôt que de chercher faites clic droit sur le jeu, propriété et dans l'onglet `Fichiers Installés` vous pourrez cliquer sur `parcourir` et vous vous retrouvez directement dans le dossier d'installation du jeu.

<p align="center">
  <img width="850" src="https://codeberg.org/Gaming-Linux-FR/steam-post-install/raw/branch/main/steam-fichiers.png" alt="steam-fichiers">
</p>

## Astuce pour améliorer la vitesse de téléchargement

Si vous constatez que vos téléchargements sur Steam sont plus longs que ce que vous pouvez voir ailleurs, alors vous pouvez tenter de désactiver le HTTP2.

Pour cela, copiez collez les linges suivantes dans un terminal : 

Steam natif :

```
echo "@nClientDownloadEnableHTTP2PlatformLinux 0" >> ~/.steam/steam/steam_dev.cfg
echo "@fDownloadRateImprovementToAddAnotherConnection 1.0" >> ~/.steam/steam/steam_dev.cfg
```

Steam Flatpak :

```
echo "@nClientDownloadEnableHTTP2PlatformLinux 0" >> ~/.var/app/com.valvesoftware.Steam/.steam/steam/steam_dev.cfg
echo "@fDownloadRateImprovementToAddAnotherConnection 1.0" >> ~/.var/app/com.valvesoftware.Steam/.steam/steam/steam_dev.cfg
```

# Problème de compatibilité

Si et seulement si vous rencontrez des problèmes, comme par exemple la boutique qui affiche un écran noir ou l'imposibilité de cliquer sur certaines options, vous pouvez essayer de jouer avec ces 2 options encadrées :

<p align="center">
  <img width="850" src="https://codeberg.org/Gaming-Linux-FR/steam-post-install/raw/branch/main/steamcompat.png" alt="steam-fichiers">
</p>