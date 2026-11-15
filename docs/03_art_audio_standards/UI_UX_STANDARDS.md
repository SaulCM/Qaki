# UI/UX Standards

## 1. Purpose

This document defines the studio-wide standards for the visual design, presentation, consistency, and usability of user interfaces in game projects.

Its purpose is to ensure that game interfaces:

- Communicate information clearly.
- Support intuitive player interaction.
- Maintain consistent visual identity.
- Provide understandable feedback.
- Remain readable across supported display configurations.
- Support accessibility and player comfort.
- Integrate consistently with the game's visual direction.
- Remain maintainable as the project evolves.

These standards are reusable across studio projects. Individual games MUST define their own interface design system, visual identity, navigation structure, interaction requirements, and supported display configurations.

## 2. Scope

These standards apply to:

- Heads-up displays (HUDs).
- Main menus.
- Pause menus.
- Settings and configuration screens.
- Inventory and equipment interfaces.
- Maps and navigation interfaces.
- Dialogue interfaces.
- Quest and journal interfaces.
- Notifications and alerts.
- Tooltips and contextual information.
- Icons and interface illustrations.
- Interface typography.
- Buttons, panels, and other visual components.
- Input prompts and control indicators.
- In-game overlays.
- Accessibility-related interface elements.

This document focuses on reusable visual and usability standards.

Detailed interface design methods, player experience principles, interaction design processes, and UX evaluation practices are defined in `UI_UX_DESIGN_GUIDELINES.md`.

Godot-specific scene structure, scripting, layout implementation, input handling, and resource management MUST follow the relevant technical standards.

## 3. UI/UX Principles

All game interfaces SHOULD follow these principles.

### 3.1. Clarity

The interface MUST communicate information in a way that players can understand.

Players SHOULD be able to identify:

- What information is being displayed.
- What actions are available.
- Which elements are interactive.
- What state the interface is in.
- What happened after an interaction.
- What information requires attention.

Avoid unnecessary visual complexity and ambiguous controls.

### 3.2. Consistency

Interface elements SHOULD behave and appear consistently across the game.

Consistency applies to:

- Typography.
- Colors.
- Icons.
- Spacing.
- Alignment.
- Component dimensions.
- Interaction states.
- Navigation behavior.
- Feedback.
- Animation and transitions.

Similar actions SHOULD use similar visual and interaction conventions unless there is a clear reason to differ.

### 3.3. Visual Hierarchy

The interface MUST establish a clear hierarchy between important and secondary information.

Use appropriate combinations of:

- Size.
- Contrast.
- Position.
- Spacing.
- Weight.
- Grouping.
- Color.
- Motion.

Critical information SHOULD be recognizable without requiring players to inspect every interface element.

### 3.4. Usability

Interfaces SHOULD minimize unnecessary effort and confusion.

Controls SHOULD communicate their purpose, provide understandable feedback, and behave predictably.

Avoid interactions that require players to guess how the interface works.

### 3.5. Player Focus

The interface SHOULD support gameplay rather than unnecessarily compete with it.

HUD elements, notifications, and overlays SHOULD occupy only the space and attention required by their purpose.

### 3.6. Accessibility

Interfaces MUST consider different player needs, display configurations, input methods, and visual abilities.

Accessibility requirements SHOULD be established early rather than treated exclusively as final-stage polish.

## 4. Interface Design System

Each game project SHOULD define a reusable interface design system.

The design system SHOULD establish:

- Color palette.
- Typography.
- Spacing conventions.
- Layout rules.
- Component styles.
- Icon conventions.
- Button styles.
- Panel and container styles.
- Interaction states.
- Feedback conventions.
- Animation and transition conventions.
- Accessibility requirements.

### 4.1. Design Tokens

Projects SHOULD use centralized design values for frequently reused properties.

Examples include:

- Primary and secondary colors.
- Background and surface colors.
- Text colors.
- Semantic colors.
- Font sizes.
- Spacing values.
- Border widths.
- Corner radii.
- Shadow properties.
- Animation durations.

Avoid introducing arbitrary values for individual components when an established design token already satisfies the requirement.

### 4.2. Component Reuse

Repeated interface elements SHOULD use reusable components when doing so improves consistency and maintainability.

