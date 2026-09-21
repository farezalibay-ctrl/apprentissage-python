# Portofolio-analysis# Simulation d'un portefeuille boursier

Projection de **10 000 €** investis pendant **5 ans** avec un rendement annuel moyen de **8 %** (intérêts composés).
import pandas as pd
import matplotlib.pyplot as plt

capital_initial = 10_000
rendement_annuel = 0.08
duree_annees = 5

valeurs = [capital_initial]
for annee in range(1, duree_annees + 1):
    valeurs.append(valeurs[-1] * (1 + rendement_annuel))

tableau = pd.DataFrame({
    "Année": range(0, duree_annees + 1),
    "Valeur du portefeuille (€)": [round(v, 2) for v in valeurs],
    "Gain cumulé (€)": [round(v - capital_initial, 2) for v in valeurs],
})
tableau

