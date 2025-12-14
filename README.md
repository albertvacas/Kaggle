# GRADE PREDICTION MODEL (Model de predicció de Nota Acadèmica)

## Autors
| **Nom**               | **NIU**   |
|-----------------------|-----------|
| Albert Vacas Martínez | 1665473   |

---

## Objectiu 

L'objectiu principal d'aquest projecte és crear i avaluar un model d'aprenentatge automàtic per predir la nota final de l'assignatura (`G3`) d'estudiants de secundària. Aquesta predicció es basa en un conjunt de factors acadèmics (notes prèvies) i socioeconòmics.



| Variable | Descripció |
| :--- | :--- |
| **Target** | `G3` (Nota final - 0 a 20) |
| **Features clau** | `G1` (Nota T1), `G2` (Nota T2), `absences`, factors socioeconòmics (`Medu`, `Fedu`, `famrel`, etc.) |

---

El projecte s'ha estructurat seguint un flux de treball estàndard de Machine Learning, dividit en quatre fases:

1.  **Exploració i Neteja de Dades:** Anàlisi de la distribució de les variables i gestió de valors nuls.
2.  **Enginyeria de Característiques:** Codificació de variables categòriques (`One-Hot Encoding`) i escalat de variables numèriques.
3.  **Selecció i Entrenament de Models (Model Selection):** S'ha utilitzat una estratègia de cerca de *Grid Search* amb validació creuada per entrenar diversos models de regressió (Random Forest, Lasso, etc.) i ajustar-ne els hiperparàmetres per maximitzar el rendiment.
4.  **Avaluació Final i Anàlisi:** Avaluació del model guanyador amb dades no vistes (*Test Set*) i interpretació dels resultats, mètriques i importància de variables.

---

## Resultats

El model amb el millor rendiment en el conjunt de dades complet (sense eliminació d'outliers) ha estat el **RandomForestRegressor**.

| Mètrica | Valor | Interpretació |
| :--- | :--- | :--- |
| **MAE** (Error Absolut Mitjà) | **$1.0942$ punts** | El model s'equivoca de mitjana en poc més d'un punt. |
| **$R^2$** (Coeficient de Determinació) | **$0.8280$** | El model explica el 82.8% de la variància total de la nota final. |