Examples include:

- Buttons.
- Panels.
- Tabs.
- Input fields.
- Progress indicators.
- Tooltips.
- Notifications.
- Inventory slots.
- Item representations.

Reusable components SHOULD have clear responsibilities and configurable properties.

Avoid creating abstractions for components that are used only once and have no meaningful reuse or maintenance benefit.

### 4.3. Component Consistency

Components serving the same purpose SHOULD share consistent:

- Dimensions.
- Typography.
- Spacing.
- Colors.
- Interaction behavior.
- Feedback.
- Visual states.

Significant deviations SHOULD have a clear design justification.

## 5. Layout and Composition

Interface layouts MUST support readability, navigation, and interaction.

### 5.1. Layout Hierarchy

Organize interface elements according to their purpose and importance.

Consider:

- Primary information.
- Secondary information.
- Actions.
- Navigation.
- Contextual details.
- Decorative elements.

Related information SHOULD be grouped visually.

Unrelated elements SHOULD have sufficient separation.

### 5.2. Alignment and Spacing

Interfaces SHOULD use consistent alignment and spacing.

Avoid:

- Arbitrary spacing.
- Inconsistent margins.
- Unintentional overlap.
- Uneven alignment.
- Crowded controls.
- Unnecessary empty space that harms composition.

Spacing SHOULD communicate relationships between elements.

### 5.3. Information Density

The amount of information displayed SHOULD be appropriate for the interface's purpose.

Avoid presenting too much information simultaneously.

Complex interfaces SHOULD organize information into understandable groups, sections, tabs, or contextual views.

### 5.4. Safe Areas

Important interface elements SHOULD remain within appropriate display safe areas.

Account for:

- Screen edges.
- Display cutouts.
- Overscan where applicable.
- Platform-specific interface restrictions.
- Controller and television viewing conditions.

### 5.5. Gameplay Visibility

HUD elements and overlays MUST NOT unnecessarily obscure important gameplay information.

When overlays are required, their position, opacity, and duration SHOULD preserve appropriate visibility.

## 6. Typography Standards

Typography MUST prioritize readability and consistency.

### 6.1. Font Selection

Fonts SHOULD support the game's visual identity while remaining legible.

Consider:

- Readability.
- Character distinction.
- Supported languages.
- Font licensing.
- Available weights.
- Rendering quality.
- Display size.

Decorative fonts SHOULD be reserved for appropriate visual contexts, such as titles or selected headings.

### 6.2. Typography Hierarchy

Projects SHOULD define a consistent typography hierarchy.

Typical roles include:

- Display titles.
- Screen headings.
- Section headings.
- Body text.
- Supporting text.
- Labels.
- Tooltips.
- Captions.
- Numerical values.

Use size, weight, and spacing consistently to communicate hierarchy.

### 6.3. Text Readability

Text MUST have sufficient contrast against its background.

Avoid:

- Excessively small text.
- Unnecessary decorative effects.
- Long passages with poor line spacing.
- Inconsistent alignment.
- Overly narrow text containers.
- Background textures that interfere with reading.

### 6.4. Localization

Typography SHOULD accommodate supported languages and character sets.

Interface layouts MUST account for potential text expansion and different word lengths.

Do not assume that translated text will occupy the same space as the original.

## 7. Color Standards

Color usage SHOULD support visual hierarchy, readability, and game identity.

### 7.1. Color Palette

Each project SHOULD define an interface color palette.

It SHOULD include appropriate colors for:

- Primary interface elements.
- Secondary interface elements.
- Backgrounds.
- Surfaces and panels.
- Primary text.
- Secondary text.
- Borders and separators.
- Interactive elements.
- Semantic states.

### 7.2. Semantic Colors

Semantic colors SHOULD be applied consistently.

Typical meanings include:

- Success.
- Warning.
- Error.
- Information.
- Disabled.
- Selected.
- Highlighted.
- Destructive action.

Do not use the same color to communicate conflicting meanings within the same interface context.

### 7.3. Contrast

Text and important interface elements MUST remain distinguishable from their backgrounds.

Contrast SHOULD be evaluated in the actual game presentation rather than only in a design document.

### 7.4. Color Accessibility

