import time
import random

class Joueur:
    def __init__(self, nom):
        self.nom = nom
        self.points_de_vie = 100

    def perdre_points_de_vie(self, points):
        self.points_de_vie -= points
        if self.points_de_vie <= 0:
            print("Vous êtes mort.")
            return True
        else:
            print(f"Il vous reste {self.points_de_vie} points de vie.")
            return False

def choix_utilisateur(options):
    print("\nQue choisissez-vous ?")
    for i, option in enumerate(options, 1):
        print(f"{i}. {option}")
    choix = input("Votre choix : ")
    while not choix.isdigit() or int(choix) not in range(1, len(options)+1):
        choix = input(f"Choisissez une option valide (1-{len(options)}) : ")
    return int(choix)

def aventure(joueur):
    print(f"Bienvenue dans l'aventure, {joueur.nom} ! Vous êtes un explorateur courageux à la recherche d'un trésor légendaire.")
    print("Votre histoire commence dans la ville de Céruléa, une cité prospère entourée par une jungle impénétrable.")
    print("Les rues de Céruléa grouillent de marchands, d'aventuriers et de mystiques, tous cherchant fortune et gloire.")
    time.sleep(2)
    print("Depuis des siècles, les légendes locales parlent d'un trésor perdu dans les profondeurs de la jungle.")
    print("Certains disent qu'il appartient à un ancien roi, d'autres prétendent qu'il est gardé par une créature mythique.")
    time.sleep(2)

    print("\nUn jour, alors que vous flânez dans les ruelles animées de la ville,")
    print("vous rencontrez un vieil homme au visage parcheminé, un cartographe nommé Orin.")
    print("Il prétend connaître l'emplacement du trésor et vous montre une carte ancienne, marquée d'une croix au cœur de la jungle dense.")
    time.sleep(2)
    print("Cette croix, dit-il, marque l'emplacement du trésor perdu, caché dans les ruines d'une cité oubliée.")
    time.sleep(2)

    print("\nIntrigué par cette révélation, vous décidez de vous lancer dans cette quête dangereuse,")
    print("déterminé à découvrir la vérité derrière la légende et à devenir célèbre dans tout le royaume.")

    while True:
        print("\nVous vous tenez devant un carrefour. Où voulez-vous aller ?")
        choix = choix_utilisateur(["Explorer la jungle dense",
                                   "Visiter les ruines d'un temple ancien",
                                   "Interagir avec les habitants de la ville"])

        if choix == 1:
            print("\nVous vous lancez courageusement dans la jungle épaisse...")
            time.sleep(2)
            if random.random() < 0.4:
                print("Vous êtes attaqué par un groupe de panthères sauvages !")
                points_de_vie_perdus = random.randint(20, 40)
                if joueur.perdre_points_de_vie(points_de_vie_perdus):
                    break
            else:
                print("Après une longue marche, vous découvrez une clairière mystérieuse.")
                print("La lumière du soleil filtre à travers les feuilles denses, éclairant une ancienne statue.")
                print("La statue, couverte de mousses et de lianes, semble regarder droit dans votre âme.")
                time.sleep(2)
                choix_clairiere = choix_utilisateur(["Examiner de plus près",
                                                      "Continuer à explorer la jungle"])

                if choix_clairiere == 1:
                    print("\nVous vous approchez de la statue, ressentant une étrange aura de mystère et de pouvoir.")
                    print("En la touchant, vous découvrez un passage secret derrière elle !")
                    print("Vous décidez de l'explorer...")
                    time.sleep(2)
                    print("Après une exploration minutieuse, vous découvrez une salle secrète contenant des trésors !")
                    print("Vous trouvez un parchemin avec des inscriptions anciennes, possiblement une carte.")
                    print("Vous prenez note de l'information et décidez de poursuivre votre quête.")
                else:
                    print("\nVous décidez de continuer à explorer la jungle, laissant la clairière derrière vous.")
                    print("Vous continuez à marcher, espérant trouver un autre indice.")

        elif choix == 2:
            print("\nVous décidez de visiter les ruines d'un temple ancien...")
            time.sleep(2)
            if random.random() < 0.3:
                print("Les ruines sont dangereuses et vous trébuchez sur un piège !")
                points_de_vie_perdus = random.randint(10, 30)
                if joueur.perdre_points_de_vie(points_de_vie_perdus):
                    break
            else:
                print("Vous découvrez une salle secrète sous le temple.")
                print("Elle est remplie de reliques et d'artefacts anciens !")
                print("La poussière de siècles se soulève à chacun de vos pas, vous rappelant la grandeur passée de ce lieu.")
                time.sleep(2)
                print("Vous explorez la salle et trouvez un coffre ancien.")
                print("Vous l'ouvrez et trouvez un précieux artefact !")
                print("Vous trouvez également un parchemin énigmatique avec des symboles mystérieux.")
                print("Vous soupçonnez que cela pourrait être une clé pour trouver le trésor.")
                print("Vous décidez de le garder avec vous et de poursuivre votre quête.")
                time.sleep(2)

        elif choix == 3:
            print("\nVous décidez de vous mêler aux habitants de la ville...")
            time.sleep(2)
            print("Vous entendez parler d'une légende locale sur un guide qui peut vous mener au trésor.")
            print("Vous partez à la recherche de ce guide dans les rues animées de Céruléa.")
            time.sleep(2)
            print("Après de nombreuses recherches, vous trouvez enfin le guide.")
            print("Il est vêtu de vêtements usés par le temps et son visage porte les marques d'innombrables voyages.")
            print("Vous l'abordez avec prudence et il vous sourit d'un air mystérieux.")
            time.sleep(2)
            print("Le guide vous propose de vous emmener au cœur de la jungle en échange d'une somme d'argent.")
            print("Il prétend connaître les chemins les plus sûrs et les secrets cachés de la jungle.")
            time.sleep(2)
            choix_guide = choix_utilisateur(["Payer le guide et le suivre",
                                              "Refuser son offre et continuer seul"])

            if choix_guide == 1:
                print("\nVous décidez de payer le guide et de le suivre dans la jungle dense.")
                time.sleep(2)
                print("Pendant des jours, vous traversez des sentiers escarpés et des rivières tumultueuses, suivant les indications du guide.")
                print("Finalement, vous arrivez à l'emplacement marqué sur la carte, un ancien temple caché dans les profondeurs de la jungle.")
                time.sleep(2)
                print("Le guide vous abandonne à l'entrée du temple, affirmant qu'il ne peut pas aller plus loin.")
                print("Vous le remerciez et entrez dans le temple, prêt à affronter les défis qui vous attendent.")

                # Défis du temple
                print("\nVous entrez dans le temple et découvrez une série de défis devant vous :")
                print("1. Un corridor obscur, rempli de pièges mortels.")
                print("2. Un escalier qui mène à une salle de statues.")
                print("3. Un labyrinthe complexe.")
                choix_temple = choix_utilisateur(["Corridor obscur",
                                                   "Salle de statues",
                                                   "Labyrinthe"])

                if choix_temple == 1:
                    print("\nVous vous engagez dans le corridor obscur...")
                    print("Des flèches jaillissent des murs, des dalles piégées menacent de s'effondrer sous vos pas.")
                    if random.random() < 0.5:
                        print("Vous parvenez à éviter les pièges et à atteindre l'autre côté sain et sauf.")
                    else:
                        print("Vous déclenchez un piège mortel et subissez des blessures graves !")
                        points_de_vie_perdus = random.randint(40, 60)
                        if joueur.perdre_points_de_vie(points_de_vie_perdus):
                            break

                elif choix_temple == 2:
                    print("\nVous gravissez les escaliers et entrez dans la salle de statues...")
                    print("Les statues semblent suivre chacun de vos mouvements, vous sentez une présence mystique.")
                    print("Vous avancez avec prudence, mais une statue s'anime soudainement et attaque !")
                    if random.random() < 0.5:
                        print("Vous parvenez à esquiver ses attaques et à vous échapper.")
                    else:
                        print("La statue vous blesse gravement avant que vous ne puissiez vous échapper !")
                        points_de_vie_perdus = random.randint(50, 70)
                        if joueur.perdre_points_de_vie(points_de_vie_perdus):
                            break

                elif choix_temple == 3:
                    print("\nVous pénétrez dans le labyrinthe...")
                    print("Les murs semblent se déplacer et changer de forme, vous désorientant.")
                    print("Vous tentez de trouver votre chemin à travers les passages étroits.")
                    if random.random() < 0.5:
                        print("Après de nombreux détours, vous trouvez la sortie du labyrinthe.")
                    else:
                        print("Vous vous perdez dans le labyrinthe et subissez une désorientation sévère !")
                        points_de_vie_perdus = random.randint(60, 80)
                        if joueur.perdre_points_de_vie(points_de_vie_perdus):
                            break

                # Arrivée au trésor
                print("\nAprès avoir surmonté les défis du temple, vous parvenez enfin à la salle du trésor.")
                print("Le trésor tant convoité repose devant vous, étincelant à la lueur des torches.")
                time.sleep(2)
                print("Félicitations, vous avez trouvé le trésor légendaire !")
                print("Vous êtes maintenant célèbre dans tout le royaume.")
                break

            else:
                print("\nVous refusez l'offre du guide, préférant continuer votre quête seul.")
                print("Vous le remerciez pour ses informations et retournez dans la jungle, déterminé à trouver le trésor par vous-même.")
                time.sleep(2)
                print("Vous parvenez à trouver l'entrée du temple sans guide.")
                print("Vous explorez les ruines antiques et finalement, vous découvrez le trésor légendaire !")
                print("Félicitations, vous avez remporté la partie !")
                break

if __name__ == "__main__":
    nom_joueur = input("Entrez votre nom : ")
    joueur = Joueur(nom_joueur)
    aventure(joueur)
