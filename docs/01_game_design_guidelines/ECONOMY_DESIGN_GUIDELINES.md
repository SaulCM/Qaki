# Economy Design Guidelines

## 1. Purpose

This document establishes the principles, methods, and quality expectations for designing and maintaining in-game economies.

Its purpose is to ensure that economic systems create meaningful player decisions, support gameplay progression, provide appropriate resource availability, and remain consistent with the intended game experience.

An in-game economy encompasses the systems through which players acquire, store, consume, exchange, produce, and manage resources.

These guidelines provide a reusable framework for designing economic systems across different game genres. They do not prescribe a specific economic model, currency structure, or progression system.

## 2. Scope

These guidelines apply to:

- In-game currencies.
- Collectible and consumable resources.
- Resource generation and acquisition.
- Resource consumption and depletion.
- Item pricing and valuation.
- Trading and marketplaces.
- Shops and vendors.
- Crafting and production.
- Inventory and storage.
- Loot and reward distribution.
- Resource scarcity and abundance.
- Economic progression.
- Resource conversion systems.
- Player-driven economies, when applicable.
- Economy-related exploits and unintended resource generation.

These guidelines SHOULD be considered during concept development, prototyping, production, balancing, and post-release maintenance.

## 3. Economy Design Principles

### 3.1 Support the Core Gameplay

Economic systems MUST support the intended player experience and core gameplay loop.

Resources, currencies, and economic activities SHOULD have clear gameplay purposes.

An economic system SHOULD NOT exist merely because other games in the same genre include one.

Before introducing an economic mechanic, evaluate:

- What gameplay purpose does it serve?
- What decisions does it create?
- Which activities does it encourage?
- How does it interact with progression?
- What does it add to the player experience?
- Is its complexity justified?

### 3.2 Meaningful Resource Decisions

Resource management SHOULD create meaningful decisions.

Players MAY need to decide whether to:

- Spend or save resources.
- Upgrade or replace equipment.
- Craft or purchase an item.
- Explore or pursue a known resource source.
- Consume resources immediately or preserve them.
- Invest in short-term benefits or long-term progression.

Avoid economic systems where resource decisions are consistently obvious or where resources accumulate without meaningful uses.

### 3.3 Consistency

Economic rules SHOULD be internally consistent.

Related systems SHOULD use coherent acquisition rates, consumption requirements, conversion rules, and reward structures.

Exceptions MAY exist when they serve a deliberate design purpose.

### 3.4 Transparency

Players SHOULD understand important economic interactions.

Communicate relevant information about:

- Resource quantities.
- Costs.
- Rewards.
- Conversion rates.
- Requirements.
- Limitations.
- Potential consequences.

Hidden economic mechanics MAY be appropriate when discovery is an intentional part of the experience, but essential progression requirements SHOULD NOT depend on unexplained rules.

### 3.5 Controlled Complexity

Economic complexity SHOULD be proportional to its gameplay value.

Avoid unnecessary currencies, conversion steps, resource categories, and economic dependencies.

Every significant economic component SHOULD have a clear purpose.

### 3.6 Sustainable Resource Flow

The economy SHOULD maintain resource availability and consumption at levels appropriate to the intended gameplay experience.

Designers SHOULD consider both short-term and long-term resource behavior.

The economy SHOULD avoid unintended infinite generation, excessive accumulation, persistent shortages, or progression deadlocks.

## 4. Economic System Definition

Before designing an economy, establish its intended structure.

Document the following where applicable:

- Economic purpose.
- Resource categories.
- Currency types.
- Resource sources.
- Resource sinks.
- Conversion mechanisms.
- Storage rules.
- Trading mechanisms.
- Production systems.
- Progression dependencies.
- Economic restrictions.
- Potential exploits.

The level of documentation SHOULD reflect the complexity and importance of the system.

## 5. Resource Classification

Resources SHOULD be classified according to their gameplay function.

### 5.1 Currency

Currency represents a standardized unit of exchange or value.

Examples include:

- Coins.
- Credits.
- Gold.
- Tokens.
- Reputation points.
- Specialized faction currency.

Currency MAY be used for purchasing, trading, unlocking, or other progression activities.

Each currency SHOULD have a clearly defined purpose.

Avoid introducing multiple currencies that provide effectively identical functionality without a meaningful design reason.

