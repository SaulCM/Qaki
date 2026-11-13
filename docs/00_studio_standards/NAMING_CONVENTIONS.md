# Naming Conventions

**Document Type:** Studio Standard  
**Status:** Draft  
**Applies To:** All studio projects, repositories, source code, documentation, and game assets

---

## 1. Purpose

This document establishes consistent naming conventions across studio projects to improve readability, maintainability, discoverability, and collaboration.

Consistent naming helps developers and AI agents understand the purpose of files, directories, classes, functions, variables, resources, and other project elements without relying on unnecessary context.

These conventions apply to all studio projects unless a project-specific technical standard explicitly defines a justified exception.

## 2. Scope

This standard covers:

- Directories and files.
- Documentation and technical specifications.
- Git branches and commits.
- GDScript files, classes, functions, variables, and constants.
- Godot scenes, nodes, resources, and signals.
- Game assets, including textures, sprites, audio, animations, and fonts.
- Game content, including items, characters, enemies, abilities, and levels.
- Automated tests and test resources.
- Configuration files and project metadata.

## 3. General Naming Principles

All names MUST follow these principles:

### 3.1 Clarity

- Use descriptive names that communicate purpose.
- Prefer explicit names over abbreviations.
- Avoid generic names such as `data`, `manager`, `handler`, or `helper` when a more precise name is possible.
- Use domain terminology consistently throughout the project.

### 3.2 Consistency

- Apply the same naming convention to elements of the same type.
- Maintain consistent terminology across code, documentation, scenes, and assets.
- Follow established conventions within the existing project before introducing new patterns.

### 3.3 Readability

- Prefer names that are easy to read and understand.
- Use meaningful word separation.
- Avoid unnecessarily long names while preserving clarity.
- Avoid ambiguous abbreviations and unexplained acronyms.

### 3.4 Stability

- Avoid names based on temporary implementation details when the element represents a stable game concept.
- Prefer names that remain meaningful if the implementation changes.
- Avoid embedding version numbers or arbitrary identifiers unless they serve a specific organizational purpose.

### 3.5 Technical Compatibility

- Use characters supported by the relevant programming language, engine, filesystem, and target platforms.
- Avoid special characters, whitespace, and inconsistent capitalization in technical identifiers.
- Preserve exact naming requirements imposed by Godot, GDScript, and external tools.

## 4. Standard Naming Styles

The following styles are used throughout studio projects.

| Convention | Format | Example |
|---|---|---|
| `snake_case` | Lowercase words separated by underscores | `player_controller` |
| `PascalCase` | Each word starts with an uppercase letter | `PlayerController` |
| `camelCase` | First word lowercase, subsequent words uppercase | `playerController` |
| `SCREAMING_SNAKE_CASE` | Uppercase words separated by underscores | `MAX_HEALTH` |
| `kebab-case` | Lowercase words separated by hyphens | `player-controller` |

Each naming style has designated use cases. Do not use them interchangeably without a technical reason.

## 5. Directory and File Naming

### 5.1 Directories

Use lowercase `snake_case` for project directories by default.

Examples:

```text
assets/
audio/
characters/
game_systems/
levels/
scenes/
scripts/
tests/
ui/
```

Requirements:

- Directory names MUST describe their contents or responsibility.
- Avoid spaces and special characters.
- Avoid unnecessary abbreviations.
- Use consistent pluralization within equivalent directory categories.
- Do not create directories whose names duplicate or contradict the existing project organization.

### 5.2 General Files

Use lowercase `snake_case` for general project files unless a framework, engine, or file format requires another convention.

Examples:

```text
player_controller.gd
inventory_system.gd
main_menu.tscn
enemy_stats.tres
game_settings.cfg
```

### 5.3 Documentation Files

Follow the conventions defined in `documentation_standards.md`.

For formal studio documentation, use lowercase `snake_case.md`.

Examples:

```text
development_philosophy.md
naming_conventions.md
code_review_guidelines.md
definition_of_done.md
```

Use uppercase names only when required by an established external convention or an existing repository standard.

### 5.4 Configuration and Tooling Files

Respect conventions established by the relevant tools and ecosystems.

Examples:

