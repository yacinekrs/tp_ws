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
curl -H "x-student:yacinekrs" https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -H 'content-type : application/json' --data '{name:yacine}' -v

requete:
> Host: webhook.site
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:yacinekrs
> content-type: application/json
> Content-Length: 13

reponse:
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: 26e81b17-be3e-4c04-adac-bab25c07e61d
< X-Token-Id: 8e147a78-4d13-4452-9cc0-468b63433501
< Cache-Control: no-cache, private
< Date: Tue, 25 Oct 2022 15:32:54 GMT

## Faire une appel curl en envoyant une basic authentication en utilisant 2 méthodes différentes : copier les commandes exécutées et indiquer la requête et la réponse à chaque fois 

curl -H "x-student:yacinekrs" https://webhook.site/8e147a78-4d13-4452-9cc0-468b63433501 -u 'YACINE:yackrs' -v

requete:
> GET /8e147a78-4d13-4452-9cc0-468b63433501 HTTP/1.1
> Host: webhook.site
> Authorization: Basic WUFDSU5FOnlhY2tycw==
> User-Agent: curl/7.68.0
> Accept: */*
> x-student:yacinekrs

reponse:
< Server: nginx
< Content-Type: text/plain; charset=UTF-8
< Transfer-Encoding: chunked
< Vary: Accept-Encoding
< X-Request-Id: e1ea9a2b-b3f0-4207-946a-2afd8cf041f3
< X-Token-Id: 8e147a78-4d13-4452-9cc0-468b63433501
< Cache-Control: no-cache, private
< Date: Tue, 25 Oct 2022 21:32:58 GMT


## Exécuter la commande suivante avec la méthode GET puis indiquer la réponse : curl https://demo.api-platform.com/books/07dd4786-aaa7-4d08-a467-076b76f1d1b6 
en executant cette commande, ca sera avec la methode GET par default

reponse:
< date: Tue, 25 Oct 2022 21:35:19 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 120
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation",<https://demo.api-platform.com/.well-known/mercure>; rel="mercure"
< permissions-policy: browsing-topics=()
< status: 404 Not Found
< x-content-type-options: nosniff
< x-frame-options: deny
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=jkQbttDCPESbZd2Y8tZMULT24XZRkck%2BQJB4ESL6uMTqMP47vhok4azbM6VCkZSExZttmZ9Cv0EMW6jCXfYxAozW4587nv%2BFhE6Tk%2BVFOkR6uofDoFQzz0a9vCFtfJTOQnv4rEI%2F2eA%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 75fe14d4280699f3-CDG
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400

## Exécuter la commande suivante avec la méthode PATCH  puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

curl -X PATCH https://demo.api-platform.com/top_books/1 -v

reponse:
< date: Tue, 25 Oct 2022 21:46:39 GMT
< content-type: text/html; charset=UTF-8
< allow: GET
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< permissions-policy: browsing-topics=()
< status: 405 Method Not Allowed
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=dtRnv3%2F4CtQ%2BHSQhvA%2FPXrKrh%2Bzho4oEe5BoU2XEcHbcky1h7LKzM4Dd2yhmujkRSLXrEswil7cWYI6xXx5Gx85eO%2Fb9gOJT2O38XVfbe8u4DFDwjFPOmGdRb0XeNgtaOxlff3D2FKs%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 75fe256cfe9199c3-CDG
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400

## Quel est le code HTTP reçu ? Quel est sa signification ?
CODE 405 méthode non allouée

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/1

{"@context":"\/contexts\/TopBook","@id":"\/top_books\/1","@type":"TopBook","id":1,"title":"Depuis l\u0027au-delà","author":"Werber Bernard","part":"","place":"F WER","borrowCount":9}

reponse:
< date: Tue, 25 Oct 2022 21:50:00 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 183
< cache-control: no-cache, private
< etag: "06a23177dff31429d2a7390117fe1b2d"
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< permissions-policy: browsing-topics=()
< vary: Accept
< vary: Content-Type
< vary: Authorization
< vary: Origin
< x-content-type-options: nosniff
< x-frame-options: deny
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=Xx8K8sQo1psM4yEEBQoCvgghO8IU2gMuM%2FgORpwB3DZMahLRvQIdh5ZttknQG1A8u5bJflNjSQM%2BG2Zyv0fLXBFikaY%2BIhyn9Wc4yzu%2FaAcxuGxsaN1OOQqUISDEG%2BZ6YLKQrZb%2FHXI%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 75fe2a550e0499e1-CDG
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400

## Exécuter la commande suivante puis indiquer la réponse : curl https://demo.api-platform.com/top_books/9999

{"@context":"\/contexts\/Error","@type":"hydra:Error","hydra:title":"An error occurred","hydra:description":"Not Found"} 

reponse:
< date: Tue, 25 Oct 2022 21:51:23 GMT
< content-type: application/ld+json; charset=utf-8
< content-length: 120
< cache-control: no-cache, private
< link: <https://demo.api-platform.com/docs.jsonld>; rel="http://www.w3.org/ns/hydra/core#apiDocumentation"
< permissions-policy: browsing-topics=()
< status: 404 Not Found
< x-content-type-options: nosniff
< x-frame-options: deny
< via: 1.1 google
< cf-cache-status: DYNAMIC
< report-to: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=54T8digD8sLxpd7PKGiO4y86hmLcvwa%2BMCwxGWHEf3zlht3iowgo7mRYPaRwuw096T5Vt4q8bxgH%2BrWET6XEaPj2oUiuWPblyYsoGN8kXq0MN18JZWDV9JvHO5I1QuWhqeipwqEGX5M%3D"}],"group":"cf-nel","max_age":604800}
< nel: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
< server: cloudflare
< cf-ray: 75fe2c5b2d72d6ea-CDG
< alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400


## Quel est le code HTTP ? Que signifie-t-il ?
< HTTP/2 404 
404: page introuvable

## Exécuter la requête suivante et copier la réponse : curl https://google.fr

< location: https://www.google.fr/
< content-type: text/html; charset=UTF-8
< date: Tue, 25 Oct 2022 21:54:09 GMT
< expires: Tue, 25 Oct 2022 21:54:09 GMT
< cache-control: private, max-age=2592000
< server: gws
< content-length: 219
< x-xss-protection: 0
< x-frame-options: SAMEORIGIN
< set-cookie: CONSENT=PENDING+395; expires=Thu, 24-Oct-2024 21:54:09 GMT; path=/; domain=.google.fr; Secure
< p3p: CP="This is not a P3P policy! See g.co/p3phelp for more info."
< alt-svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000,h3-Q050=":443"; ma=2592000,h3-Q046=":443"; ma=2592000,h3-Q043=":443"; ma=2592000,quic=":443"; ma=2592000; v="46,43"

## Quel est le code HTTP reçu ? Pouvez-vous expliquer cette réponse ?
< HTTP/2 301 : indique que le contenu de la page n'est plus disponible à l'URL renseignée

## Comment éviter cette réponse ? Trouvez 2 solutions différentes et détaillez les.
