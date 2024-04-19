# Communication bidirectionnelle parent / iframe

Cette test démontre la communication bidirectionnelle parent / iframe inter-domaine (web).
`postMessage` est utilisée pour envoyer un message et `attachEvent` ou `addEventListener` pour les écouter.

[Documentation](https://developer.mozilla.org/fr/docs/Web/API/Window/postMessage)

Pour tester avec plusieurs domaines, on peut configurer la résolution sur 127.0.0.1. Exemple :
```shell
cat /etc/hosts |  grep 127
  127.0.0.1       localhost
  127.0.0.1       iframe-domain
  127.0.0.1       parent-domain
```

Exécution d'un serveur HTTP. Exemple :
```shell
docker run -it --rm --name test-server -p 8000:80 -v ${PWD}:/usr/share/nginx/html:ro nginx
```

Tester : http://parent-domain:8000/ivx_parent.html
