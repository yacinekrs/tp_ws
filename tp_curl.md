# TP curl - comprendre les requêtes et les réponses HTTP

Pour les questions suivantes, vous devez utiliser l'url suivante : https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe

Pour tous les appels vous devez ajouter un header pour identifier votre appel parmis ceux des autres étudiants : x-student : VOTRE_NOM

## Faire un appel curl : copier la commande exécutée et indiquer la requête et la réponse
curl --header "x_student:yacinekrs" https://webhook.site/6f594809-a4b4-483e-841b-0c3b0a00edfe -v

-la requete:

> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x_student:yacinekrs

-la reponse :

< HTTP/1.1 200 OK
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: e4e6cb2f-e23b-41ff-8f35-7d8cc69f2f87
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:04:57 GMT
<

## Quel est la version du protocole utilisé par le serveur ?
 on utilise le protocole http et sa version est HTTP/1.1

## Quels sont les headers que l'on envoie dans la requête ? Quels sont leur sens ?
> GET /6f594809-a4b4-483e-841b-0c3b0a00edfe HTTP/1.1 // c'est la methode utilisé GET
> Host: webhook.site //la site web a qui on a envoyé la requete 
> User-Agent: curl/7.68.0 // version du curl utilisé
> Accept: */*
> x_student:yacinekrs // le nom de l'utilisateur qui fait la requete

## Quelles informations pouvez-vous trouver à propos du certificat SSL ?
* SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384
on trouve la version du certificat ssl utilisé

## Quel est le code de la réponse ? Que signifie-t-il ?
-Code : 200 veut dire que c'est un succes

## Quels headers recevez vous dans la response ? Quels sont leur sens ?

< Server: nginx    // le nom du serveur qui a repondu 
< Content-Type: text/plain; charset=UTF-8 // le type du fichier retourner et le type de caractere utilise
< Transfer-Encoding: chunked   //forme de l'encodeage pour trandferer toute en securité
< Vary: Accept-Encoding
< X-Request-Id: 50988a89-913f-4fcd-9ade-3c1661db898e
< X-Token-Id: 6f594809-a4b4-483e-841b-0c3b0a00edfe
< Cache-Control: no-cache, private
< Date: Tue, 04 Oct 2022 15:31:30 GMT
<

## Faire un appel curl en envoyant du texte brut : copier la commande exécutée et indiquer la requête et la réponse
curl --header "x-student:yacinekrs" https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 --data "texte" -v
requete: 
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:yacinekrs
> Content-Length: 5
> Content-Type: application/x-www-form-urlencoded

reponse:
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: e7affe28-3116-4a48-b336-5d17b503ca3c
< X-Token-Id: 8e147a78-4d13-4452-9cc0-468b63433501
< Cache-Control: no-cache, private
< Date: Tue, 25 Oct 2022 15:02:10 GMT

## Faire un appel curl en envoyant du JSON (avec les bons headers) : copier la commande exécutée et indiquer la requête et la réponse


## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 


## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1


## Quel est le code HTTP reçu ? Quel est sa signification ?


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1


## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999


## Quel est le code HTTP ? Que signifie-t-il ?


## Exécuter la requête suivante et copier la réponse : curl https://google.fr


## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?


## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