### 5.2 Consumable Resources

Consumable resources are depleted when used.

Examples include:

- Ammunition.
- Food.
- Medicine.
- Energy.
- Crafting materials.
- Repair components.

Their availability and consumption rates SHOULD support the intended gameplay loop.

### 5.3 Renewable Resources

Renewable resources can be generated or acquired repeatedly.

Examples include:

- Regenerating energy.
- Replenishing environmental resources.
- Repeatable resource production.
- Periodic rewards.

Renewable resource generation SHOULD be evaluated against consumption and storage capacity.

### 5.4 Limited or Non-Renewable Resources

Limited resources have restricted availability or cannot be replenished through normal gameplay.

Examples include:

- Unique crafting materials.
- One-time rewards.
- Rare collectibles.
- Limited-use items.
- Finite environmental deposits.

Their acquisition and consumption SHOULD be designed carefully because they may influence irreversible player decisions.

### 5.5 Progression Resources

Progression resources are primarily used to unlock capabilities or advance the player's development.

Examples include:

- Experience points.
- Skill points.
- Upgrade materials.
- Unlock tokens.
- Research points.

Progression resources SHOULD have clear acquisition requirements and meaningful uses.

### 5.6 Resource Categories and Properties

When appropriate, define the following properties for each resource:

| Property | Description |
|---|---|
| Identifier | Unique internal resource identifier |
| Display Name | Player-facing name |
| Category | Resource classification |
| Acquisition Sources | Activities or systems that generate it |
| Consumption Methods | Activities or systems that use it |
| Storage Rules | Capacity and persistence behavior |
| Rarity | Relative availability |
| Renewability | Whether it can be replenished |
| Progression Role | Its relationship with player advancement |
| Dependencies | Other resources or systems involved |

Not every resource requires every property.

## 6. Resource Acquisition

### 6.1 Acquisition Sources

Every important resource SHOULD have clearly defined acquisition sources.

Sources MAY include:

- Exploration.
- Combat.
- Quests and objectives.
- Trading.
- Crafting.
- Gathering.
- Production.
- Exploration discoveries.
- Achievements.
- Environmental interactions.
- Periodic or passive generation.

Acquisition methods SHOULD align with the resource's purpose.

### 6.2 Acquisition Frequency

The frequency of resource acquisition SHOULD be appropriate to its value and intended usage.

Consider:

- Time required to obtain the resource.
- Difficulty of the activity.
- Risk involved.
- Availability of alternative sources.
- Player progression.
- Expected consumption.
- Resource storage limitations.

### 6.3 Acquisition Variety

Important resources SHOULD have an appropriate number of acquisition methods.

Alternative acquisition methods MAY support different playstyles and strategies.

However, not every resource needs to be obtainable through every activity.

### 6.4 Repeatable Acquisition

Repeatable acquisition systems SHOULD be evaluated for unintended farming strategies.

Consider:

- Repetition frequency.
- Reward consistency.
- Activity duration.
- Resource generation rate.
- Interaction with other systems.
- Whether the activity can be automated or exploited.

Repeatable activities SHOULD provide rewards appropriate to their effort and intended role.

## 7. Resource Consumption and Sinks

### 7.1 Resource Sinks

A resource sink is a mechanic or activity that removes resources from the player's available inventory or economy.

Examples include:

- Purchases.
- Crafting.
- Upgrades.
- Repairs.
- Consumable usage.
- Construction.
- Trading fees.
- Unlock requirements.
- Maintenance costs.

Resource sinks SHOULD provide meaningful gameplay value or support a deliberate economic purpose.

### 7.2 Consumption Rates

Consumption rates SHOULD be evaluated relative to acquisition rates.

Consider:

- Expected consumption per activity.
- Frequency of use.
- Resource availability.
- Player progression.
- Alternative consumption methods.
- Recovery opportunities.

Excessive consumption MAY create unnecessary friction or prevent players from engaging with important gameplay systems.

### 7.3 Mandatory and Optional Consumption

Distinguish between mandatory and optional resource expenditures.

Mandatory costs SHOULD be predictable enough to support normal progression.

Optional costs SHOULD provide meaningful alternatives, improvements, or conveniences.

Avoid optional expenditures that are effectively mandatory because the alternatives are unreasonably inefficient.

