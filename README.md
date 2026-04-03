# Exam-SQL

# Partie 1 - Connaissances 

1. SELECT * FROM nom_de_la_table;

2. USE nom_de_la_bdd;

3. SELECT * selectionne TOUTES les informations de la tables.
SELECT colonne ne prendra qu'une colonne de la table choisi.

4. Pour ne pas afficher les doublons, on utilise la commande : DISTINCT
Cela permettra de faire une distinction entre toutes les lignes d'une table et s'il y a plusieurs fois un users, on le prendra 1 seulement fois.

5. On filtre avec la commande WHERE.
Par exemple WHERE date = "1989";

6. Pour une valeur partielle on utilise la commande LIKE.
Si on a une personne qui à pour NOM de famille SCOTT et que l'on ne connaît pas son prénom, on aura : name_user LIKE "% SCOTT" (avec % la partie inconnue)

7. condition AND condition => test qui doit correspondre aux 2 conditions.
condition OR condition => test qui doit correspondre à une des 2 conditions. 

8. COUNT (*) permet de compter le nombre de lignes d'une table en particulier.

9. DROP permet de supprimer une table complètement d'une bdd.
Alors que DELETE va être utilisé pour supprimer des éléments d'une table.


# Partie 2 - Requêtes simples

10. SELECT * FROM users;

11. SELECT name FROM users;

12. SELECT * FROM users WHERE age > 25;

13. SELECT * FROM users WHERE city = "Paris";

14. SELECT * FROM users WHERE name LIKE "MAR%" OR firstname LIKE "Mar%"; 
On part du principe que c'est un début de nom ou de prénom donc on cherche la fin de ce dernier. 

15. SELECT * FROM users WHER city = "Marseille" AND age = 18 OR age > 18 
    AND age < 30 OR age = 30;   
On vetu trouver tous les users habitant à Marseille avec 18 <= date >= 30

16. SELECT * FROM users
ORDER BY age DESC;
On sélectionne tous les users et on les affiche par age de manière décroissante.


# Partie 3 - Relations

17. SELECT * FROM orders;

18. SELECT * FROM orders WHERE amount > 100;

19. SELECT name, client_id FROM clients
JOIN orders ON clients.id = orders.client.id; 

20. SELECT * FROM clients
JOIN orders ON clients.id = orders.client.id
WHERE id = "5";     (On prend 5 un id au hasard pour voir toutes ses commandes)

21. COUNT amount FROM orders;
Ici on va chercher à faire le montant total de notre table orders.
Pour ça on va faire un compte de tous les amount présent dans notre table.

22. Pour trouver le montant moyen des commandes on va faire le compte de TOUTES les commandes et ensuite appliquer la formule de moyenne en prenant le montant total des commandes.

23. Pour avoir le nombre de commandes qui ont le même client_id dans la table orders. Ensuite on va relier cela à chauqe id de la table clients. 