```text
.gitignore
.gitattributes
.editorconfig
project.godot
README.md
```

Do not rename framework-recognized files simply to enforce the studio naming convention.

## 6. GDScript Naming Conventions

Follow Godot's GDScript conventions.

### 6.1 Script Files

Use lowercase `snake_case` for GDScript filenames.

Examples:

```text
player_controller.gd
enemy_ai.gd
inventory_manager.gd
damage_calculator.gd
```

Script filenames SHOULD describe the primary responsibility of the script.

### 6.2 Classes

Use `PascalCase` for named GDScript classes declared with `class_name`.

Examples:

```gdscript
class_name PlayerController
class_name InventorySystem
class_name DamageCalculator
```

Class names MUST be descriptive and consistent with the script's responsibility.

Avoid declaring global classes when a local script class or another composition approach is more appropriate.

### 6.3 Variables

Use `snake_case` for variables.

Examples:

```gdscript
var player_health: int = 100
var movement_speed: float = 250.0
var current_weapon: WeaponData
var is_alive: bool = true
```

Variable names MUST communicate their meaning and intended use.

### 6.4 Constants

Use `CONSTANT_CASE` (`SCREAMING_SNAKE_CASE`) for constants.

Examples:

```gdscript
const MAX_HEALTH: int = 100
const BASE_MOVEMENT_SPEED: float = 250.0
const DEFAULT_ATTACK_COOLDOWN: float = 1.5
```

Use constants for values that are intended to remain unchanged during runtime.

### 6.5 Functions

Use `snake_case` for functions.

Examples:

```gdscript
func calculate_damage() -> int:
    pass

func update_movement(delta: float) -> void:
    pass

func apply_status_effect(effect: StatusEffect) -> void:
    pass
```

Function names SHOULD describe an action or operation.

Prefer verbs for methods that perform actions:

- `calculate_damage()`
- `update_inventory()`
- `apply_effect()`
- `save_game()`

### 6.6 Signals

Use `snake_case` for signals.

Examples:

```gdscript
signal health_changed(new_health: int)
signal player_died
signal inventory_updated
signal item_equipped(item: ItemData)
```

Signal names SHOULD describe an event that has occurred or a meaningful state change.

### 6.7 Enumerations

Use `PascalCase` for enum type names and `CONSTANT_CASE` for enum members.

Examples:

```gdscript
enum MovementState {
    IDLE,
    WALKING,
    RUNNING,
    JUMPING
}

enum DamageType {
    PHYSICAL,
    FIRE,
    POISON
}
```

### 6.8 Boolean Variables

Boolean names SHOULD communicate a condition or state.

Prefer prefixes such as:

- `is_`
- `has_`
- `can_`
- `should_`

Examples:

```gdscript
var is_alive: bool = true
var has_key: bool = false
var can_attack: bool = true
var should_update: bool = false
```

Avoid ambiguous boolean names such as `active`, `status`, or `enabled` when the intended meaning is unclear.

### 6.9 Private Members

Use a leading underscore for private or internal implementation details when appropriate.

Examples:

```gdscript
var _current_target: Node2D

func _calculate_internal_damage() -> int:
    pass
```

Follow Godot conventions for built-in lifecycle methods such as:

```gdscript
func _ready() -> void:
    pass

func _process(delta: float) -> void:
    pass
```

Do not expose internal implementation details unnecessarily.

## 7. Godot Scenes and Nodes

### 7.1 Scene Files

Use lowercase `snake_case` for scene filenames and the `.tscn` extension.

Examples:

```text
player.tscn
enemy_grunt.tscn
main_menu.tscn
inventory_panel.tscn
forest_level.tscn
```

Scene names SHOULD represent the primary object, interface, or environment they contain.

### 7.2 Node Names

Use `PascalCase` for node names in the scene tree.

Examples:

```text
Player
Sprite2D
CollisionShape2D
HealthComponent
InventoryPanel
AnimationPlayer
```

Requirements:

- Use descriptive names for custom nodes.
- Preserve meaningful names for built-in Godot node types when practical.
- Avoid ambiguous names such as `Node2D2`, `NewNode`, or `Container3`.
- Use consistent names for equivalent nodes across similar scenes.
- Do not rename nodes referenced by scripts, animations, signals, or external resources without checking their dependencies.

