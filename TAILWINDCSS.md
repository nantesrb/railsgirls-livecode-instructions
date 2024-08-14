# Tailwind et votre projet

Pour améliorer le rendu visuel de notre application Touiteur, nous utilisons le framework CSS [Tailwind](https://tailwindcss.com/).

Il est déjà intégré à votre application depuis que vous l'avez crée grâce à la commande `rails new touiteur-demo --css tailwind`

## 1. Modifier la structure HTML des vues

Vous pourvez utiliser des classes CSS fournies par Tailwind dans vos vues HTML. Voici un exemple de structure (aussi appelé _markup_) pour afficher une liste de messages.

```erb
<div class="container mx-auto py-4">
  <h1 class="text-center text-2xl font-bold mb-4">
    Touiteur
  </h1>
  <!-- TODO: Parcourir la liste des messages (variable '@messages') -->
    <div class="bg-white shadow-md rounded-lg mb-4 w-1/2 mx-auto">
      <div class="p-4">
        <h5 class="text-lg font-semibold flex items-center">
          Auteur
          <!-- TODO: Afficher ici l'auteur du message (méthode 'author') -->
        </h5>
        <p class="text-gray-700">
          <%= link_to '#', class: "no-underline text-gray-700 hover:text-gray-900" do %>
            Contenu
            <!--  TODO: Afficher ici le contenu du message (méthode 'content') -->
          <% end %>
        </p>
        <div class="flex justify-end items-center text-gray-500">
          <small>
            Date
            <!--  TODO: Afficher ici la date de création du message (méthode 'created_at') -->
          </small>
        </div>
      </div>
    </div>
  <!-- TODO: Fin de la boucle parcourant les messages -->
</div>
```

Libre à vous cependant de trouver d'autres structures qui vous conviennent. Pour cela, vous pouvez parcourir le Web [(exp ici d'une librairie de design)](https://flowbite.com/docs/components/card/).

## 3. Dynamiser les vues

Il ne nous reste plus qu'à afficher les données réelles (issues de la base de données) de chaque message. En effet, dans l'exemple donné ci-dessus, nous n'affichons pour l'instant aucune information issue de la base de données.

Pour réaliser cela, il vous faudra suivre ces étapes :
- boucler sur la liste des messages (présents dans la variable `@messages`, en utilisant la méthode `.each`
- afficher l'auteur du message (méthode `author`)
- de la même façon, afficher le contenu du message (méthode `content`)
- et enfin, afficher la date de création du message (méthode `created_at`)

Rappel : pour afficher le résultat d'une méthode Ruby, il faut l'entourer des balises `<%=` et `%>`.

Et voilà le résultat!
<img width="586" alt="Screenshot 2024-08-14 at 15 29 28" src="https://github.com/user-attachments/assets/cdbba204-12d7-4290-8f11-d22ee7439334">

## 4. Continuer sur cette voie !

Maintenant que vous maîtriser parfaitement Ruby on Rails et Tailwind, pourquoi pas mettre également à jour les vues de liste des messages, du formulaire de création, etc. ?
