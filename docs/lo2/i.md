# Inference

## Inference in Propositional

**Propositional logic** deals with whole, indivisible declarative statements (propositions) that are either true or false, linked together by operators like **AND** **(\(\land \))**, **OR (\(\lor \))**, **NOT (\(\neg \))**, and **Implication (→)**.

**How it works**: Inference in propositional logic applies standard rules of derivation to move from premises to a valid conclusion without breaking truth values.

**Scope**: It has a local/atomic scope; it cannot look inside a statement to examine individual objects, properties, or internal relationships.

<br/>

- **Modus Ponens**: If P → Q is true and P is true, then Q is true.
	- **Example**: If it rains, the grass gets wet (P → Q). It is raining (P). Therefore, the grass is wet (Q).
- **Modus Tollens**: If P → Q is true and \(\neg Q\) is true, then \(\neg P\) is true.
- **Hypothetical Syllogism**: From P → Q and Q → R, you can infer P → R.
- **Disjunctive Syllogism**: From \(P \vee Q\) and \(\neg P\), you can infer Q.

<br/>

## Inference in First Order Logics

**First-Order Logic (also called predicate logic)** extends propositional logic by adding **objects**, **properties**, **relations, predicates**, and **quantifiers (Universal ∀ and Existential ∃)**.

**How it works**: Inference in FOL incorporates all propositional rules plus specialized rules to handle variables, constants, and quantifiers.

**Scope**: It has a global scope allowing complex reasoning about structured objects and how they interact in a domain.

<br/>

- **Universal Instantiation**: If a statement holds for all objects (∀ x P(x)), you can infer it for a specific object (P(c)).
	- **Example**: From "All humans are mortal" (∀ x: Human(x) → Mortal(x)), you can infer "Socrates is mortal" given Human(Socrates).
- **Universal Generalization**: If you prove a property for an arbitrary element c, you can generalize it to all elements (∀ x P(x)).
- **Existential Instantiation & Introduction**: Rules that allow you to substitute or introduce witnesses for "there exists" (∃) statements.
- **Unification and Substitution**: Core algorithmic steps where variables are matched and replaced with constants or other terms to make different expressions look identical.

<br/>

## Key Differences

<br/>

| Feature | Propositional Logic Inference | First-Order Logic (FOL) Inference |
| :--- | :--- | :--- |
| **Basic Unit** | Whole propositions (P, Q) | Predicates, terms, and variables (P(x), Cat(y)) |
| **Quantifiers** | None | Uses ∀ (for all) and ∃ (there exists) |
| **Expressiveness** | Limited to flat truth values | High; can model objects, relations, and rules |
| **Core Mechanisms** | Truth tables, Modus Ponens, Resolution | Unification, substitution, and instantiation |
