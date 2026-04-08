---
marp: true
theme: default
paginate: true
backgroundColor: #f5f5f5
color: #1a1a1a
style: |
  section {
    font-family: 'JetBrains Mono', monospace;
    font-size: 24px;
    border: 1px solid #27272a;
    padding: 60px 80px;
  }
  h1 { color: #1a1a1a; font-size: 2.2em; margin-top: 80px; }
  h2 { color: #0066cc; font-size: 1.8em; border-bottom: 1px solid #cccccc; padding-bottom: 10px; }
  h3 { color: #333333; }
  code { background: #e8e8e8; color: #0066cc; border: 1px solid #cccccc; border-radius: 6px; }
  blockquote { background: #f0f0f0; border-left: 4px solid #0066cc; color: #333333; padding: 10px 20px; }
  
  .logo-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: absolute;
    top: 30px;   
    left: 60px;
    right: 60px;
  }
  .logo-header img {
    height: 110px;
  }
  
  .dt-card {
    background: #ffffff;
    padding: 25px;
    border-radius: 10px;
    border: 1px solid #cccccc;
    border-top: 4px solid #0066cc;
    margin-top: 20px;
  }
  
  .highlight { color: #3b82f6; font-weight: bold; }
---

<div class="logo-header">
  <img src="images/ofppt-logo.png"   alt="OFPPT">
  <img src="images/logo-solicode.png" alt="Solicode">
</div>

# **🧠 TDD : Test Driven Development**
### Développer mieux, coder plus sereinement

**Présenté par :** <span class="highlight">Yasmine Haddad</span>

---

## 🎯 1. Introduction au TDD

**Qu'est-ce que c'est ?**
Méthode de développement où l'on écrit les tests avant d'écrire le code.

<div class="dt-card">
  <h4>Objectifs principaux :</h4>
  <ul>
    <li>🛡️ Produire un code fiable</li>
    <li>🧩 Rendre le code facilement testable</li>
    <li>🛠️ Garantir une excellente maintenabilité</li>
  </ul>
</div>

**Contexte :**
Très utilisé et recommandé dans les environnements et méthodes Agiles.

---

## ⚙️ 2. Le Principe Fondamental

Le Cycle "Red - Green - Refactor"

- 🔴 **1. Red (Échec) :** Écrire un test qui échoue.
  *Pourquoi ?* Pour vérifier que le test détecte bien l'absence de la fonctionnalité.
- 🟢 **2. Green (Succès) :** Écrire le code minimal nécessaire pour faire passer le test.
- 🔄 **3. Refactor (Amélioration) :** Améliorer le code sans casser les tests (optimiser, nettoyer, typer).

> [!NOTE]
> En résumé : Test ❌ ➔ Code ✔️ ➔ Amélioration 🔄

---

## 🚀 3. Les Avantages du TDD

Pourquoi s'embêter à tester avant ?

<div class="dt-card">
  <ul>
    <li>✅ <strong>Code plus fiable :</strong> Le TDD permet de réduire le nombre de bugs, car chaque fonctionnalité est testée dès le départ.</li>
    <li>⏱️ <strong>Détection rapide :</strong> Les erreurs sont identifiées immédiatement, ce qui facilite leur correction</li>
    <li>📐 <strong>Meilleure conception :</strong> Le fait d’écrire les tests en premier pousse à mieux réfléchir à la structure du code.</li>
    <li>📖 <strong>Documentation automatique :</strong> Les tests montrent comment le code doit fonctionner.</li>
  </ul>
</div>

---

## ⚠️ 4. Les Inconvénients & Défis

Tout n'est pas magique, il y a des contraintes :

- 🧠 **Temps d'apprentissage :** Le TDD demande du temps pour s’habituer à cette façon de travailler..
- 🐢 **Lenteur initiale :** u début, on peut avoir l’impression de perdre du temps.
- 📏 **Rigueur exigée :** Il faut être discipliné et bien suivre les étapes du TDD.

---

## 💻 5. Exemple Concret (1/2)

🎯 **Problème :** Créer une fonction qui additionne deux nombres.

### 🔴 Étape 1 : Le test (RED)
On écrit le test avant que la fonction n'existe.

```php
public function testAddition()
{
    // On s'attend à ce que 2+3 donne 5
    $this->assertEquals(5, addition(2, 3));
}
```

👉 **Résultat :** Le test échoue (Erreur : la fonction addition n'existe pas).

---

## 💻 5. Exemple Concret (2/2)

### 🟢 Étape 2 : Le code minimal (GREEN)
On écrit juste de quoi faire passer le test.

```php
function addition($a, $b) {
    return $a + $b;
}
```
👉 **Résultat :** Le test passe au vert ! ✅

### 🔄 Étape 3 : Le nettoyage (REFACTOR)
On améliore la qualité du code.

```php
function addition(int $a, int $b): int {
    return $a + $b;
}
```
👉 **Résultat :** Code propre, typé, et toujours validé par le test !

---

## 🔄 6. Le Schéma Visuel

Voici la boucle infinie du développeur TDD :

```text
┌──────────────────────────────────────────────┐
│                                              │
│   📝 Write Test ➔ 🔴 Run Test (FAIL)         │
│                         │                    │
│                         ▼                    │
│   🔄 Refactor   ◄─ 🟢 Run Test (PASS)        │
│                         ▲                    │
│                         │                    │
│                   💻 Write Code              │
│                                              │
└──────────────────────────────────────────────┘
```

---

## ⭐ 7. Les Bonnes Practices

Pour réussir en TDD, il faut suivre ces règles d'or :

<div class="dt-card">
  <ul>
    <li><strong>KISS (Keep It Simple, Stupid) :</strong> Écrire des tests simples et compréhensibles.</li>
    <li><strong>Focus :</strong> Tester une seule chose à la fois par test.</li>
    <li><strong>Minimalisme :</strong> Ne pas écrire plus de code que ce que le test demande.</li>
    <li><strong>Discipline :</strong> Toujours prendre le temps de refactoriser à la fin du cycle.</li>
  </ul>
</div>

---

## 🛠️ 8. Les Outils Incontournables

Le TDD s'applique partout, voici les outils par langage :

- 🐘 **PHP :** PHPUnit, Pest (pour écrire les tests.)
- 🟨 **JavaScript / TypeScript :** Les outils les plus connus sont Jest, Vitest, Mocha
- 🐍 **Python :** PyTest, Unittest
- ☕ **Java :** L’outil principal est JUnit

---

## 🎯 9. Conclusion

- Le TDD n'est pas juste une technique de test, c'est une méthode de conception.
- “Il permet d’avoir un code plus propre, plus fiable et plus facile à maintenir.
- Même si ça demande de la pratique, c’est très utilisé dans les projets professionnels.

<br>

<div style="text-align: center; margin-top: 40px;">
  <h2>❓ Des questions ?</h2>
  <h3>Merci de votre attention !</h3>
</div>