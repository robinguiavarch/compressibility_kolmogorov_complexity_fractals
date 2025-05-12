🌳 La Complexité comme Feature pour la Segmentation d’Arbres Fractals
Projet réalisé par Luca Hachani & Robin Guiavarch - Mastère IA703, Décembre 2024

Ce projet explore les propriétés des arbres fractals de Mandelbrot-Vicsek, leur encodage par marches de Harris, leur compression spécifique, et enfin leur segmentation à partir des distances NCD.
Notre objectif est d'illustrer comment la complexité d'un objet fractal peut être utilisée comme feature robuste pour la classification et le clustering.

🧩 À savoir :

Tout le projet est implémenté dans le notebook arbres_fractales_hachani_guiavarch_code.ipynb.

Il suffit de suivre le notebook pas à pas pour retrouver toutes les explications, implémentations et résultats.

📂 Structure du projet
1. Arbres fractals de Mandelbrot-Vicsek : Construction et 1er Encodage
Définition d'une fractale : Application répétée d'une transformation contractante.

Pré-fractale : Approximations finies de fractales (étapes de construction).

Arbres fractals : Construction par division récursive d'un lien en plusieurs.

Premier encodage naïf : Basé sur la structure entière de l'arbre, jugé lourd et inefficace.

2. Encodage efficace avec les marches de Harris
Définition : Suivre la génération des nœuds par parcours en profondeur (up : 1, down : 0).

Avantages : Encodage léger et révélateur des motifs fractals.

Exemples : Marche de Harris d’arbres simples et interprétation intuitive des motifs.

3. Approche de la Complexité
Marche de Harris spécifique aux arbres de Mandelbrot-Vicsek : Génération à chaque itération.

Programmation de la marche : Simulation d’une machine de Turing pour encoder la croissance de l’arbre.

Complexité : Approximée par la longueur minimale du programme nécessaire à générer la marche.

4. Compression spécifique des marches de Harris
Création d'un compresseur dédié :

Exploitation des motifs et duplicats miroirs.

Pipeline simple mais adapté aux structures fractales.

Comparaison avec compresseurs classiques (zip, gzip, bzip2) :

Performances compétitives.

Tests de qualité (idempotence, symétrie, détection de régularités, etc.).

Bzip2 validé pour les expériences finales.

5. Distance NCD et Clustering de Fractales
Première tentative : Clustering sur des arbres immatures (k faible).

Résultats moyens avec notre compresseur.

Meilleure cohérence avec bzip2.

Maturité des arbres : Définie à partir du taux de compression (coude observé à k = 4).

Seconde tentative : Clustering sur des arbres matures (k élevé).

Segmentation efficace en fonction de la multiplicité m.

Limites du compresseur bzip2 avec signaux très volumineux (problèmes de concaténation au-delà de 10 millions de bits).

6. Conclusion
Complexité des arbres fractals : Reliée à la brièveté du programme générant leur marche de Harris.

Segmentation réussie pour arbres de faible multiplicité et maturité élevée.

Limites : Liées à la scalabilité des compresseurs standards pour très gros signaux.

📝 Comment utiliser ce projet
Ouvrir le fichier arbres_fractales_hachani_guiavarch_code.ipynb.

Suivre le notebook dans l'ordre :

Chaque grande section du rapport est directement illustrée et expérimentée dans le code.

Modifier les paramètres m (multiplicité) et k (nombre d'itérations) pour tester d'autres arbres fractals.

Observer les résultats de compression et de clustering.

📚 Références
The Similarity Metric, Ming Li et al., 2004

Directed Recursion Models for Fractal Growth, Mandelbrot & Vicsek, 1989
