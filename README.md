<!DOCTYPE html>
<html lang="fr">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pauline Chauvet - CV</title>
  <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Montserrat&display=swap">
  <style>
    body {
      font-family: 'Montserrat', sans-serif;
      margin: 0;
      padding: 0;
      background-color: #95a595; /* Vert chaud */
      color: #333;
    }

    header {
      background-color: #fff; /* Blanc */
      color: #333;
      text-align: left;
      padding: 1em;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }

    header img {
      max-width: 100px;
      height: auto;
    }

    header h1 {
      display: inline-block;
      margin-left: 20px;
      color: #758675; /* Vert chaud foncé */
    }

    section {
      max-width: 1000px;
      margin: 20px auto;
      padding: 20px;
      background-color: #fff;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      overflow: hidden; /* Pour masquer le contenu au départ */
      transition: max-height 0.5s ease-out; /* Animation de transition */
      margin-bottom: 20px;
			border-radius: 10px; /* Coins arrondis */
    }

    section.collapsed {
      max-height: 40px; /* Réduire la hauteur lorsqu'il est plié */
      padding-bottom: 0 20px; /* Supprimer l'espacement lorsque replié */
    }

    h1, h2 {
      color: #758675; /* Vert chaud foncé */
    }

    h2 {
      border-bottom: 2px solid #336633; /* Vert foncé */
      padding-bottom: 5px;
      margin-bottom: 20px;
      cursor: pointer; /* Curseur indiquant que le titre est cliquable */
    }

    h2.collapsed::after {
      content: "+"; /* Symbole "+" pour indiquer que la section est repliée */
      float: right;
    }
		
		h3 {
      margin-top: 10px;
    }

    ul {
      list-style-type: none;
      padding: 0;
    }

    li {
      margin-bottom: 10px;
    }

    .highlight {
      color: #f5bb00;
    }

    .divider {
      border-top: 3px solid #b3b191; /* Ligne de séparation */
      max-width: 950px;
      margin: 20px auto;
      padding: 10px;
    }

    .footer {
      text-align: right;
      margin-top: 20px;
			margin-right: 40px;
    }
		
/* Personnalisation des points -ligne de temps- dans la section experience professionnelle */
		
		.timeline-dot {
			position: relative;
			height: 15px; /* Ajustez la taille du point */
			width: 15px; /* Ajustez la taille du point */
			background-color: #b3b191; /* Couleur du point */
			border-radius: 50%;
			margin-top: 3px;
			margin-bottom: 3px;
			align-items: center; /* Centrer la date */
		}

		.timeline-dot::before {
			content: attr(data-date);
			position: relative;
			font-size: 12px; /* Ajustez la taille de la date */
			color: #b3b191; /* Couleur de la date */
			white-space: nowrap;
			margin-left: 20px;
		}
		
