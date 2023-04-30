# POWERSHELL - Basic Commands

## SOMMAIRE
- [POWERSHELL - Basic Commands](#powershell---basic-commands)
  - [SOMMAIRE](#sommaire)
  - [BASICS](#basics)
  - [HELP](#help)
  - [ALIAS](#alias)
  - [CMDLETS](#cmdlets)
  - [VARIABLES](#variables)
  - [ASSIGNMENT, LOGICAL, COMPARISON OPERATORS](#assignment-logical-comparison-operators)
  - [IMPORTING, EXPORTING, CONVERTING](#importing-exporting-converting)
  - [ARRAYS, OBJECTS](#arrays-objects)
  - [WRITING OUTPUT AND READING INPUT](#writing-output-and-reading-input)

## BASICS
- `Cmdlet` Commande construite dans le shell, écrite en .NET
- `Functions` Commande écrite en langage PowerShell
- `Parameter` Argument d'un Cmdlet/Function/Script
- `Alias` Raccourcis d'un Cmdlet ou Function
- `Scripts` Fichier texte avec extension .ps1
- `Applications` Programme Windows existant
- `Pipeline |` Permet d'intéragir avec la commande
- `CTRL+C` Interrompt la commande en cours
- `Gauche/Droite` Bouge le curseur horizontalement
- `CTRL+Gauche/Droite` Bouge le curseur mot par mot
- `Home/End` Place le curseur au début / Fin 
- `Haut/Bas` Bouge le curseur verticalement
- `Insert` Switch entre mode Insertion et Ecraser
- `F7` Historique des commandes dans une fenêtre
- `Tab / Shift-Tab` Completion de la commande
## HELP
- `Get-Command` Affiche toutes les commandes
- `Get-Command -Module RGHS` Affiche toutes les commandes du module RGHS
- `Get-Command Get-p*` Affiche toutes les commandes commençant par p
- `Get-Help get-process` Affiche l'aide de la commande
- `Get-Process | Get-Member` Affiche les membres de l'objet
- `Get-Process | format-list -properties *` Affiche la commande sous forme de liste avec toutes les propriétés
## ALIAS
| Alias | Commande | Action |
| ------ | -------- | ----- |
| Gcm | Get-Command | Affiche les commandes
| Foreach,% | Foreach-Object | Pour chaque object
| Sort | Sort-Object | trier les objets
| Where,? | Where-Object | Localiser un objet
| Diff,compare | Compare-Object | Faire une comparaison
| Dir, ls, gci | Get-ChildItem | Obtenir la liste de fichiers/dossiers
| Gi | Get-Item | Prendre l'objet
| Copy,cp,cpi | Copy-Item | Copier
| Move,mv,mi | Move-Item | Déplacer
| Del,rm | Remove-Item | Supprimer
| Rni,ren | Rename-Item | Renommer
| Ft | Format-Table | Mettre au format tableau
| Fl | Format-List | Mettre au format liste
| Gcim | Get-CimInstance | Obtenir les versions de Windows
| Cat,gc,type | Get-Content | Lire le contenu d'un fichier
| Sc | Set-Content | Modifier le contenu d'un contenu
| h,history,ghy | Get-History | Afficher l'historique
| Ihy,r | Invoke-History | Invoque l'historique
| Gp | Get-ItemProperty | Obtenir les propriétés d'un objet
| Sp | Set-ItemProperty | Modifier les propriétés d'un objet
| Pwd,gl | Get-Location | Connaître son emplacement
| Gm | Get-Member | Afficher les membres 
| Sls | Select-String | Sélectionner le texte
| Cd,chdir,sl | Set-Location | Modifier son emplacement actuel
| Cls,clear | Clear-Host | Effacer le terminal
## CMDLETS

Liste d'exemple de Cmdlets disponible et d'objet:
| Cmdlets   | Objet
| ------------ | ------------ |
| Get-EventLog | Get-WinEvent |
|   | Get-Date |
| Start-Sleep | Compare-Object |
| Start-Job | Get-Credential  |
| Test-Connection | New-PSSession |
| Test-Path | Split-Path|
| Get-ADUser | Get-ADComputer|
| Get-History | New-ISESnippet |
| Get-WMIObject | Get-CimInstance |
## VARIABLES
| Syntax | Désignation
| ----|-----|
|`$var = "string"`  | Assigner une variable|
| `$a,$b = 0 or $a,$b = 'a','b'` | Assigner plusieurs variables|
| `$a,$b = $b,$a` | Inverser les variables|
| `$var=[int]5` | Forcer le texte de la variable|
## ASSIGNMENT, LOGICAL, COMPARISON OPERATORS

| Syntax | Désignation |
| ------ | ------- |
|=,+=,-=,++,-- |Assigner une valeur à la variable|
|-and,-or,-not,! |Connecte les expressions / états |
|-eq, -ne |Egale ou non égale |
|-gt, -ge |Plus grand que, Plus grand ou égale |
|-lt, -le |Moins que, Moins ou égale |
|-replace |“Hi” -replace “H”, “P” |
|-match,-notmatch | Vérifie les occurences |
|-like,-notlike |Occurences approximatives |
|-contains,-notcontains |Check si la valeur est présente |
|-in, -notin |L'inverse contient ou non|
## IMPORTING, EXPORTING, CONVERTING

| Exporter | Convertir |Importer | Désignation |
| ---------|-----------|--------|-------------|
| Export-CliXML | | Import-CliXML| Exporte/Importe au format CliXML
| | ConvertTo-XML || Converti au format XML
| |ConvertTo-HTML|| Converti au format HTML
| Export-CSV | |Import-CSV |  Exporte/Importe au format CSV
| |ConvertTo-CSV || Converti au format CSV
| |ConvertFrom-CSV || Converti à partir du format CSV
## ARRAYS, OBJECTS

| Chaîne de caractère / Objet | Désignation |
| ----- | ----- |
|$arr = "a", "b" | Chaîne de caractère |
|$arr = @() | Chaîne vide|
|$arr[5] | 6e élément de la chaîne|
|$arr[-3..-1] | Les trois derniers éléments de la chaîne|
|$arr[1,4+6..9] | Elements indéxés 1,4, 6-9|
|$arr[1] += 200 | Add to array item value|
|$z = $arA + $arB | Deux chaînes de caractères en une seule|
|[pscustomobject]@{x=1;z=2} | Créer un objet personnalisé|
|(Get-Date).Date |Date de l'objet|
## WRITING OUTPUT AND READING INPUT
| Syntax | Désignation |
| ------ | ------------ |
| "This displays a string" |String is written directly to output|
| Write-Host "color" -ForegroundColor Red -NoNewLine |String with colors, no new line at end|
| $age = Read-host "Please enter your age" |Set $age variable to input from user|
| $pwd = Read-host "Please enter your password" -asSecureString |Read in $pwd as secure string|
| Clear-Host| Clear console|