Critical information MUST NOT rely exclusively on color.

Use additional indicators when appropriate, such as:

- Icons.
- Labels.
- Patterns.
- Shapes.
- Text.
- Distinct visual states.

Consider color-vision deficiencies when designing status indicators and interactive elements.

## 8. Icons and Visual Symbols

Icons SHOULD communicate their meaning clearly and consistently.

### 8.1. Icon Design

Icons SHOULD maintain consistent:

- Visual style.
- Proportions.
- Stroke or edge treatment.
- Perspective.
- Detail density.
- Color treatment.
- Alignment.

### 8.2. Icon Readability

Icons MUST remain recognizable at their intended display sizes.

Avoid excessive detail that disappears or becomes visually ambiguous when scaled down.

### 8.3. Icon Meaning

Important or unfamiliar icons SHOULD have supporting labels or tooltips.

Do not assume that players understand an icon simply because it is visually attractive.

### 8.4. Icon Consistency

Icons representing similar actions or categories SHOULD use consistent visual conventions.

Avoid mixing unrelated icon styles without a deliberate art direction decision.

## 9. Buttons and Interactive Components

Interactive components MUST communicate their purpose and interaction state.

### 9.1. Interactive States

Components SHOULD define the relevant states for their interaction type.

Common states include:

- Normal.
- Hovered.
- Focused.
- Pressed.
- Selected.
- Disabled.
- Loading.
- Error.

Not every component requires every state.

State changes MUST be visually distinguishable when the difference affects usability.

### 9.2. Button Design

Buttons SHOULD:

- Clearly communicate their action.
- Use understandable labels.
- Maintain consistent dimensions where appropriate.
- Provide visible interaction feedback.
- Distinguish primary and secondary actions.
- Clearly identify destructive actions.

### 9.3. Interactive Boundaries

Interactive elements SHOULD have sufficiently clear visual boundaries.

Clickable or selectable elements MUST NOT appear indistinguishable from purely decorative elements when that distinction matters.

### 9.4. Disabled Components

Disabled controls SHOULD communicate that they cannot currently be used.

When useful, provide an explanation of why the action is unavailable.

Disabled states SHOULD remain readable.

### 9.5. Destructive Actions

Actions with significant or irreversible consequences SHOULD have appropriate visual distinction and confirmation behavior.

The confirmation method SHOULD be proportional to the consequence.

Avoid unnecessary confirmation dialogs for routine actions.

## 10. HUD Standards

The heads-up display communicates information relevant during gameplay.

### 10.1. HUD Purpose

Each HUD element MUST have a clear gameplay or player-information purpose.

Examples include:

- Health.
- Stamina.
- Resources.
- Ammunition.
- Objectives.
- Interaction prompts.
- Status effects.
- Navigation.
- Combat information.
- Contextual notifications.

### 10.2. Information Priority

HUD elements SHOULD be prioritized according to their importance and frequency of use.

Critical information SHOULD be easy to identify.

Secondary information MAY be presented contextually or through expandable interfaces.

### 10.3. Screen Space

HUD elements SHOULD use screen space efficiently.

Avoid persistent elements that provide little value during normal gameplay.

### 10.4. Dynamic Visibility

HUD elements MAY appear or disappear according to gameplay context.

Visibility changes SHOULD be predictable and MUST NOT hide critical information unexpectedly.

### 10.5. HUD Consistency

HUD components SHOULD maintain consistent visual treatment, spacing, alignment, and feedback.

## 11. Menus and Navigation

Menus MUST support predictable navigation and clear information organization.

### 11.1. Navigation Structure

Menu hierarchies SHOULD be understandable and consistent.

Players SHOULD be able to determine:

- Their current location.
- Available actions.
- How to navigate.
- How to return to the previous screen.
- How to confirm or cancel actions.

### 11.2. Navigation Feedback

Navigation SHOULD provide clear feedback for:

- Selection.
- Focus.
- Activation.
- Cancellation.
- Screen transitions.
- Unavailable actions.

### 11.3. Menu Consistency

Related menus SHOULD share consistent:

- Layout.
- Navigation patterns.
- Button placement.
- Typography.
- Interaction behavior.
- Visual transitions.

### 11.4. Settings Interfaces

