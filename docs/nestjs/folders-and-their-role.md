# Foldery i ich role

## prisma

W folderze z prismą powinniśmy trzymać folder z wszystkimi modelami. 
Rozrzucenie ich po całym projekcie nie jest dobrym pomysłem ze względu na późniejsze problemy z ich odszukaniem.

![Explorer prisma](asset/prisma-explorer.png)

## src

W folderze wydzieliłem 3 główne moduły:

- `api`
- `common`
- `templates` - Przydatne tylko w przypadku gdy korzystamy z MVC lub w jakimś celu generujemy widoki

![Explorer src](asset/src-explorer.png)

## api

Dobrą konwencją jest wyodrębnienie kilku folderów które będą określać poziom dostępności do znajdujących się poniżej endpintów

![Explorer api](asset/api-explorer-1.png)

Następnie każdy z tych folderów będzie posiadać własny zestaw funkcjonalności które będą wyodrębnione w osobnych folderach. <br/>
Plik `serviceAdmin.module.ts` importuje wszystkie znajdujące się w folderze serviceAdmin controllery i sewisy, 
następnie ten moduł jest importowany do `app.module.ts`

![Explorer api](asset/api-explorer-2.png)

We wnętrzu każdego folderu wykonujemy standardowe operacje 

![Explorer api](asset/api-explorer-3.png)

## common

Przetrzymuje wszystkie przydatne globalnie dekoratory, moduły, typy etc

![Explorer modules](asset/api-common.png)

## modules

Wszystkie paczki które nie są ściśle związane z projektem i mogą łatwo zostać przeniesione do innego projektu proponuję trzymać w folderze modules.

![Explorer modules](asset/api-modules.png)