### 7.3 Node References

Use descriptive variable names when referencing nodes.

Examples:

```gdscript
@onready var animation_player: AnimationPlayer = $AnimationPlayer
@onready var health_component: Node = $HealthComponent
@onready var interaction_area: Area2D = $InteractionArea
```

Avoid unnecessary abbreviations or names that hide the referenced node's purpose.

## 8. Godot Resources and Resource Classes

### 8.1 Resource Files

Use lowercase `snake_case` for resource filenames.

Examples:

```text
iron_sword.tres
player_stats.tres
goblin_stats.tres
fire_damage_effect.tres
```

Use the appropriate Godot resource extension, such as `.tres` or `.res`.

### 8.2 Custom Resource Classes

Use `PascalCase` for custom resource class names.

Examples:

```gdscript
class_name WeaponData
class_name CharacterStats
class_name StatusEffect
```

### 8.3 Resource Naming

Resource names SHOULD identify the represented game entity or configuration.

Avoid naming resources after temporary development states or editor-generated defaults.

## 9. Asset Naming Conventions

Assets MUST use consistent, descriptive filenames that identify their content and, where useful, their role.

Use lowercase `snake_case` by default.

### 9.1 Textures and Sprites

Examples:

```text
player_idle.png
player_walk.png
goblin_attack.png
iron_sword_icon.png
forest_background.png
```

### 9.2 Audio

Include a meaningful description of the sound and its purpose.

Examples:

```text
player_footsteps.wav
sword_swing_01.wav
enemy_death.wav
forest_ambience.ogg
main_theme.ogg
```

### 9.3 Animations

Use descriptive names representing the action or animation state.

Examples:

```text
idle
walk
run
attack
hurt
death
```

Use consistent animation names across equivalent character types when their behavior is equivalent.

### 9.4 Fonts

Examples:

```text
main_ui_font.ttf
dialogue_font.ttf
title_font.otf
```

### 9.5 Asset Variants

When multiple variations of an asset exist, use numbered suffixes or meaningful variant descriptions.

Examples:

```text
rock_01.png
rock_02.png
rock_03.png

goblin_idle.png
goblin_idle_alternate.png
```

Use numbered suffixes for interchangeable variations and descriptive suffixes when the distinction has semantic meaning.

Do not use arbitrary suffixes such as `final`, `final2`, `new`, or `latest`.

## 10. Game Content Naming

Game content names SHOULD use terminology that reflects the game's world, design language, and player-facing concepts.

Examples include:

- Characters: `GoblinScout`, `Merchant`, `PlayerCharacter`.
- Items: `IronSword`, `HealthPotion`.
- Abilities: `Fireball`, `Dash`, `HealingAura`.
- Factions: `RoyalGuard`, `ForestClan`.
- Locations: `AbandonedMine`, `NorthernVillage`.

These are examples of conceptual names, not mandatory programming identifier styles.

Distinguish between:

- **Internal identifiers:** Stable technical names used by code and data.
- **Display names:** Player-facing names that may contain spaces, punctuation, localization, or stylistic capitalization.

Example:

```gdscript
const ITEM_ID: StringName = &"iron_sword"

@export var display_name: String = "Iron Sword"
```

Internal identifiers SHOULD remain stable even when player-facing names change.

## 11. Testing and QA Naming

Use lowercase `snake_case` for test filenames and test functions unless the selected testing framework requires another convention.

Examples:

```text
test_inventory_system.gd
test_damage_calculator.gd
test_player_movement.gd
```

Test function names SHOULD describe the behavior and expected result.

Examples:

```gdscript
func test_player_takes_damage_when_hit() -> void:
    pass

func test_inventory_rejects_invalid_item() -> void:
    pass
```

Test resources SHOULD identify the scenario or fixture they represent.

Examples:

```text
inventory_full_fixture.tres
low_health_fixture.tres
```

## 12. Git Naming Conventions

Git naming MUST follow the studio's branching and commit standards.

### 12.1 Branches

Use lowercase `kebab-case` for descriptive branch names after the branch type prefix.

Examples:

```text
feature/player-movement
feature/inventory-system
fix/player-death-animation
bugfix/inventory-duplication
docs/naming-conventions
refactor/damage-calculation
test/player-combat
```

Use the approved branch prefixes defined in `branching_strategy.md`.

### 12.2 Commits

Follow the studio's commit message convention, including its required type, scope, and description format.

Examples:

```text
feat(player): add sprint movement
fix(inventory): prevent item duplication
docs(standards): add naming conventions
refactor(combat): simplify damage calculation
```

The authoritative commit format belongs in the studio's commit conventions document, not in this naming standard.

## 13. Abbreviations and Acronyms

Abbreviations SHOULD be avoided unless they are widely recognized or established within the project.

Acceptable examples:

- `UI` — User Interface.
- `AI` — Artificial Intelligence.
- `NPC` — Non-Player Character.
- `HP` — Hit Points, when consistently established by the project.
- `ID` — Identifier.

Requirements:

- Use established terminology consistently.
- Do not invent abbreviations to shorten otherwise readable names.
- Document domain-specific abbreviations when they are necessary.
- Avoid multiple abbreviations for the same concept.

## 14. Naming Restrictions

The following practices MUST be avoided:

- Generic names that conceal purpose.
- Inconsistent capitalization for equivalent elements.
- Spaces in technical identifiers and asset filenames.
- Special characters in identifiers unless explicitly supported and required.
- Arbitrary numeric suffixes without a meaningful distinction.
- Temporary names such as `new_script`, `test2`, or `final_version`.
- Names that conflict with reserved language keywords or built-in engine identifiers.
- Names that misrepresent an element's responsibility.
- Renaming public interfaces or resource identifiers without checking dependencies.

## 15. Exceptions and Project-Specific Conventions

A project MAY introduce additional naming conventions when justified by:

- Engine or framework requirements.
- External integrations.
- Platform restrictions.
- Established project architecture.
- Specific artistic or content-production workflows.

Exceptions MUST:

1. Have a clear technical or production justification.
2. Be documented in the relevant project-specific standard.
3. Avoid contradicting mandatory engine or language conventions.
4. Be applied consistently within their scope.

When a project-specific convention conflicts with this document, the conflict MUST be documented and resolved according to the studio's documentation authority rules.

## 16. AI-Assisted Development Requirements

AI agents MUST follow this standard when creating or modifying project files, code, resources, and documentation.

Before introducing new names, agents MUST:

- Inspect existing naming patterns in the relevant directory.
- Check for existing classes, resources, files, and identifiers with similar names.
- Follow the applicable Godot and GDScript conventions.
- Preserve existing identifiers when renaming would break dependencies.
- Avoid introducing inconsistent naming styles.
- Report necessary naming deviations and their justification.

AI agents MUST NOT rename existing files, classes, nodes, resources, or public identifiers solely to impose personal naming preferences.

## 17. Compliance Checklist

Before completing a task, verify that:

- [ ] New directories and files follow the applicable naming convention.
- [ ] GDScript identifiers follow Godot conventions.
- [ ] Classes, functions, variables, and constants are named consistently.
- [ ] Scenes, nodes, and resources have descriptive names.
- [ ] Assets follow the established asset naming convention.
- [ ] Internal identifiers are distinct from player-facing display names.
- [ ] Tests use descriptive names.
- [ ] Git branches and commits follow their respective standards.
- [ ] No unnecessary abbreviations or ambiguous names were introduced.
- [ ] Existing references and dependencies remain valid after renaming.
- [ ] Any justified exception is documented.

## 18. Related Documents

- `development_philosophy.md`
- `documentation_standards.md`
- `git_conventions.md`
- `branching_strategy.md`
- `gdscript_standards.md`
- `architecture_guidelines.md`
- `asset_management_standards.md`
- `code_review_guidelines.md`
- `definition_of_done.md`

Only maintain references to documents that actually exist in the repository.

## 19. Maintenance

This document MUST be reviewed when:

- Studio-wide naming practices change.
- Godot or GDScript conventions materially change.
- New development tools introduce naming requirements.
- Repeated naming inconsistencies indicate that the standard needs clarification.

Changes to this standard require project owner approval before being marked `Approved`.