# Coding style

## General

- UTF8

- pas de warning à la compilation

- indentation: 4 espaces

- nom de variables explicites

- une instruction par ligne

- pas de memory leaks/ segfault

- Macros en majuscules

- Chaques accolades doivent avoir sa propre ligne

- indentation correcte (vim: gg=G in normal mode)

- separation des composants dans des fichiers (.c/.h) differents

- Developpement sur la branche develop 
```bash
git checkout develop
```
- **INTERDIT** de push sur master

- **INTERDIT** de push force (sauf en cas d'état d'urgence déclaré par le chef suprême)

- Autorisation de créer de nouvelles branches pour les features 
Nom de la branche
```
feature/name
```
    name: le nom de la feature
```bash
git checkout -b feature/name
```
- Pour merge un branche de feature
```bash
git checkout develop
git merge feature/name
```

## Header (.h)

- Tous les fichiers .h doivent avoir la structure suivant :

```c
#ifndef _SRC_PATH_TO_H_
#define _SRC_PATH_TO_H_

// Définitions des macros, structures, fonctions

#endif /* _SRC_PATH_TO_H_ */

```
       PATH_TO_H: le chemin vers le fichier .h depuis le dossier src

- **Seulement** les fonctions, structures et macros devant etre accessibles depuis l'exterieur doivent etre definis dans le .h

- Pas de typedef pour les structures

- La definition d'une fonction dans le **.h** doit être de la forme

```c
/* functionName: description
 * arg1: type: description
 * arg2: type: description
 * return: void
 */
void functionName(int arg1, int arg2);
```

## Fonction

- Nom de fonction explicites

- Pour les fonctions devant etre accessibles depuis l'exterieur : nom de fonction relatif au module (ou du sous-module) de la forme 
```
MODULE_functionname
```
par exemple, pour une fonction du module de gui 
```
GUI_functionname
```

- La definition d'une fonction dans le **.c** doit être de la forme

```c
/* functionName: description
 * arg1: type: description
 * arg2: type: description
 * return: void
 */
void functionName(int arg1, int arg2)
{
    //YOUR CODE
}
```

## Structures

- Nom de fonction explicites

- definis dans le .h **seulement** si elles doivent etre utilisé depuis l'exterieur (sinon dans le .c)

- de la forme
```c
struct MODULE_structname {
    type var1;
    ...
    type varn;
} MODULE_structname
```

## Pointeurs

```c
char *var;

void *func(void *arg);
```

## Tests

- Les tests unitaires fonctionnent via [criterion](https://criterion.readthedocs.io) (Lit la doc putain !)

- Le nom des tests doivent êtres explicites et de la forme
```c
Test(MODULE_NAME, TEST_NAME)
{
    //YOUR TESTS
}
```