Settings SHOULD be grouped logically.

Examples include:

- Audio.
- Display.
- Graphics.
- Controls.
- Accessibility.
- Gameplay.
- Language.

Settings MUST communicate current values and provide appropriate feedback when changed.

### 11.5. Confirmation and Cancellation

Players SHOULD have clear ways to confirm, cancel, and return from menu interactions.

Settings that require explicit application SHOULD communicate whether changes have been saved or are still pending.

## 12. Inventory and Management Interfaces

Inventory and management interfaces SHOULD support efficient information scanning and interaction.

### 12.1. Item Representation

Items SHOULD communicate relevant information through appropriate combinations of:

- Iconography.
- Names.
- Categories.
- Descriptions.
- Quantities.
- Rarity.
- Attributes.
- State indicators.

### 12.2. Item Interaction

Interactions SHOULD clearly communicate their available operations.

Examples include:

- Select.
- Equip.
- Unequip.
- Use.
- Inspect.
- Move.
- Drop.
- Compare.
- Combine.

Unavailable operations SHOULD be visually distinguishable.

### 12.3. Item Comparison

When comparison is supported, relevant differences SHOULD be easy to identify.

Avoid presenting excessive numerical information without clear visual organization.

### 12.4. Capacity and Resource Feedback

Inventory capacity, resource quantities, and storage limitations SHOULD be communicated clearly.

Warnings SHOULD appear when they provide useful information to the player.

## 13. Notifications and Feedback

Notifications MUST communicate relevant information without unnecessarily interrupting gameplay.

### 13.1. Notification Types

Projects SHOULD distinguish relevant notification categories, such as:

- Informational.
- Success.
- Warning.
- Error.
- Objective updates.
- System messages.
- Progression events.

### 13.2. Notification Priority

Notification priority SHOULD reflect its importance.

Critical warnings SHOULD be distinguishable from routine informational messages.

### 13.3. Duration and Dismissal

Notification duration SHOULD be appropriate to the amount and importance of information.

Important information SHOULD remain available long enough to be understood.

Persistent notifications SHOULD provide a clear dismissal or resolution method when appropriate.

### 13.4. Visual Feedback

Interface interactions SHOULD provide feedback that confirms the result.

Examples include:

- Selection highlights.
- Button state changes.
- Progress indicators.
- Success messages.
- Error messages.
- State transitions.

Avoid feedback that is purely decorative when players need confirmation of an action.

## 14. Tooltips and Contextual Information

Tooltips SHOULD provide relevant information without overwhelming the interface.

They MAY communicate:

- Item descriptions.
- Control instructions.
- Attribute explanations.
- Interaction requirements.
- Status information.
- Additional context.

Tooltips SHOULD:

- Be readable.
- Appear near their associated elements when practical.
- Avoid obstructing important content.
- Remain visible long enough to be read.
- Support the appropriate input method.

Important gameplay instructions MUST NOT depend exclusively on hover-based tooltips.

## 15. Dialogue and Text Interfaces

Dialogue interfaces SHOULD support readability and character presentation.

Consider:

- Speaker identification.
- Text hierarchy.
- Dialogue pacing.
- Text readability.
- Choice presentation.
- Subtitle behavior.
- Character portraits.
- Dialogue progression feedback.

Player choices SHOULD be visually distinguishable from ordinary dialogue text.

Text speed, skip behavior, and dialogue progression SHOULD be consistent with the project's interaction requirements.

### 15.1. Subtitles

When subtitles are supported, they SHOULD:

- Be readable.
- Have sufficient contrast.
- Use appropriate background treatment.
- Identify speakers when necessary.
- Support relevant localization.
- Avoid obscuring important gameplay information.

## 16. Input and Control Presentation

Interfaces MUST communicate available interactions through appropriate input indicators.

### 16.1. Input Prompts

Input prompts SHOULD reflect the active input method where applicable.

Examples include:

- Keyboard and mouse.
- Game controller.
- Touchscreen.
- Other supported input devices.

### 16.2. Input Consistency

Controls serving similar purposes SHOULD use consistent visual and interaction conventions.

### 16.3. Input Method Changes

When the active input method changes, interface prompts SHOULD update appropriately when the project supports dynamic input detection.