### 7.4 Resource Sinks and Progression

Resource sinks MAY control progression pace, but SHOULD NOT become arbitrary barriers.

When resources are required for progression, evaluate whether players have reasonable access to the necessary quantities.

## 8. Currency and Monetary Systems

### 8.1 Currency Purpose

Each currency SHOULD serve a distinct gameplay function.

For every currency, define:

- Its acquisition sources.
- Its primary uses.
- Its availability.
- Its relationship with progression.
- Whether it can be exchanged.
- Whether it can be lost or transferred.
- Whether it is renewable.

### 8.2 Currency Separation

Multiple currencies MAY be used when they support different economic activities or strategic decisions.

Examples include:

- General-purpose currency.
- Faction-specific currency.
- Premium or special event currency.
- Research currency.
- Regional or specialized trade tokens.

Avoid currency fragmentation that makes economic management unnecessarily confusing.

### 8.3 Currency Generation

Currency generation SHOULD be evaluated against spending opportunities.

Uncontrolled currency generation may reduce the value of rewards and make prices irrelevant.

### 8.4 Currency Removal

Currency sinks SHOULD provide meaningful opportunities to spend accumulated currency.

Examples include:

- Equipment purchases.
- Repairs.
- Upgrades.
- Services.
- Construction.
- Unlocks.
- Consumables.

Avoid introducing arbitrary costs solely to remove excess currency without considering their effect on player motivation.

## 9. Pricing and Value

### 9.1 Price Definition

Prices SHOULD reflect the intended value and availability of the item or service.

Consider:

- Resource acquisition difficulty.
- Player progression.
- Item usefulness.
- Alternative acquisition methods.
- Opportunity cost.
- Item scarcity.
- Economic supply and demand, where applicable.

### 9.2 Relative Value

Related items SHOULD have coherent relative prices.

For example, an item with substantially greater utility or rarity may justify a higher cost.

However, price differences SHOULD reflect actual gameplay value rather than arbitrary numerical hierarchy.

### 9.3 Price Progression

Prices MAY change throughout the game to reflect progression, availability, or changing economic conditions.

Price scaling SHOULD be evaluated against player income and resource generation.

### 9.4 Avoid Obsolete Purchases

Purchases SHOULD remain useful for an appropriate portion of the gameplay experience.

Early-game items MAY become less effective later, but the progression of item value SHOULD be intentional.

### 9.5 Opportunity Cost

Economic decisions SHOULD consider what players give up when choosing one expenditure over another.

If two purchases compete for the same limited resource, their relative value SHOULD create meaningful trade-offs where appropriate.

## 10. Trading and Marketplaces

When trading systems exist, they SHOULD provide clear and consistent exchange rules.

### 10.1 Trading Rules

Define:

- Available items and resources.
- Buy and sell conditions.
- Exchange rates.
- Transaction costs.
- Inventory restrictions.
- Trading limitations.
- Availability conditions.
- Player-to-player rules, when applicable.

### 10.2 Buy and Sell Values

Buying and selling prices MAY differ to support economic progression or prevent trivial conversion exploits.

The difference SHOULD have a clear purpose.

### 10.3 Market Availability

Market availability SHOULD reflect the intended game economy.

Markets MAY have fixed inventories, rotating inventories, regional availability, or dynamic supply.

The chosen model SHOULD be consistent with the game's complexity and intended experience.

### 10.4 Player-Driven Economies

When players can trade with one another, evaluate:

- Supply and demand.
- Item duplication.
- Currency generation.
- Market manipulation.
- Trade restrictions.
- Transaction security.
- Economic concentration.
- Exploitation through alternate accounts or coordinated activity.

Player-driven economies require additional monitoring and validation because player behavior can produce outcomes that are difficult to predict.

## 11. Crafting and Production Economies

When crafting or production systems exist, their economic structure SHOULD be documented.

### 11.1 Recipes and Requirements

Each production activity SHOULD define:

- Required inputs.
- Required quantities.
- Production output.
- Processing time.
- Additional costs.
- Failure conditions, if applicable.
- Dependencies.

Requirements SHOULD be appropriate to the value and purpose of the resulting item.

### 11.2 Production Value

Production systems SHOULD provide meaningful alternatives to direct acquisition.