/* Personnalisation du format des outils dans la section de compétence en 3 colonnes suivant le niveau de compétence avec une barre progressive pour marquer visuellement le niveau */
		
		.tools {
      margin-top: 20px;
    }

    .tool-category {
      margin-top: 10px;
      margin-bottom: 20px;
    }
		
		.tool-info {
      margin-left: 10px;
      font-size: 14px;
      color: #666; /* Couleur du texte pour les informations sur l'outil */
    }

    .tool-item {
      margin-bottom: 10px;
    }

    .progress-bar {
      background-color: #d9e7da; /* Couleur de fond de la barre de progression */
      height: 20px;
      border-radius: 5px;
      margin-bottom: 10px;
    }

    .fully-mastered {
      background-color: #b3b191; /* Couleur de la barre de progression pour les outils maîtrisés complètement */
			width: 190px; /* Ajustez cette valeur en fonction du niveau de maîtrise */
    }

    .partially-mastered {
      background-color: #b3b191; /* Couleur de la barre de progression pour les outils utilisés partiellement */
      width: 100px; /* Ajustez cette valeur en fonction du niveau de maîtrise */
    }
		
		.low-mastered {
      background-color: #b3b191; /* Couleur de la barre de progression pour les outils utilisés partiellement */
      width: 50px; /* Ajustez cette valeur en fonction du niveau de maîtrise */
    }
		
		.tool-subcategory h3 {
      margin-bottom: 10px;
    }

    .tool-subcategories {
      display: flex;
      flex-wrap: wrap; /* Permet le passage à la ligne lorsque l'espace est insuffisant */
      justify-content: space-evenly; /* Répartit les sous-catégories sur la ligne */
      margin-top: 10px;
    }

    .tool-subcategory {
      flex: 0 0 31%; /* Réduit la largeur pour s'assurer que deux sous-catégories tiennent sur une ligne */
      margin-bottom: 20px;
      border-right: 2px solid #b3b191; /* Ligne verticale entre les sous-catégories */
      padding-right: 4px; /* Espacement à droite de la ligne */
			padding-left: 4px; /* Espacement à droite de la ligne */
    }
		
		.tool-subcategory:last-child {
      border-right: none; /* Supprime la ligne verticale pour la dernière sous-catégorie */
      padding-right: 0; /* Supprime l'espacement à droite de la dernière sous-catégorie */
    }
		
		.tool-subcategory:last-child .tool-bar {
      margin-bottom: 0;
    }

    .tool-bar {
      display: flex;
      align-items: center;
      margin-bottom: 15px;
    }
		
/* Ajout d'icones pour les sections langues et autres activités */
		
		.flag {
      width: auto; /* Ajustez la taille des drapeaux */
      height: 15px;
			vertical-align:sub
      margin-left: 5px;
			margin-right: 5px;
    }
		.Icon {
      width: auto; /* Ajustez la taille des icones de centre d'intérêt */
      height: 40px;
			margin-left: 5px;
			margin-right: 5px;
    }
		.conteneur {
      display: flex; /* Centrez les icones dans la section */
			justify-content: center;
			text-align: center;
    }
  </style>

	<script>
    document.addEventListener("DOMContentLoaded", function () {
      // Ajoutez un gestionnaire d'événement à tous les titres de section h2
      var sectionTitles = document.querySelectorAll('h2');
      sectionTitles.forEach(function (title) {
        title.addEventListener('click', function () {
          // Basculez la classe collapsed pour cacher ou afficher le contenu
          this.parentNode.classList.toggle('collapsed');
        });
      });
    });
		
  </script>
	
	
</head>

