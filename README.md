# 🎮 Steam Linux : Optimisation Post-Installation

Apprenez à configurer et optimiser Steam sur Linux pour une expérience de jeu fluide. Ce guide couvre les réglages essentiels, de la gestion des disques à la résolution des problèmes fréquents.

## 📌 Table des Matières

1. [🌍 Changer la Langue](https://www.google.com/search?q=%23changer-la-langue)
2. [💾 Ajout de Disque & Stockage](https://www.google.com/search?q=%23ajout-de-disque)
3. [📡 Désactiver Remote Play](https://www.google.com/search?q=%23d%C3%A9sactiver-remote-play)
4. [📊 Afficher les FPS](https://www.google.com/search?q=%23afficher-les-fps)
5. [📂 Trouver le chemin d'installation](https://www.google.com/search?q=%23trouver-le-chemin-d-installation-de-vos-jeux)
6. [🚀 Booster la vitesse de téléchargement](https://www.google.com/search?q=%23astuce-pour-am%C3%A9liorer-la-vitesse-de-t%C3%A9l%C3%A9chargement)
7. [🛠️ Problèmes d'affichage et compatibilité](https://www.google.com/search?q=%23probl%C3%A8me-de-compatibilit%C3%A9)
8. [♻️ Réparation et Nettoyage](https://www.google.com/search?q=%23r%C3%A9paration-et-nettoyage)

---

## 🌍 Changer la Langue

Pour adapter l'interface de Steam à votre préférence :

![langue](steam-post-install/langue.png)

---

## 💾 Ajout de disque

Gérez vos bibliothèques de jeux sur plusieurs disques (SSD, HDD secondaire) :

![ssd](steam-post-install/ssd.png)

> 💡 **Disque non reconnu ?**
> * **Montage automatique :** Consultez notre [guide pour formater et monter un disque](https://codeberg.org/Gaming-Linux-FR/guide-formater-monter).
> * **Version Flatpak :** Si Steam ne voit pas vos dossiers, utilisez [Flatseal](https://flathub.org/apps/com.github.tchx84.Flatseal) pour autoriser l'accès aux disques externes.
> 
> 

---

## 📡 Désactiver Remote Play

Si vous ne jouez pas en streaming vers d'autres appareils, désactivez cette option pour économiser des ressources en arrière-plan :

![remote](steam-post-install/remote.png)

---

## 📊 Afficher les FPS

Pour surveiller vos performances sans outils externes complexes :

![hud](steam-post-install/hud.png)

---

## 📂 Trouver le chemin d'installation de vos jeux

Sur Linux, les fichiers sont souvent cachés dans des dossiers complexes. Pour y accéder facilement (modding, sauvegardes manuelles) :
**Clic droit sur le jeu > Propriétés > Fichiers installés > Parcourir.**

![fichiers](steam-post-install/fichier.png)

---

## 🚀 Astuce pour améliorer la vitesse de téléchargement

Si votre fibre semble bridée sur Steam Linux, désactiver le protocole HTTP2 peut stabiliser et accélérer le débit.

Ouvrez un terminal et copiez les lignes correspondant à votre installation :

**Steam Natif (.deb, .rpm, arch) :**

```bash
echo "@nClientDownloadEnableHTTP2PlatformLinux 0" >> ~/.steam/steam/steam_dev.cfg
echo "@fDownloadRateImprovementToAddAnotherConnection 1.0" >> ~/.steam/steam/steam_dev.cfg

```

**Steam Flatpak :**

```bash
echo "@nClientDownloadEnableHTTP2PlatformLinux 0" >> ~/.var/app/com.valvesoftware.Steam/.steam/steam/steam_dev.cfg
echo "@fDownloadRateImprovementToAddAnotherConnection 1.0" >> ~/.var/app/com.valvesoftware.Steam/.steam/steam/steam_dev.cfg

```

---

## 🛠️ Problème de compatibilité (Interface)

En cas d'écran noir dans la boutique ou de bugs graphiques de l'interface Steam, modifiez ces options dans les paramètres **Interface** :

![compat](steam-post-install/compat.png)

---

## ♻️ Réparation et Nettoyage <a name="réparation-et-nettoyage"></a>

Parfois, un jeu refuse de se lancer à cause d'un "préfixe" (le dossier Windows virtuel créé par Proton) corrompu. Voici comment faire le ménage.

### 1. Supprimer le préfixe d'un jeu

Si un jeu bugue après une mise à jour ou un changement de version Proton, supprimer son dossier `pfx` permet de le réinitialiser proprement sans supprimer le jeu.

* **Chemin (Natif) :** `~/.steam/steam/steamapps/compatdata/[ID_DU_JEU]/pfx`
* **Chemin (Flatpak) :** `~/.var/app/com.valvesoftware.Steam/.steam/steam/steamapps/compatdata/[ID_DU_JEU]/pfx`

> ⚠️ **Attention :** Si le jeu n'utilise pas le *Steam Cloud*, vos sauvegardes locales peuvent se trouver dans ce dossier. Faites une copie avant !

### 2. Vider le cache des Shaders

Si vous avez des micro-saccades (stuttering), vous pouvez supprimer le cache de shaders pour forcer Steam à les recalculer.

* Dossier : `.../steamapps/shadercache/`