Crafting MAY offer:

- Lower resource costs.
- Specialized equipment.
- Customization.
- Progression opportunities.
- Access to otherwise unavailable items.

### 11.3 Production Efficiency

Evaluate:

- Input-to-output ratios.
- Production duration.
- Resource availability.
- Storage requirements.
- Alternative production methods.
- Output value.
- Potential resource loops.

### 11.4 Production Chains

Complex production chains SHOULD be introduced only when they provide meaningful gameplay decisions.

Dependencies SHOULD be understandable and SHOULD NOT create unnecessary bottlenecks.

## 12. Scarcity and Abundance

### 12.1 Controlled Scarcity

Scarcity MAY create meaningful decisions and encourage resource prioritization.

However, scarcity SHOULD be intentional and consistent with the intended experience.

Consider:

- Resource availability.
- Consumption frequency.
- Alternative acquisition sources.
- Player progression.
- Storage capacity.
- Consequences of shortages.

### 12.2 Resource Abundance

Abundant resources MAY support experimentation and reduce unnecessary friction.

However, excessive abundance can make resource management meaningless.

Evaluate whether players still have meaningful reasons to acquire, conserve, and spend resources.

### 12.3 Resource Bottlenecks

A bottleneck occurs when limited availability of a particular resource restricts other gameplay activities or progression.

Bottlenecks MAY be intentional, but SHOULD be evaluated carefully.

Avoid unintended situations where a single resource prevents normal progression without providing reasonable acquisition opportunities.

### 12.4 Storage Capacity

Storage limitations MAY create meaningful inventory-management decisions.

When implementing capacity restrictions, consider:

- Resource stack sizes.
- Inventory organization.
- Storage upgrades.
- Transfer requirements.
- Item importance.
- Player convenience.

Storage limitations SHOULD contribute to gameplay rather than create unnecessary interface friction.

## 13. Economic Progression

### 13.1 Progression Alignment

The economy SHOULD evolve alongside player progression.

Consider how resource availability, purchasing power, production capabilities, and consumption requirements change throughout the game.

### 13.2 Early, Mid, and Late Game

When applicable, evaluate economic behavior across different progression stages.

| Stage | Design Considerations |
|---|---|
| Early Game | Introduce essential resources, establish acquisition methods, and teach spending decisions |
| Mid Game | Expand resource interactions, production options, and economic choices |
| Late Game | Preserve meaningful resource usage and prevent economic systems from becoming irrelevant |

These stages are conceptual and SHOULD be adapted to the game's structure.

### 13.3 Economic Obsolescence

As players progress, some resources or items MAY become less relevant.

Designers SHOULD consider whether obsolete resources can:

- Be converted.
- Be used in alternative recipes.
- Be exchanged.
- Support optional activities.
- Remain useful for specialized purposes.

Not every resource must remain equally valuable throughout the game.

### 13.4 Long-Term Sustainability

Evaluate whether the economy remains functional during extended gameplay.

A system that works during early progression may become unstable after significant resource accumulation or repeated activity.

## 14. Economic Modeling and Analysis

### 14.1 Resource Flow Analysis

For important resources, evaluate the relationship between generation and consumption.

A simplified resource balance can be represented as:

\[
R_{t+1} = R_t + G_t - C_t
\]

Where:

- \(R_t\): Resource quantity at the beginning of a period.
- \(G_t\): Resources generated during the period.
- \(C_t\): Resources consumed during the period.
- \(R_{t+1}\): Resource quantity at the end of the period.

This model MAY be extended to include conversion, transfer, losses, or other economic interactions.

### 14.2 Resource Generation and Consumption Rates

For recurring activities, evaluate average generation and consumption over an appropriate period.

A simplified net resource flow is:

\[
F = G - C
\]

Where:

- \(G\): Average resource generation rate.
- \(C\): Average resource consumption rate.
- \(F\): Net resource flow.

Interpretation:

- Positive flow indicates accumulation.
- Negative flow indicates depletion.
- Zero flow indicates a stable average quantity.

The desired result depends on the resource's intended role.

### 14.3 Economic Ratios

Useful measurements MAY include:

- Resource generation per minute.
- Resource consumption per activity.
- Reward-to-effort ratio.
- Item cost relative to average player income.
- Crafting input-to-output ratio.
- Time required to afford an item.
- Currency accumulation over progression.
- Resource availability relative to mandatory costs.