<body>

  <header>
    <img src="https://img.genial.ly/5def6a572448c50fd41fce03/39430952-d170-45f3-bb92-03b4465ce214.png" alt=" " />
    <h1>Pauline Chauvet - FAIR Data Manager</h1>
		<li style="margin-left: 70px;"><a href="https://orcid.org/0000-0002-6989-9072"> ORCID,</a> <a href="https://www.linkedin.com/in/pauline-chauvet-3ba816248/"> LinkedIn,</a><a href="https://github.com/pauline-chauvet"> Github</a></li>
  </header>
	
		
  <section class="collapsed">
  <h2>Expérience Professionnelle</h2>
    <ul>
		<li>
			
			<li><div class="timeline-dot" data-date="Mars 2023-Aujourd'hui"></div></div><h3 style="margin-left: 70px;">Ingénieure de Recherche. Chargée du Projet de Plan de Gestion de Données</h3></li>
			<li style="margin-left: 70px;"><strong>Institut Universitaire Européen de la Mer (Brest, France) (Mars 2023-aujourd'hui)</strong></li>
        <ul style="margin-left: 70px;">
          <li>Récupération et synthèse des pratiques en gestion de données des différentes unités mixtes de recherche de l'institut</li>
					<li>Aide à la rédaction de plans de gestion de données.</li>
					<li>Conseils sur les bonnes pratiques en gestion de différents types de produits de la recherche.</li>
          <li>Utilisation des principes FAIR et CARE pour assurer la qualité des données.</li>
          <li>Conception d'une application pour faciliter la rédaction de PGD.</li>
          <li>Création et mise à jour des pages et articles du site web (Wordpress)</li>
          <li>Communication d'évènements, organisation de réunions, production de documents de synthèse.</li>
          <li>Collaboration avec des informaticiens</li>
					<li>Conception d'un outil "pilote" de visualisation de l'écosystème des entrepôts et catalogues de données.</li>
        </ul>
				<li style="margin-left: 70px;"> 
					<strong>Exemple de production:</strong><a href="https://orcid.org/0000-0002-6989-9072#works"> Accès aux publications</a> </li>
      </li>
      <li>
			<li><div class="timeline-dot" data-date="Sept 2020-Fév 2023"></div><h3 style="margin-left: 70px;">Conseillère scientifique.</h3></li>
			<li style="margin-left: 70px;"><strong>Observatoire Global du Saint-Laurent (Rimouski, Qc, Canada) (Sept 2020-Fév 2023)</strong></li>
        <ul style="margin-left: 70px;">
					<li><strong>OGSL</strong></li>
					<li>Création et/ou correction de fiche de métadonnées (adaptation pour une visualisation sur CKAN).</li>
					<li>Création d'identifiants persistants (DOI via DataCite).</li>
					<li>Standardisation de données de biodiversité et de tracking au format DarwinCore (R).</li>
					<li>Intégration de données de tracking dans OBIS (via l'IPT-GBIF).</li>
					<li>Formation du personnel de recherche et des étudiants sur OBIS et DarwinCore.</li>
					<li>Traduction de document de formation sur OBIS et DarwinCore anglais->français.</li>
					<li>Développement d'une application de visualisation des espèces du Saint-Laurent maritime (RShiny).</li>
					<li>Aide à la conception de jeu de données complexe sur un projet de recherche de microalgues toxiques (DOI, métadonnées, ERDDAP, application web de visualisation).</li>
					<li>Sensibilisation sur les mesures particulières à appliquer aux données des communautés autochtones.</li>
					<li><strong>CIOOS-SIOOC</strong></li>
					<li>Co-Chair du conseil scientifique du Système Intégré d'Observation des Océans du Canada (CIOOS-SIOOC)</li>
					<li>Coordinatrice du groupe de travail sur les variables océaniques essentielles</li>
					<li>Participation aux groupes de travail sur les métadonnées, les plans de gestion de données, les données de modèles, données de biodiversité et data stewardship</li>
					<li>Expérience au sein de l'écosystème d'entrepôt et de catalogue de données de recherche Canadien.</li>
					<li>Travail bilingue (Français et Anglais) avec des partenaires anglophones et francophones.</li>
					
					
        </ul>
				<li style="margin-left: 70px;"> 
					<strong>Exemple de production:</strong>
						<li style="margin-left: 80px;"><a href="https://explo-especes.ogsl.ca/"> Application d'exploration d'espèce du Saint-Laurent maritime en RShiny</a></li>
						<li style="margin-left: 80px;"><a href="https://github.com/ocean-tracking-network/obis-workshop/tree/master"> Matériel du webinaire: formation sur OBIS en collaboration avec Ocean Tracking Network</a></li>
						<li style="margin-left: 80px;"><a href="https://commons.datacite.org/doi.org/10.26071/ogsl-bw9a-0y85"> DOIsation de l'application web du projet de recherche: modèle de prévision du risque de floraison de l’algue toxique Alexandrium catenella</a></li>
						</li>
      </li>
			<li>
			<li><div class="timeline-dot" data-date="Aout 2019-Sept 2020"></div><h3 style="margin-left: 70px;">Postdoctorante. Modélisation de la dynamique spatiale des herbiers à zostère de l'estuaire et du Golfe du Saint-Laurent</h3></li>
			<li style="margin-left: 70px;"><strong>Université du Québec à Rimouski (Aout 2019-Sept 2020)</strong></li>
			  <ul style="margin-left: 70px;">
          <li>Définition du modèle conceptuel</li>
          <li>Acquisition des données de température, glace, courant, vent et topo-bathymétrie ainsi que la distribution des herbiers a zostère de la région de Manicouagan</li>
          <li>Construction d’un modèle de distribution d’espèce (sdm, langage R)</li>
          <li>Utilisation du logiciel R pour l'analyse des données.</li>
          <li>Utilisation de python dans ArcGIS pour automatiser la création de noms d'écosystème dans la base de données de biodiversité des écosystèmes du Saint-Laurent maritime.</li>
        </ul>
				<li style="margin-left: 70px;"> 
					<strong>Exemple de production:</strong><a href="https://sigec.uqar.ca/portal/carto/view?page=mapGallery&mapid=722a2b0e-9068-4ca3-bfbb-e6bcfe53c5be"> Carte des écosystèmes littoraux du golfe et de l'estuaire de Saint-Laurent</a> </li>
      </li>
			<li>
			<li><div class="timeline-dot" data-date="Jan 2019-Juin 2019"></div><h3 style="margin-left: 70px;">Ingénieure de recherche. Analyse globale du recrutement dans l’océan profond au large de l'ile de Vancouver (projet INDEEP).</h3></li>
			<li style="margin-left: 70px;"><strong>Université de Dalhousie (N-E, Canada) (Jan 2019-Juin 2019)</strong></li>
			  <ul style="margin-left: 70px;">
          <li>Tri, identification, analyse et discussion des résultats provenant des substrats de recrutement déposés entre 400 et 2600 m de profondeur à l’observatoire NEPTUNE Canada.</li>
				</ul>
      </li>
			<li>
			<li><div class="timeline-dot" data-date="Sept 2016-Sept 2018"></div><h3 style="margin-left: 70px;">Assistante d'enseignement à la recherche. Enseignement de biologie animale, statistiques, sciences et société</h3></li>
			<li style="margin-left: 70px;"><strong>Université de Bretagne Occidentale (Sept 2016-Sept 2018)</strong></li>
			  <ul style="margin-left: 70px;">
          <li>Travaux pratiques en biologie animale (niveau L1): préparation de salle, présentation du TP et encadrement à la dissection.</li>
          <li>Travaux dirigés et pratiques en statistiques (niveau M1): création du cours selon le plan donné, présentation du cours puis mise en pratique avec le logiciel R.</li>
          <li>Activité sciences et société (niveau M1): présentation d'un sujet puis encadrement d'un groupe pluridisciplinaire.</li>
         </ul>
      </li>
			<li>
			<li><div class="timeline-dot" data-date="Janv 2015-Juil 2016"></div><h3 style="margin-left: 70px;">Médiatrice scientifique</h3></li>
			<li style="margin-left: 70px;"><strong>Océanopolis (Brest, France) (Janv 2015-Juil 2016)</strong></li>
				<ul style="margin-left: 70px;">
          <li>Animation de visite guidée (niveau grand public maternel à sénior): biologie, océanographie, géologie et protection de l'environnement sur trois pavillons (tempéré, polaire et tropical)</li>
        </ul>
      </li>
			<li>
			<li><div class="timeline-dot" data-date="Aout 2014-Déc 2014"></div><h3 style="margin-left: 70px;">Ingénieure d'étude. Inventaire de la mégafaune épibenthique des canyons du Golfe de Gascogne</h3></li>
			<li style="margin-left: 70px;"><strong>Ifremer (Brest, France)(Aout 2014-Dec 2014)</strong></li>
				<ul style="margin-left: 70px;">
          <li>Comptage, identification et cartographie des individus, substrats et particularités topographiques observés sur des photos issues de transects-caméra tractée</li>
        </ul>
				<li style="margin-left: 70px;"> 
					<strong>Exemple de production:</strong><a href="https://archimer.ifremer.fr/doc/00416/52777/53656.pdf"> Contributions au Référentiel National des Habitats Benthiques de la Région Atlantique - Identification et Classification des Habitats Profonds</a> </li>
      </li>
		</div>
    </ul>
  </section>
	
  <div class="divider"></div>

  <section class="collapsed">
    <h2>Formation académique</h2>
    <ul>
      <li>
			<li><div class="timeline-dot" data-date="Oct 2015-Déc 2018"></div><h3 style="margin-left: 70px;">Doctorat en écologie marine</h3></li>
			<li style="margin-left: 70px;"><strong>Ecole Doctoral des Sciences de la Mer et du Littoral (Université de Bretagne Occidentale)</strong></li>
			<li style="margin-left: 70px;"><strong>Institut Universitaire Européen de la Mer,Ifremer (Brest, France) et Université de Dakhousie (Halifax, N-E, Canada) (Oct 2015-Déc 2018)</strong></li>
        <ul style="margin-left: 70px;">
          <li>Dynamique temporelle et environnementale de la mégafaune profonde du Canyon de Barkley en utilisant les données produites par l'Observatoire Ocean Network Canada.</li>
          <li> <a href="https://theses.hal.science/tel-02139444"> Accès au mémoire de thèse</a> </li>
					<li> <a href="https://orcid.org/0000-0002-6989-9072#works"> Accès aux publications</a> </li>
        </ul>
      </li>
			<li>
			<li><div class="timeline-dot" data-date="Sept 2012-Aout 2014"></div><h3 style="margin-left: 70px;">Master en écologie marine</h3></li>
			<li style="margin-left: 70px;"><strong>Institut Universitaire Européen de la Mer(Sept 2012-Aout 2014)</strong></li>
        <ul style="margin-left: 70px;">
          <li>Stage de 1ère année: Distribution et diversité des habitats benthiques profonds associés au Golfe de Gascogne, Ifremer (Brest, France)</li>
          <li>Stage de 2ème année: Variabilité temporelle de la mégafaune épibenthique vivant dans un canyon: influence des paramètres physico-chimiques et hydrographiques, Ifremer (Brest, France) et Université de Dalhousie (N-E, Canada)</li>
        </ul>
      </li>
			<li>
			<li><div class="timeline-dot" data-date="Sept 2009-Aout 2011"></div><h3 style="margin-left: 70px;">Licence en biologie</h3></li>
			<li style="margin-left: 70px;"><strong>Université de Bretagne Occidentale(Sept 2009-Aout 2011)</strong></li>
      </li>
		 </ul>
		 <h2>Autre formations</h2>
		 <ul>
      <li>
			<li><div class="timeline-dot" data-date="Fév 2024"></div><h3 style="margin-left: 70px;"><a href="https://atelier-rgpd.cnil.fr/">L'atelier RGPD</a></h3></li>
			<li style="margin-left: 70px;"><strong>CNIL</strong></li>
			<li style="margin-left: 70px;">MOOC, formation en ligne, 4 modules de 5 heures avec attestations de suivi.</li>
      </li>
			<li>
			<li><div class="timeline-dot" data-date="Janv 2024"></div><h3 style="margin-left: 70px;"><a href="https://www.fun-mooc.fr/fr/cours/recherche-reproductible-principes-methodologiques-pour-une-science-transparente/">Recherche reproductible : principes méthodologiques pour une science transparente</a></h3></li>
			<li style="margin-left: 70px;"><strong>Inria</strong></li>
			<li style="margin-left: 70px;">MOOC, formation en ligne, 24 heures.</li>
      </li>
			<li>
			<li><div class="timeline-dot" data-date="Janv 2022"></div><h3 style="margin-left: 70px;"><a href="https://learning.fnigc.ca/#/public-dashboard">Cours fondamentaux des principes PCAP/OCAP (Propriété, Contrôle, Accès et Possession)</a></h3></li>
			<li style="margin-left: 70px;"><strong>First Nations Information Governance</strong></li>
			<li style="margin-left: 70px;">Formation en ligne au Québec, 6 heures.</li>
      </li>
			<li>
			<li><div class="timeline-dot" data-date="Janv 2020"></div><h3 style="margin-left: 70px;"><a href="http://r.qcbs.ca/fr/workshops/">Ateliers R sur les modèles linéaires généralisés mixtes</a></h3></li>
			<li style="margin-left: 70px;"><strong>Centre de la Science de la Biodiversité de Québec</strong></li>
			<li style="margin-left: 70px;">Formation en présentiel au Québec, 1 semaine.</li>
      </li>
			<li>
			<li><div class="timeline-dot" data-date="Sept 2017"></div><h3 style="margin-left: 70px;">Advances in spatial analysis of ecological data using R</h3></li>
			<li style="margin-left: 70px;"><strong>PRstatistics</strong></li>
			<li style="margin-left: 70px;">Formation en présentiel, en anglais au Pays de Galle, 40 heures.</li>
      </li>
		 </ul>
  </section>

  <div class="divider"></div>

  <section class="collapsed">
    <h2>Langues </h2>
    <h4><img class="flag" src="https://cdn-icons-png.flaticon.com/128/330/330490.png" alt="-" /> Français </h4><p>Langue maternelle</p>
		<h4><img class="flag" src="https://cdn-icons-png.flaticon.com/128/317/317348.png" alt="-" />Anglais </h4><p>Rédaction d'articles scientifiques, réunions en anglais quotidiennes de 2020 à 2022 (vocabulaire scientifique, gestion de données, vie quotidienne)</p>
  </section>
	
	<div class="divider"></div>
	
	<div class="tools">
	<section class="collapsed">
    <h2>Outils</h2>
		<div class="tool-subcategories">
      <div class="tool-subcategory">
        <h3>Utilisation avancée</h3>
          <div class="tool-bar">
            <div class="progress-bar fully-mastered">
              <div class="level"></div>
            </div>
          </div>
					<ul>
						<li><h4>MS Office et Google drive</h4> 
							<li>Word et Docs: rédaction de documents avec mise en page avancée</li>
							<li>Excel: manipulation de données (utilisation de macros simples)</li>
							<li>PowerPoint et Slides: production de présentations de travail</li>
							<li>Forms: production formulaires</li>
							</li>
						<li><h4>R, RStudio</h4>
							<li>Analyses statistiques et visualisation de données</li>
							<li>Collecte, exploration, standardisation et mise à disposition de données ouvertes (requête API, standardisation des données, formatage de tables...)</li>
							<li>Travail collaboratif et enseignement (Rmarkdown)</li>
							<li>Création d'une application (RShiny)</li>
							</li>
					</ul>
        </div>

      <div class="tool-subcategory">
        <h3>Utilisation régulière</h3>
          <div class="tool-bar">
            <div class="progress-bar partially-mastered">
              <div class="level"></div>
            </div>
          </div>
          <ul>
						<li><h4>Git</h4>Utilisation du GitLab professionnel pour déposer et récupérer des projets de travail collaboratifs. </li>
							<li>Création de tickets (issues)</li>
							<li>Github personnel </li></li>
						<li><h4>HTML/CSS</h4>Personnalisation de l'esthétique d'une application en RShiny</li>
							<li>Création d'un CV interactif (avec l'aide de ChatGPT) </li></li>
						<li><h4>WeKan</h4>Gestion de projets en mode Agile</li>
						<li><h4>JIRA</h4>Gestion de projets en mode Agile</li>
						<li><h4>Wordpress</h4>Production de pages, d'articles et d'actualités pour le site web du service</li>
						<li><h4>Flourish</h4>Visualisation optimisée et interactive d'un jeu de données complexe</li>
						<li><h4>Genially</h4>Production de présentations avec animation</li>
					</ul>
        </div>

      <div class="tool-subcategory">
        <h3>Utilisation sporadique</h3>
          <div class="tool-bar">
            <div class="progress-bar low-mastered">
              <div class="level" style="width: 20%;"></div>
            </div>
          </div>
          <ul>
						<li><h4>ELabFTW</h4>Test du Cahier de Laboratoire Electronique</li>
						<li><h4>Collec-Science</h4>Test de l'application de gestion des collections d'échantillons</li>
						<li><h4>Cantharella</h4>Test de l'application de gestion des métadonnées d'un échantillon et de ses analyses</li>
						<li><h4>ERDDAP</h4>Vérification de format et retour UX</li>
						<li><h4>Python</h4>Modification d'une BDD dans ArcGIS</li>
						<li><h4>QGIS</h4>Personnalisation de cartes chargées depuis des entrepôts de données ouverts</li>
						<li><h4>ArcGIS</h4>Modification d'une BDD d'écosystèmes littoraux</li>
						<li><h4>ImageJ</h4>Comptage et mesure d'individus (mégafaune épibenthique) sur des images</li>
					</ul>
        </div>
      </div>   
  </section>
	</div>
	
	<div class="divider"></div>

  <section class="collapsed">
    <h2>Compétences techniques</h2>
    <ul>
      <li>Analyse de données avec R</li>
      <li>Collaboration avec informaticiens</li>
			<li>Capacités éditoriales et de communication orale (rapports, articles scientifiques, affiches, colloques, animation et création d’ateliers grand public)</li>
			<li>Communication et organisation d'événements</li>
      <li>Organisation de réunions</li>
			<li>Gestion de projets scientifiques pluridisciplinaires</li>
			<li>Vocabulaire contrôlé (divers thesaurus, BODC, NC)</li>
    </ul>
		
		<h2>Compétences théoriques</h2>
    <ul>
      <li>Plans de gestion de données</li>
      <li>RGPD</li>
      <li>Recherche reproductible</li>
      <li>Écosystème des entrepôts et catalogues de données de recherche</li>
      <li>Principes FAIR et CARE</li>
			<li>Métadonnées (eml, iso, json)</li>
			<li>Cycle de vie de la donnée</li>
			<li>Données sensibles</li>
			<li>Formats de fichiers (ouverts et certains formats propriétaires)</li>
			<li></li>

    </ul>
  </section>

  <div class="divider"></div>
	
	<section class="collapsed">
    <h2>Campagnes en mer</h2>
		<ul>
    <li><div class="timeline-dot" data-date="été 2016"></div><strong style="margin-left: 70px;">Wiring The Abyss</strong></li>
		<li style="margin-left: 70px;">Campagne hauturière, 3 semaines au large de l’île de Vancouver. But: maintenance de l’observatoire NEPTUNE Canada et échantillonnage de la faune benthique</li>
		<li><div class="timeline-dot" data-date="automne 2012"></div><strong style="margin-left: 70px;">RETROKONK</strong></li>
		<li style="margin-left: 70px;">Campagne côtière, 1 semaine dans le nord du Golfe de Gascogne. But: échantillonnage, tri et pré-identification de la faune benthique.</li>
		</ul>
	</section>
	
	<div class="divider"></div>

  <section class="collapsed">
    <h2>Centres d'Intérêt</h2>
    <conteneur>
		<img class="Icon" src="https://cdn-icons-png.flaticon.com/128/5971/5971575.png" alt="Escalade" title="Escalade" />
		<img class="Icon" src="https://cdn-icons-png.flaticon.com/128/3792/3792629.png" alt="Randonnée" title="Randonnée" />
		<img class="Icon" src="https://cdn-icons-png.flaticon.com/128/2283/2283351.png" alt="Chasse sous-marine" title="Chasse sous-marine" />
		<img class="Icon" src="https://cdn-icons-png.flaticon.com/128/3526/3526027.png" alt="Activités nautiques" title="Act. nautiques" />
		</conteneur>
  </section>

  <div class="footer">
    <img src="https://img.genial.ly/5def6a572448c50fd41fce03/39430952-d170-45f3-bb92-03b4465ce214.png" alt="goeland" style="width: 100px; height: auto;">
  </div>

</body>

</html>
