# Boutique Diayma
# Oumar Yoro DIOUF M2GLSI

## Question 1: Récupérez dans Visual Studio et exécutez le code fourni.

<img width="945" height="457" alt="image" src="https://github.com/user-attachments/assets/98e54519-a4a7-48b4-9149-e435d0f2b648" />

<img width="945" height="498" alt="image" src="https://github.com/user-attachments/assets/3fce60f7-6698-4fc6-aa4c-49bb3b0ec492" />

## Question 2: Quels sont les projets de la solution ?
<img width="420" height="422" alt="image" src="https://github.com/user-attachments/assets/9aa766ee-9c0c-40f7-9b1d-9ac08eca6f53" />

il y'a un seul projet dans la solution : Diayma

## Question 3: Quelle est la version SDK.NET utilisée par ces projets 
La version SDK.NET utilisée est : netcoreapp2.0

## Question 4: Installer le SDK
J'ai installé le sdk au lancement de visual studio car ça apparaissait au niveau des notifications

## Question 5: Créer un dépot Github pour y stocker le code 
**Lien du repo github :** https://github.com/Yorodiouf13/diayma_repo.git

<img width="945" height="374" alt="image" src="https://github.com/user-attachments/assets/34eaeb4d-52ab-4bfb-aa10-5a27f8d6e0e9" />

## Question 6: Explorez l’application. Signalez 2 bugs trouvés ?
**1er bug :** Lorsqu’on ne met rien dans le panier et qu’on appuie sur « Passer la commande » on est quand même redirigé sur la page de livraison 
**2ème bug :** La langue espagnol donne toujours du français et pas de l’espagnol 

## Question 7: Placer un point d'arrêt sur les lignes de code 

### a)  CartSummaryViewComponent ligne 12

<img width="625" height="305" alt="image" src="https://github.com/user-attachments/assets/84d5b421-0ed5-41f1-9bf1-57df467a439a" />

### b)	ProductController ligne 15

<img width="620" height="355" alt="image" src="https://github.com/user-attachments/assets/798376af-4535-4d62-9fc1-9fcd93d6d7d0" />

### c)	OrderController ligne 17

<img width="625" height="328" alt="image" src="https://github.com/user-attachments/assets/1d26b3ef-2807-427d-b8b2-08b6cae71a17" />

### d)	CartController ligne 15

<img width="620" height="329" alt="image" src="https://github.com/user-attachments/assets/8211630c-6fd9-49dc-a254-3acd6f34e546" />

### e)	Startup ligne 20

 <img width="622" height="409" alt="image" src="https://github.com/user-attachments/assets/3b7237db-12b3-46d3-afa7-1e09a71da34d" />


## Question 8: Quels sont les namespaces, classes et méthodes visités avant l’affichage des produits sur l’écran d’accueil de votre navigateur ?
**Mode utilisé : F10 (Pas à pas principal)** → pour rester dans le flux de notre application sans entrer dans le code de Microsoft.

### Séquence réelle observée dans la pile d’appels (Call Stack)

| Ordre | Namespace                                 | Classe                     | Méthode                              | Commentaire |
|-------|-------------------------------------------|----------------------------|--------------------------------------|-------------|
| 1     | P2FixAnAppDotNetCode                      | Program                    | Main()                               | Point d’entrée |
| 2     | Microsoft.AspNetCore.Hosting              | GenericWebHostBuilder      | Build()                              | Construction du host |
| 3     | P2FixAnAppDotNetCode                      | Startup                    | ConfigureServices(IServiceCollection) | Injection de dépendances (Cart, ProductService, etc.) |
| 4     | P2FixAnAppDotNetCode                      | Startup                    | Configure(IApplicationBuilder, IHostingEnvironment) | Configuration du pipeline HTTP |
| 5     | P2FixAnAppDotNetCode.Startup             | Configure()                | app.UseStaticFiles()                 | F10 → passe à la ligne suivante |
| 6     | P2FixAnAppDotNetCode.Startup             | Configure()                | app.UseRequestLocalization()        | F10 |
| 7     | P2FixAnAppDotNetCode.Startup             | Configure()                | app.UseSession()                    | F10 |
| 8     | P2FixAnAppDotNetCode.Startup             | Configure()                | app.UseMvc(routes => ...)            | F10 → ici le routeur est configuré |
| 9     | Microsoft.AspNetCore.Mvc                  | MvcRouteHandler           | RouteAsync()                         | Le framework trouve la route par défaut |
| 10    | P2FixAnAppDotNetCode.Controllers         | ProductController          | Index()                              | **Méthode exécutée pour l’URL /** |
| 11    | P2FixAnAppDotNetCode.Controllers.ProductController | Index()       | return View(products);               | Retourne la liste des produits |
| 12    | Microsoft.AspNetCore.Mvc.ViewFeatures     | ViewResultExecutor         | ExecuteAsync()                       | Rend la vue |
| 13    | Views/Product/Index.cshtml                | -                          | -                                    | Affichage final dans le navigateur |

### Conclusion
- La page d’accueil est gérée par **`ProductController.Index()`** (car la route par défaut est `{controller=Product}/{action=Index}`)
- Le point d’arrêt dans `Startup.cs` (ligne ≈20, `app.UseMvc(...)`) est bien traversé **avant** l’affichage des produits.
- Aucun des autres points d’arrêt (CartSummary, OrderController, etc.) n’est atteint au chargement de la page d’accueil → ils ne sont appelés que lors d’actions spécifiques.

**Méthode finale responsable de l’affichage des produits : `ProductController.Index()`**

## Question 9: Déploiement de la solution 

<img width="446" height="127" alt="image" src="https://github.com/user-attachments/assets/a5c76538-e28e-4a47-aaae-3f4bf5f86fea" />

<img width="672" height="341" alt="image" src="https://github.com/user-attachments/assets/b9fe1afb-9976-4fda-b656-eb0b9cfa0d12" />


## Question 10: Lien Google drive
**Lien :** https://drive.google.com/file/d/1WdgPgYdjaHbLJmo7yovoVaEtqZSVZPZu/view?usp=sharing



 