### 14.4 Simulation

Simulation MAY be used to evaluate complex economic systems before or during implementation.

Possible techniques include:

- Repeated activity simulation.
- Resource-flow modeling.
- Monte Carlo simulation.
- Price and reward comparisons.
- Production-chain analysis.
- Long-term accumulation analysis.

Simulation assumptions SHOULD be documented.

Analytical results MUST be validated against actual gameplay behavior when practical.

### 14.5 Avoid False Precision

Economic models are tools for understanding system behavior, not guarantees of enjoyable gameplay.

Numerical consistency does not automatically produce meaningful player decisions.

Economic values SHOULD be validated through playtesting.

## 15. Exploit Prevention and Economic Integrity

Economic systems SHOULD be evaluated for unintended resource generation and conversion exploits.

Potential problems include:

- Infinite resource loops.
- Item duplication.
- Repeated reward exploitation.
- Purchase-and-resell profit loops.
- Incorrect conversion ratios.
- Unintended stacking behavior.
- Transaction inconsistencies.
- Save/load duplication.
- Exploitation of system resets.
- Automated resource farming.

### 15.1 Conversion Validation

When resources can be converted between categories, verify that conversion rules produce the intended economic outcomes.

Repeated conversions SHOULD NOT create unintended positive resource gains.

### 15.2 Transaction Integrity

For systems involving purchases, trades, or resource transfers, verify that:

- Costs are applied correctly.
- Rewards are granted exactly once.
- Invalid transactions are rejected.
- Failed transactions do not produce partial unintended results.
- Inventory and currency states remain consistent.

### 15.3 Persistence

When economic data is saved, ensure that resource quantities and transaction states remain consistent across save and load operations.

## 16. Economic Testing and Validation

Economic systems SHOULD be tested through analytical evaluation and gameplay observation.

### 16.1 Test Scenarios

Relevant test scenarios MAY include:

- Normal resource acquisition.
- Repeated resource farming.
- High resource accumulation.
- Resource depletion.
- Mandatory progression expenditures.
- Alternative acquisition methods.
- Crafting and conversion chains.
- Purchase and resale interactions.
- Inventory capacity limits.
- Save and load behavior.
- Unusual combinations of economic systems.

### 16.2 Metrics

Relevant metrics MAY include:

- Average resource quantity.
- Resource generation rate.
- Resource consumption rate.
- Currency accumulation.
- Average purchase frequency.
- Time required to afford important items.
- Crafting profitability.
- Resource shortage frequency.
- Inventory utilization.
- Progression completion time.
- Distribution of player wealth, when applicable.

### 16.3 Qualitative Evaluation

Quantitative metrics SHOULD be complemented by observations of player behavior.

Evaluate whether players:

- Understand the economy.
- Make meaningful spending decisions.
- Experience appropriate scarcity.
- Have sufficient opportunities to acquire resources.
- Find economic activities worthwhile.
- Accumulate resources without meaningful uses.
- Become blocked by unexpected costs.
- Exploit unintended economic interactions.

### 16.4 Regression Testing

Changes to economic values or mechanics MAY affect multiple systems.

After significant changes, verify relevant interactions involving:

- Progression.
- Rewards.
- Crafting.
- Trading.
- Inventory.
- Resource generation.
- Resource consumption.
- Difficulty.
- Player upgrades.

## 17. Economic Iteration Workflow

Use the following workflow when designing or adjusting an economic system:

1. **Define purpose:** Establish the role of the economy in the gameplay experience.
2. **Classify resources:** Identify currencies, consumables, renewable resources, and progression resources.
3. **Map resource flows:** Document acquisition, consumption, conversion, and storage.
4. **Identify dependencies:** Determine which gameplay systems rely on each resource.
5. **Establish assumptions:** Define expected player behavior and economic conditions.
6. **Set initial values:** Establish reasonable starting quantities, rates, and costs.
7. **Analyze:** Use calculations or simulations where useful.
8. **Test:** Validate economic behavior through gameplay.
9. **Evaluate:** Identify shortages, excesses, exploits, and ineffective decisions.
10. **Adjust:** Modify the relevant mechanics or values.
11. **Regression test:** Verify related systems.
12. **Document:** Record significant decisions and unresolved issues.

