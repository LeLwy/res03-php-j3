La liste de tous les utilisateurs ;

SELECT * FROM users

La liste de tous les utilisateurs rangée par noms de famille ;

SELECT * FROM `users` ORDER BY last_name

Le dernier utilisateur inscrit ;

SELECT * FROM `users` ORDER BY registration_date DESC LIMIT 1

La liste de tous les utilisateurs fêtant leur anniversaire ce mois-ci ;

SELECT * FROM `users` WHERE MONTH(birthdate) = MONTH(NOW())

Le nombre total d'utilisateurs ;

SELECT COUNT(*) FROM users

La liste de tous les utilisateurs associés à leurs villes respectives ;

SELECT users.*, addresses.city FROM users JOIN addresses ON users.id = addresses.user_id

La liste de tous les utilisateurs vivant à une adresse sans numéro ;

SELECT * FROM users JOIN addresses ON users.id = addresses.user_id WHERE addresses.number IS NULL

La liste de tous les produits dont le prix est supérieur à 1 000 € ;

SELECT * FROM products WHERE products.price > 1000

La liste de tous les produits associés à leurs photos respectives ;

SELECT products.*, pictures.* FROM products JOIN pictures ON products.id = pictures.product_id

La liste de tous les produits appartenant à la catégorie « Voyage » ;

SELECT * FROM products JOIN products_categories JOIN categories ON products.id = products_categories.product_id AND categories.id = products_categories.category_id WHERE categories.title = "voyage"

La liste de tous les utilisateurs ayant effectué plus de dix commandes ;

SELECT users.* FROM users JOIN orders ON users.id = orders.user_id GROUP BY orders.user_id HAVING COUNT(orders.user_id) > 10

La liste de tous les produits achetés par le premier utilisateur inscrit.