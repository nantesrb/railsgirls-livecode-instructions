# Intégrer Bootstrap au projet

Pour améliorer le rendu visuel de notre application Touiteur, on peut utiliser un framework CSS. Un des plus connus est [Bootstrap](https://getbootstrap.com/).

Voici les quelques étapes nécessaires pour intégrer Bootstrap dans notre projet.

## 1. Ajouter les dépendances CSS et Javascript

Replacer le contenu du fichier `app/views/layouts/application.html.erb`, ajouter les lignes suivantes dans la section `<head>` :

📄
```erb
<!DOCTYPE html>
<html>
  <head>
    <title>TouiteurDemo</title>
    <%= csrf_meta_tags %>
    <%= csp_meta_tag %>
    <%= stylesheet_link_tag "https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css", integrity: "sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z", crossorigin: "anonymous" %>
    <%= stylesheet_link_tag 'application', media: 'all' %>
    <%= javascript_include_tag "https://code.jquery.com/jquery-3.5.1.slim.min.js", integrity: "sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj", crossorigin: "anonymous" %>
    <%= javascript_include_tag "https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js", integrity: "sha384-9/reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU+6BZp6G7niu735Sk7lN", crossorigin: "anonymous" %>
    <%= javascript_include_tag "https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js", integrity: "sha384-B4gt1jrGC7Jh4AgTPSdUtOBvfO8shuf57BaghqFfPlYxofvL8/KUEfYiJOMMV+rV", crossorigin: "anonymous" %>
  </head>
  <body>
    <%= yield %>
  </body>
</html>
```

Cette étape consiste à ajouter des feuilles de styles CSS et du code Javascript qui a déjà été écrit pour nous, et que nous nous contentons de réutiliser. C'est aussi comme ça que fonctionne le développement web : en (ré)utilisant des outils et des briques de base.

## 2. Modifier la structure HTML des vues

À partir de là, vous pourver utiliser des classes CSS fournies par Bootstrap dans vos vues HTML. Voici un exemple de structure (aussi appelé _markup_) pour afficher une liste de messages.

```erb
<div class="container-sm py-4">
  <h1>
    Touiteur
  </h1>
  <!-- TODO: Parcourir la liste des messages (variable '@messages') -->
    <div class="card mb-4 w-50 mx-auto">
      <div class="card-body">
        <h5 class="card-title d-flex align-items-center">
          Auteur
          <!-- TODO: Afficher ici l'auteur du message (méthode 'author') -->
        </h5>
        <p class="card-text">
          <%= link_to '#', class: "text-decoration-none stretched-link text-body" do %>
            Contenu
            <!--  TODO: Afficher ici le contenu du message (méthode 'content') -->
          <% end %>
        </p>
        <div class="d-flex justify-content-end align-items-center text-muted">
          <small>
            Date
            <!--  TODO: Afficher ici la date de création du message (méthode 'created_at') -->
          </small>
        </div>
      </div>
    <!-- TODO: Fin de la boucle parcourant les messages -->
  </div>
</div>
```

Libre à vous cependant de trouver d'autres structures qui vous conviennent. Pour cela, vous pouvez parcourir [le catalogue de composants de Bootstrap](https://getbootstrap.com/docs/4.5/components/card/).

## 3. Dynamiser les vues

Il ne nous reste plus qu'à afficher les données réelles (issues de la base de données) de chaque message. En effet, dans l'exemple donné ci-dessus, nous n'affichons pour l'instant aucune information issue de la base de données.

Pour réaliser cela, il vous faudra suivre ces étapes :
- boucler sur la liste des messages (présents dans la variable `@messages`, en utilisant la méthode `.each`
- afficher l'auteur du message (méthode `author`)
- de la même façon, afficher le contenu du message (méthode `content`)
- et enfin, afficher la date de création du message (méthode `created_at`)

Rappel : pour afficher le résultat d'une méthode Ruby, il faut l'entourer des balises `<%=` et `%>`.

## 4. Continuer sur cette voie !

Maintenant que vous maîtriser parfaitement Ruby on Rails et Bootstrap, pourquoi pas mettre également à jour les vues de liste des messages, du formulaire de création, etc. ?