Economic systems SHOULD be revisited as new mechanics, content, and progression opportunities are introduced.

## 18. Economy Configuration and Data Management

Where practical, economic values SHOULD be separated from gameplay logic.

In Godot projects, consider using appropriate resources or configuration data for tunable economic parameters.

Examples include:

- Item prices.
- Resource quantities.
- Acquisition rates.
- Consumption rates.
- Crafting recipes.
- Production durations.
- Reward tables.
- Currency conversion rates.
- Storage limits.

The implementation SHOULD:

- Use clear and consistent identifiers.
- Define appropriate value ranges.
- Avoid unnecessary duplication.
- Preserve a clear source of truth.
- Make important values easy to inspect and adjust.
- Validate configuration data where practical.

Data-driven configuration SHOULD be proportional to system complexity and expected maintenance needs.

## 19. Economy Documentation

Significant economic systems SHOULD document:

- Economic purpose.
- Resource classifications.
- Acquisition sources.
- Consumption methods.
- Resource-flow relationships.
- Pricing and conversion rules.
- Progression dependencies.
- Important formulas.
- Assumptions.
- Test scenarios.
- Observed results.
- Known exploits or risks.
- Accepted trade-offs.

Major economic changes SHOULD include a brief explanation of:

- What changed.
- Why it changed.
- What evidence supported the change.
- Which related systems were evaluated.
- What remains uncertain.

## 20. AI-Assisted Economy Design Requirements

AI agents assisting with economy design MUST follow these requirements:

1. Read the approved game vision and relevant game-specific design documentation.
2. Identify the intended purpose of each proposed economic mechanic.
3. Inspect existing resource sources, sinks, and dependencies before making changes.
4. Avoid introducing unnecessary currencies or resource categories.
5. Document important economic assumptions and formulas.
6. Distinguish calculated results from estimated or hypothetical values.
7. Evaluate resource generation and consumption together.
8. Identify potential bottlenecks, infinite loops, and conversion exploits.
9. Consider progression and long-term economic sustainability.
10. Recommend simulations or playtesting when appropriate.
11. Document significant economic changes and their rationale.
12. Seek project owner approval before making significant changes to approved economic design.

AI-generated economic recommendations are proposals until reviewed and validated.

## 21. Economy Review Checklist

Before considering an economic system sufficiently designed for its current development stage, evaluate:

- [ ] Its gameplay purpose is clearly defined.
- [ ] Important resources are classified.
- [ ] Resource acquisition sources are identified.
- [ ] Resource consumption methods are identified.
- [ ] Important resource flows are understood.
- [ ] Currency types have distinct purposes.
- [ ] Pricing and conversion rules are coherent.
- [ ] Resource availability supports intended progression.
- [ ] Resource sinks provide meaningful value.
- [ ] Potential bottlenecks have been evaluated.
- [ ] Long-term accumulation and depletion have been considered.
- [ ] Production and crafting dependencies are understood.
- [ ] Potential exploits have been evaluated.
- [ ] Relevant test scenarios have been completed.
- [ ] Significant changes have been regression tested.
- [ ] Known issues and assumptions are documented.

Not every item applies to every game. Non-applicable items SHOULD be identified rather than treated as mandatory implementation work.

## 22. Related Documents

This document SHOULD be used alongside relevant documents that exist in the repository, including:

- Game vision documentation.
- Design principles.
- Core loop design guidelines.
- Balancing guidelines.
- Difficulty design guidelines.
- Progression design documentation.
- Gameplay mechanics specifications.
- Inventory design documentation.
- Crafting and production design documentation.
- Quality standards.
- Definition of Done.
- QA and playtesting standards.

Game-specific resource definitions, prices, recipes, economic formulas, and configurations belong in the individual game's documentation and implementation.

## 23. Maintenance

These guidelines SHOULD be reviewed when:

- The studio's approach to economy design changes.
- New economic design practices are adopted.
- Repeated economic problems reveal gaps in the guidelines.
- New tools or techniques materially improve economic analysis and validation.

Changes MUST preserve the document's purpose as a reusable design guideline rather than turning it into a specification for a particular game.

The project owner is responsible for approving changes to studio-wide game design guidelines.