### 16.4. Control Customization

If control remapping is supported, interfaces SHOULD clearly communicate:

- Available actions.
- Current bindings.
- Conflicting bindings.
- Unassigned actions.
- Reset options.

## 17. Animation and Transitions

Interface animations SHOULD improve clarity, feedback, and visual continuity.

### 17.1. Animation Purpose

Animations MAY communicate:

- State changes.
- Focus and selection.
- Opening and closing.
- Progress.
- Notifications.
- Transitions.
- Emphasis.

Avoid animations that add delay without improving the experience.

### 17.2. Consistency

Related interface animations SHOULD use consistent:

- Duration.
- Easing.
- Motion direction.
- Transition behavior.
- Visual intensity.

### 17.3. Responsiveness

Interface interactions MUST remain responsive.

Animations SHOULD NOT unnecessarily delay player input or prevent important actions.

### 17.4. Reduced Motion

Projects SHOULD provide appropriate options for reducing nonessential interface motion when relevant.

Avoid unnecessary flashing, rapid movement, or excessive visual effects.

Animation-specific requirements are defined in `ANIMATION_STANDARDS.md`.

## 18. Resolution and Display Adaptability

Interfaces MUST support the project's declared display configurations.

### 18.1. Resolution Support

Layouts SHOULD adapt appropriately to supported resolutions and aspect ratios.

Consider:

- Widescreen displays.
- Standard aspect ratios.
- Ultrawide displays, when supported.
- Different window sizes.
- Fullscreen and windowed modes.
- Platform-specific safe areas.

### 18.2. Scaling

Text, icons, and interactive elements SHOULD remain readable at supported display sizes.

Avoid fixed layouts that become unusable when the available display area changes.

### 18.3. Layout Validation

Interfaces SHOULD be reviewed at representative supported resolutions.

Check for:

- Clipped content.
- Overlapping elements.
- Incorrect alignment.
- Excessive spacing.
- Unreadable text.
- Unavailable controls.
- Unexpected layout shifts.

## 19. Accessibility Standards

Interfaces SHOULD support players with different visual, motor, cognitive, and sensory needs.

Consider:

- Readable typography.
- Appropriate contrast.
- Scalable text where supported.
- Color-independent information.
- Clear interaction states.
- Consistent navigation.
- Input customization.
- Reduced motion.
- Subtitle customization.
- Adjustable interface opacity or size where appropriate.
- Avoiding unnecessary time pressure.
- Clear error recovery.

Accessibility requirements SHOULD be established at the project level and validated throughout development.

## 20. Visual Asset Requirements

UI visual assets MUST follow the relevant studio art asset standards.

This includes:

- Icons.
- Illustrations.
- Panels.
- Backgrounds.
- Borders.
- Decorative elements.
- Interface textures.
- Fonts.
- Visual effects.

Assets MUST:

- Follow the project's visual identity.
- Use appropriate dimensions and formats.
- Remain readable at their intended size.
- Be organized according to the feature-oriented project structure.
- Respect licensing and attribution requirements.
- Be technically suitable for the target platform.

Relevant requirements are defined in `ART_ASSET_STANDARDS.md` and `ART_PIPELINE.md`.

## 21. UI State and Reliability

Interface presentation MUST accurately reflect the underlying game state.

Examples include:

- Current health.
- Available resources.
- Inventory contents.
- Selected equipment.
- Quest progress.
- Settings values.
- Interaction availability.

Avoid visual states that imply an action succeeded when the underlying system rejected or failed to process it.

When an action fails, the interface SHOULD provide appropriate feedback.

Interface elements SHOULD remain synchronized with their owning feature or system.

Technical state management and communication MUST follow the relevant architecture, GDScript, and event and signal standards.

## 22. UI Review and Acceptance

Interfaces SHOULD be reviewed before being considered complete.

### 22.1. Visual Review

Verify that the interface:

- Follows the approved visual identity.
- Has a clear information hierarchy.
- Uses consistent typography and colors.
- Has appropriate spacing and alignment.
- Uses readable icons and symbols.
- Has consistent component styling.
- Avoids unnecessary visual clutter.
- Works in its intended gameplay context.

### 22.2. Usability Review

Verify that:

- Available actions are understandable.
- Navigation is predictable.
- Interactive states are visible.
- Feedback is clear.
- Errors can be understood and recovered from.
- Important information is easy to find.
- Controls are appropriate for supported input methods.

### 22.3. Technical Review

Verify that:

- Layouts work at supported resolutions.
- Text is not clipped.
- Components do not overlap unexpectedly.
- Input works correctly.
- UI state reflects the underlying game state.
- Animations do not interfere with interaction.
- No unintended visual or runtime errors are introduced.

### 22.4. Acceptance

An interface SHOULD be considered accepted when its applicable visual, usability, accessibility, and technical requirements are satisfied.

AI agents MAY perform preliminary reviews but MUST NOT independently approve significant changes to the established interface design system.

## 23. AI-Assisted UI/UX Work

AI agents assisting with interface design or implementation MUST:

1. Read the project's approved UI/UX design requirements.
2. Follow the established interface design system.
3. Reuse existing components when appropriate.
4. Follow project naming and feature-oriented organization conventions.
5. Preserve existing interface behavior outside the approved task scope.
6. Consider supported resolutions and input methods.
7. Maintain accessibility requirements.
8. Validate visual and functional behavior where possible.
9. Report unresolved issues and limitations honestly.
10. Request approval before making significant changes to the established interface design system.

AI agents MUST NOT:

- Introduce arbitrary visual styles without justification.
- Duplicate existing components unnecessarily.
- Remove important interface information without approval.
- Assume that visual correctness guarantees usability.
- Claim that an interface has been tested when it has not.
- Mark subjective design decisions as approved without the appropriate authority.

## 24. UI/UX Review Checklist

Before accepting an interface, verify the applicable requirements:

- [ ] The interface has a clear purpose.
- [ ] It follows the approved interface design system.
- [ ] Information hierarchy is clear.
- [ ] Typography is readable and consistent.
- [ ] Colors and contrast are appropriate.
- [ ] Icons and symbols are understandable.
- [ ] Interactive elements have clear states.
- [ ] Navigation is predictable.
- [ ] Feedback is understandable.
- [ ] Layout and spacing are consistent.
- [ ] Important gameplay information remains visible.
- [ ] Supported input methods are handled correctly.
- [ ] Supported resolutions are validated.
- [ ] Accessibility requirements are considered.
- [ ] Animations do not interfere with interaction.
- [ ] UI state accurately reflects game state.
- [ ] Visual assets follow art asset standards.
- [ ] Relevant documentation has been updated.

Not every checklist item applies to every interface. Non-applicable requirements SHOULD be identified rather than treated as failures.

## 25. Exceptions

Exceptions to these standards MAY be permitted when justified by:

- Specific gameplay requirements.
- Artistic direction.
- Technical limitations.
- Platform constraints.
- Accessibility requirements.
- Experimental interface approaches.

Exceptions MUST:

- Have a clear justification.
- Identify affected interfaces or features.
- Describe relevant risks and consequences.
- Receive project owner approval when they affect established studio or project standards.
- Be documented when they have lasting impact.

Temporary exceptions SHOULD be reviewed before final release.

## 26. Related Documents

- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`
- `docs/01_game_design_guidelines/PLAYER_EXPERIENCE_GUIDELINES.md`
- `docs/01_game_design_guidelines/UI_UX_DESIGN_GUIDELINES.md`
- `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`
- `docs/02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md`
- `docs/02_technical_standards/GDSCRIPT_STANDARDS.md`
- `docs/03_art_audio_standards/ART_ASSET_STANDARDS.md`
- `docs/03_art_audio_standards/ART_PIPELINE.md`
- `docs/03_art_audio_standards/ANIMATION_STANDARDS.md`

## 27. Maintenance

These standards SHOULD be reviewed periodically and updated when:

- Studio interface design practices change.
- New interface patterns or interaction methods are introduced.
- Supported display configurations change.
- Accessibility requirements evolve.
- Recurring usability or visual consistency issues are identified.
- Engine capabilities or technical requirements change.
- Improvements to interface design and review practices are identified.

Changes MUST preserve the distinction between reusable studio standards and project-specific interface design decisions.

The project owner is responsible for approving changes to these standards.