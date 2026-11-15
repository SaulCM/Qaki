# UI/UX Design Guidelines

## 1. Purpose

This document defines reusable guidelines for designing, implementing, and evaluating user interfaces (UI) and user experiences (UX) in games developed by the studio.

Its purpose is to ensure that interfaces are intuitive, consistent, accessible, responsive, and aligned with the intended gameplay experience.

UI and UX design MUST support gameplay rather than unnecessarily interrupt, obscure, or complicate it.

## 2. Scope

These guidelines cover:

- User interface design principles.
- User experience and interaction design.
- Heads-up displays (HUDs).
- Main menus and navigation.
- In-game menus and interfaces.
- Inventory and equipment interfaces.
- Dialogue and interaction interfaces.
- Notifications and feedback.
- Input methods and controls.
- Information hierarchy and readability.
- Accessibility and usability.
- Responsive layouts and different display configurations.
- UI state management and interaction behavior.
- UI/UX testing and validation.

These guidelines apply to all player-facing interfaces, including menus, overlays, interactive elements, and gameplay-related information displays.

They establish design expectations rather than prescribing a specific visual style, UI framework, or implementation architecture.

## 3. Core UI/UX Principles

### 3.1 Player-Centered Design

Interfaces MUST be designed around player needs, capabilities, and gameplay context.

Designers SHOULD consider:

- What information players need.
- When they need that information.
- How they access it.
- What actions they are expected to perform.
- What feedback they need after interacting.
- How much attention the interface requires.

Interfaces SHOULD minimize unnecessary cognitive effort.

### 3.2 Clarity

Every interface element SHOULD communicate its purpose clearly.

Players SHOULD be able to understand:

- What an element represents.
- What actions are available.
- What happens when an action is performed.
- Which elements are interactive.
- Which states are active, disabled, selected, or unavailable.

Ambiguous labels, inconsistent symbols, and unexplained interactions SHOULD be avoided.

### 3.3 Consistency

Interfaces MUST use consistent interaction patterns, terminology, visual language, and behavior.

Consistency SHOULD be maintained across:

- Menus.
- HUD elements.
- Buttons and controls.
- Navigation.
- Icons.
- Notifications.
- Interaction prompts.
- Input behavior.
- Feedback and animations.

Exceptions MAY be introduced when they provide a clear usability or gameplay benefit.

### 3.4 Efficiency

Interfaces SHOULD allow players to complete common actions with minimal unnecessary steps.

Designers SHOULD:

- Minimize repetitive interactions.
- Avoid unnecessary confirmation dialogs.
- Provide useful shortcuts where appropriate.
- Keep frequently used information accessible.
- Avoid deeply nested navigation.
- Preserve relevant context when moving between interfaces.

Efficiency MUST NOT compromise clarity or prevent meaningful player decisions.

### 3.5 Feedback

Every meaningful player interaction MUST produce appropriate feedback.

Feedback SHOULD communicate:

- Whether an action was recognized.
- Whether it succeeded or failed.
- What changed as a result.
- Whether additional input is required.
- Whether the game is processing an action.

Feedback may be visual, audio, textual, or haptic where supported.

### 3.6 Context Awareness

Interfaces SHOULD adapt to the current gameplay context.

Information and controls SHOULD be presented according to:

- Current game state.
- Player activity.
- Available interactions.
- Relevant objectives.
- Selected objects or entities.
- Current input method.

Context-sensitive interfaces SHOULD remain predictable and avoid unexpected changes in control behavior.

### 3.7 Minimalism With Purpose

Interfaces SHOULD display the information necessary for the current context.

Designers SHOULD avoid:

- Decorative elements that reduce readability.
- Redundant information.
- Unnecessary visual effects.
- Excessive notifications.
- Unneeded interface complexity.
- Persistent elements that provide little value.

Minimalism MUST NOT remove information necessary for player understanding or decision-making.

## 4. Information Architecture and Hierarchy

### 4.1 Information Architecture

Information architecture defines how interface information is organized and accessed.

Designers SHOULD group information according to:

- Purpose.
- Gameplay function.
- Player tasks.
- Relationships between information.
- Frequency of use.
- Context.

Related information SHOULD be grouped together.

Navigation structures SHOULD reflect the player's mental model rather than internal technical implementation.

### 4.2 Visual Hierarchy

Visual hierarchy determines which interface elements attract attention first.

Designers SHOULD use consistent differences in:

- Size.
- Position.
- Contrast.
- Typography.
- Spacing.
- Color.
- Visual emphasis.
- Animation.

The most important information SHOULD be visually distinguishable without overwhelming other relevant elements.

### 4.3 Information Priority

Information SHOULD be prioritized according to its importance and urgency.

A useful classification is:

- **Critical:** required immediately to avoid failure or understand an important event.
- **Important:** relevant to current decisions or gameplay objectives.
- **Contextual:** useful under specific gameplay conditions.
- **Supplementary:** optional information that does not require immediate attention.

Interface elements SHOULD reflect their information priority.

### 4.4 Progressive Disclosure

Progressive disclosure presents information when it becomes relevant rather than exposing all available information simultaneously.

Designers SHOULD use it when:

- Interfaces contain many options.
- Players are learning a system.
- Advanced information is not needed immediately.
- Context determines which details are useful.

Essential information MUST remain discoverable and accessible.

## 5. HUD Design

### 5.1 HUD Purpose

The heads-up display communicates relevant gameplay information without requiring players to leave the active gameplay experience.

HUD elements SHOULD support immediate awareness and decision-making.

Examples include:

- Health and survival status.
- Resources.
- Ammunition.
- Objectives.
- Navigation information.
- Interaction prompts.
- Status effects.
- Relevant ability availability.

Not every game requires a persistent HUD.

HUD complexity SHOULD be proportional to the information required by the gameplay.

### 5.2 HUD Prioritization

HUD elements SHOULD be prioritized according to their gameplay relevance.

Critical information SHOULD be easy to identify.

Supplementary information MAY be displayed contextually or through secondary interfaces.

Designers SHOULD avoid displaying every possible gameplay statistic simultaneously.

### 5.3 HUD Placement

HUD elements SHOULD be positioned to:

- Preserve visibility of important gameplay areas.
- Avoid covering critical world objects.
- Maintain consistent locations.
- Reduce unnecessary eye movement.
- Remain readable at supported resolutions.

Important elements SHOULD NOT be placed where they are frequently obscured by gameplay activity.

### 5.4 Dynamic HUD Behavior

HUD elements MAY appear, disappear, or change according to gameplay context.

Examples include:

- Showing interaction prompts near usable objects.
- Displaying health information during combat.
- Showing resource information when relevant.
- Temporarily emphasizing critical warnings.

Dynamic behavior MUST remain predictable.

Important information SHOULD NOT disappear before players have a reasonable opportunity to process it.

### 5.5 HUD Customization

When appropriate, games SHOULD support customization such as:

- HUD scaling.
- Element positioning.
- Visibility toggles.
- Opacity adjustments.
- Simplified HUD modes.

Customization SHOULD preserve the functionality and readability of essential information.

## 6. Menus and Navigation

### 6.1 Menu Structure

Menus SHOULD have a clear and understandable hierarchy.

Common menu categories include:

- Main menu.
- Pause menu.
- Settings.
- Inventory.
- Character or equipment management.
- Map and navigation.
- Journal or objectives.
- Save and load interfaces.

Menu structures MUST reflect the actual features and needs of the game.

Unnecessary menu layers SHOULD be avoided.

### 6.2 Navigation Consistency

Navigation behavior MUST remain consistent across menus.

Designers SHOULD define:

- How players enter a menu.
- How players move between sections.
- How players return to previous screens.
- How selection is indicated.
- How focus changes.
- How unavailable options behave.

The same navigation action SHOULD produce the same expected result unless the context clearly requires different behavior.

### 6.3 Back and Cancel Behavior

Every navigable interface SHOULD define predictable back and cancel behavior.

The back action SHOULD:

- Return to the previous interface when appropriate.
- Close the active overlay when appropriate.
- Cancel the current operation when supported.
- Avoid unexpectedly discarding player changes.

Destructive actions MUST NOT be triggered by ambiguous back or cancel behavior.

### 6.4 Pause and Gameplay Continuity

Designers MUST define how menus affect gameplay.

Possible behaviors include:

- Fully pausing the game.
- Pausing selected systems.
- Allowing gameplay to continue.
- Opening an in-world interface without interruption.

The selected behavior MUST be consistent with the game's intended experience.

## 7. Interaction Design

### 7.1 Interaction Clarity

Interactive elements MUST communicate that they can be used.

Players SHOULD be able to identify:

- Available interactions.
- Required input.
- Interaction range or conditions.
- Current interaction state.
- Expected outcome.

Interaction prompts SHOULD be contextual and avoid unnecessary screen clutter.

### 7.2 Interaction States

Interactive elements SHOULD define their relevant states.

Common states include:

- Idle.
- Focused.
- Hovered, where supported.
- Pressed.
- Selected.
- Disabled.
- Loading.
- Successful.
- Failed.

State changes MUST be visually or otherwise perceptibly communicated.

### 7.3 Action Confirmation

Confirmation SHOULD be required when an action is:

- Irreversible.
- Destructive.
- Expensive.
- Likely to cause significant loss.
- Difficult to recover from.

Routine actions SHOULD NOT require unnecessary confirmation.

Confirmation messages MUST explain the consequence of the action.

### 7.4 Error Prevention and Recovery

Interfaces SHOULD prevent common player errors where reasonably possible.

Designers SHOULD consider:

- Valid input restrictions.
- Clear action requirements.
- Disabled states for unavailable actions.
- Confirmation for destructive operations.
- Undo or recovery options where appropriate.
- Clear error messages.

When an error occurs, players SHOULD understand what happened and how to recover when recovery is possible.

### 7.5 Interaction Responsiveness

Interfaces SHOULD respond promptly to player input.

Input SHOULD NOT be silently ignored.

When an operation requires time, the interface SHOULD communicate that it is processing.

Repeated input MUST NOT accidentally trigger duplicate actions unless that behavior is intentional.

## 8. Input and Control Design

### 8.1 Input Consistency

Input behavior MUST remain consistent throughout the game.

Designers SHOULD define:

- Primary and secondary actions.
- Navigation controls.
- Interaction controls.
- Confirmation and cancellation.
- Context-sensitive inputs.
- Input priority when actions overlap.

Controls SHOULD be documented in a way players can understand.

### 8.2 Input Mapping

Where supported, players SHOULD be able to remap relevant controls.

Control configuration SHOULD account for:

- Keyboard and mouse.
- Game controllers.
- Alternative input devices.
- Input conflicts.
- Unsupported or unavailable actions.

Remapping MUST preserve required gameplay functionality.

### 8.3 Input Method Awareness

When multiple input methods are supported, interfaces SHOULD adapt their prompts to the active input method.

For example:

- Keyboard keys when using keyboard input.
- Controller buttons when using a gamepad.
- Appropriate touch controls when using touch input.

Input prompts MUST accurately reflect the current control configuration.

### 8.4 Focus and Navigation

Interfaces designed for controller or keyboard navigation MUST provide predictable focus behavior.

Players SHOULD always be able to identify the currently focused element.

Focus navigation SHOULD avoid unexpected jumps, inaccessible elements, and situations where focus becomes lost.

## 9. Visual Design and Readability

### 9.1 Visual Consistency

The visual language SHOULD reinforce the game's identity.

Designers SHOULD define reusable conventions for:

- Colors.
- Typography.
- Iconography.
- Borders.
- Shapes.
- Spacing.
- Panels.
- Buttons.
- Visual states.
- Animations.

Visual consistency SHOULD be maintained across all player-facing interfaces.

### 9.2 Typography

Typography MUST prioritize readability.

Designers SHOULD consider:

- Font size.
- Font weight.
- Line spacing.
- Character spacing.
- Text contrast.
- Text hierarchy.
- Localization requirements.
- Supported display resolutions.

Decorative fonts SHOULD NOT be used for information that players must read quickly or accurately.

### 9.3 Color Usage

Colors SHOULD have consistent meanings throughout the interface.

For example, a game MAY establish colors for:

- Health.
- Resources.
- Warnings.
- Positive feedback.
- Negative feedback.
- Interactive elements.
- Disabled states.

Color MUST NOT be the only method used to communicate critical information.

### 9.4 Iconography

Icons SHOULD communicate recognizable and consistent meanings.

Designers SHOULD:

- Reuse established icon meanings.
- Avoid unnecessary icon variations.
- Provide labels or tooltips when meanings are unclear.
- Maintain visual consistency.
- Validate icon readability at actual display sizes.

Important actions SHOULD NOT rely exclusively on unfamiliar symbols.

### 9.5 Contrast and Backgrounds

Text and important interface elements MUST maintain sufficient contrast against their backgrounds.

Designers SHOULD consider interface readability over:

- Bright environments.
- Dark environments.
- Visually complex backgrounds.
- Changing gameplay scenes.
- Different display configurations.

Background panels, shadows, outlines, or other treatments MAY be used when necessary to preserve readability.

## 10. Feedback and Notifications

### 10.1 Feedback Types

Interfaces SHOULD provide appropriate feedback for:

- Player actions.
- System responses.
- State changes.
- Objective progress.
- Reward acquisition.
- Errors.
- Warnings.
- Important gameplay events.

Feedback SHOULD be proportional to the importance of the event.

### 10.2 Notification Priority

Notifications SHOULD be classified according to importance.

For example:

- Critical warnings.
- Important gameplay events.
- Routine confirmations.
- Optional informational messages.

Critical notifications SHOULD be distinguishable from routine messages.

### 10.3 Notification Timing

Notifications MUST appear at appropriate times.

Designers SHOULD consider:

- Current gameplay intensity.
- Player attention.
- Event importance.
- Notification duration.
- Whether the player can dismiss the notification.
- Whether the information needs to remain available.

Important information SHOULD remain accessible after temporary notifications disappear.

### 10.4 Notification Overload

The interface SHOULD avoid overwhelming players with simultaneous or repetitive notifications.

Designers SHOULD:

- Group related notifications when appropriate.
- Prioritize important events.
- Avoid repeating unchanged information.
- Limit unnecessary animations.
- Provide notification settings when useful.

## 11. Dialogue and Text Interfaces

### 11.1 Dialogue Readability

Dialogue interfaces MUST make spoken or displayed text easy to read.

Designers SHOULD consider:

- Speaker identification.
- Text presentation.
- Dialogue pacing.
- Character voice.
- Text size.
- Line length.
- Background contrast.
- Player reading speed.

### 11.2 Dialogue Choices

Dialogue choices SHOULD communicate their intended meaning.

When choices affect narrative outcomes, the game SHOULD provide enough context for players to make informed decisions.

Designers SHOULD avoid misleading choices unless uncertainty is an intentional narrative design objective.

### 11.3 Text Speed and Control

Where appropriate, players SHOULD be able to control dialogue presentation through:

- Text speed.
- Immediate text display.
- Dialogue advancement.
- Auto-advance settings.
- Dialogue history.

Important dialogue information SHOULD remain accessible when practical.

### 11.4 Localization

Text interfaces SHOULD accommodate localization requirements.

Designers SHOULD avoid fixed layouts that break when translated text becomes longer or shorter.

Text rendering MUST support the languages and character sets required by the project.

## 12. Inventory and Management Interfaces

Inventory and management interfaces SHOULD make it easy to inspect, compare, organize, and use game items.

Designers SHOULD consider:

- Item identification.
- Item categories.
- Sorting and filtering.
- Quantity information.
- Item descriptions.
- Equipment comparisons.
- Available capacity.
- Selection states.
- Item actions.
- Confirmation for destructive operations.

The interface SHOULD communicate the consequences of item-related actions.

Complex inventory systems SHOULD prioritize common player tasks and avoid unnecessary navigation.

## 13. Accessibility and Inclusivity

UI/UX design MUST consider accessibility from the beginning of development rather than treating it as a final presentation adjustment.

Where appropriate and feasible, games SHOULD support:

### 13.1 Visual Accessibility

- Adjustable text sizes.
- High-contrast options.
- Colorblind-friendly indicators.
- Clear focus states.
- Readable typography.
- Reduced visual clutter.

### 13.2 Auditory Accessibility

- Subtitles.
- Adjustable audio levels.
- Visual alternatives for important audio cues.
- Distinguishable audio feedback.

### 13.3 Motor Accessibility

- Remappable controls.
- Adjustable input sensitivity.
- Toggle options instead of mandatory hold actions where appropriate.
- Reduced dependence on rapid repeated inputs.
- Flexible interaction timing where appropriate.

### 13.4 Cognitive Accessibility

- Clear instructions.
- Consistent terminology.
- Predictable navigation.
- Manageable information density.
- Optional tutorials or reference information.
- Clear error messages.

### 13.5 Motion and Visual Effects

Where appropriate, provide options for:

- Reduced screen shake.
- Reduced flashing effects.
- Reduced motion.
- Adjustable camera-related effects.
- Reduced visual intensity.

Accessibility features SHOULD be validated in actual gameplay contexts.

## 14. Responsive Layout and Display Support

Interfaces MUST be designed for the project's supported display configurations.

Designers SHOULD consider:

- Resolution changes.
- Aspect ratio differences.
- UI scaling.
- Safe areas.
- Text overflow.
- Panel resizing.
- Element anchoring.
- Minimum readable sizes.

Layouts SHOULD adapt without overlapping important elements or hiding essential information.

Designers SHOULD validate interfaces at representative minimum and maximum supported resolutions.

If the game targets only a specific display configuration, that constraint SHOULD be documented.

## 15. Animation and Transitions

UI animations SHOULD communicate state changes, hierarchy, and interaction feedback.

Animations MAY be used for:

- Opening and closing menus.
- Highlighting important information.
- Showing reward acquisition.
- Transitioning between screens.
- Confirming player actions.
- Communicating warnings.

Animations MUST NOT unnecessarily delay player input or obstruct access to important information.

Designers SHOULD consider:

- Duration.
- Easing.
- Motion consistency.
- Frequency.
- Visual intensity.
- Interruptibility.
- Accessibility.

Repeated animations SHOULD NOT become disruptive during normal gameplay.

## 16. UI State and Interaction Reliability

Interfaces MUST accurately represent the underlying game state.

Designers and developers MUST consider:

- Active and inactive states.
- Selected elements.
- Available and unavailable actions.
- Loading and processing states.
- Error states.
- Empty states.
- Persistent interface settings.
- State changes caused by gameplay events.

The interface MUST NOT display outdated or contradictory information.

When gameplay state changes, relevant UI elements SHOULD update reliably.

UI interactions that modify persistent game data MUST follow the project's data integrity and save management standards.

## 17. UI/UX Documentation

Significant interfaces SHOULD have a documented specification.

A UI/UX specification SHOULD include:

| Element | Description |
|---|---|
| Interface name | Name of the interface or screen |
| Purpose | Why the interface exists |
| Context | When and where it is accessed |
| Target users | Relevant player needs and assumptions |
| Information hierarchy | Information displayed and its priority |
| Layout | Element arrangement and structure |
| Interactions | Available actions and expected behavior |
| Navigation | Entry, exit, focus, and navigation rules |
| States | Idle, focused, selected, disabled, loading, error, and other relevant states |
| Feedback | Visual, audio, textual, or haptic responses |
| Inputs | Supported input methods and mappings |
| Accessibility | Relevant accessibility considerations |
| Responsive behavior | Supported resolutions and layout adaptations |
| Dependencies | Related gameplay systems and data |
| Validation | How usability and functionality will be tested |

Wireframes, mockups, interaction flows, and state diagrams SHOULD be included when they clarify complex interfaces.

Visual mockups MUST NOT be treated as complete functional specifications when interaction behavior remains undefined.

## 18. Testing and Validation

UI/UX MUST be validated throughout development.

### 18.1 Functional Validation

Verify that:

- Interface elements behave as specified.
- Navigation works correctly.
- Inputs are recognized.
- Focus and selection states are correct.
- Buttons and controls perform their intended actions.
- Interface information reflects current game state.
- Notifications appear under the correct conditions.
- Settings persist when required.
- Invalid actions are handled appropriately.

### 18.2 Visual Validation

Verify that:

- Text is readable.
- Important information is visible.
- Elements do not overlap unexpectedly.
- Icons and visual states are consistent.
- Layouts adapt to supported resolutions.
- Animations behave correctly.
- Interface elements remain distinguishable against gameplay backgrounds.

### 18.3 Usability Validation

Playtesting SHOULD evaluate whether players can:

- Understand interface organization.
- Find important information.
- Complete common tasks.
- Recognize available interactions.
- Recover from mistakes.
- Navigate without unnecessary confusion.
- Understand important feedback.

### 18.4 Accessibility Validation

Verify relevant accessibility features, including:

- Text readability.
- Contrast.
- Input remapping.
- Focus visibility.
- Subtitle behavior.
- Reduced motion options.
- Non-color-dependent information.

### 18.5 Contextual Validation

Interfaces SHOULD be tested during actual gameplay rather than exclusively in isolated menu scenes.

Validation SHOULD include relevant contexts such as:

- Combat.
- Exploration.
- Dialogue.
- Inventory management.
- Loading transitions.
- Pause and resume.
- Different gameplay states.

## 19. Iterative UI/UX Design

UI/UX design SHOULD follow an iterative process.

A recommended workflow is:

1. Identify the player task or information need.
2. Define the interface purpose.
3. Establish the information hierarchy.
4. Design the navigation and interaction flow.
5. Create a wireframe or prototype.
6. Validate usability and clarity.
7. Establish visual design conventions.
8. Implement the interface.
9. Test functionality and presentation.
10. Conduct contextual playtesting.
11. Refine based on observed problems.
12. Update the interface specification.

Designers SHOULD validate interface structure and interaction behavior before investing heavily in visual polish.

Significant interface changes MUST be evaluated for their impact on related screens and established interaction patterns.

## 20. Godot Implementation Considerations

UI implementation MUST follow the project's approved technical and architectural standards.

The following principles SHOULD guide implementation:

- Keep UI functionality within the feature that owns the relevant interface.
- Use reusable interface components when they provide genuine value.
- Keep presentation logic separate from gameplay rules where appropriate.
- Use Godot Control nodes and containers according to their intended responsibilities.
- Prefer container-based layouts over unnecessary fixed positioning.
- Use theme resources and shared style definitions to maintain visual consistency.
- Avoid duplicating common interaction behavior across unrelated interfaces.
- Handle focus and input navigation explicitly.
- Ensure UI state reflects authoritative gameplay state.
- Avoid tightly coupling UI elements to unrelated gameplay internals.
- Use signals or established interfaces for communication between UI and gameplay features.
- Validate interface behavior when scenes are opened, closed, or reloaded.
- Avoid unnecessary processing or repeated updates when interface data has not changed.

UI implementation SHOULD remain modular, testable, and maintainable without introducing unnecessary abstraction.

## 21. AI-Assisted UI/UX Design Requirements

AI agents assisting with UI/UX design MUST:

1. Read this document and relevant game-specific design specifications.
2. Identify the player task and interface purpose before proposing layouts.
3. Respect the game's established visual identity and interaction conventions.
4. Avoid introducing unnecessary interface elements.
5. Consider accessibility and supported input methods.
6. Evaluate navigation and interaction states.
7. Check consistency with existing interfaces.
8. Consider different resolutions and display configurations.
9. Distinguish visual mockups from functional interaction specifications.
10. Document assumptions and unresolved design questions.
11. Propose significant changes to established UI patterns for human approval.
12. Never mark unapproved visual or interaction decisions as approved.

AI-generated layouts, interaction flows, and UI implementations MUST be reviewed and validated in the actual game.

## 22. UI/UX Design Review Checklist

Before approving an interface, verify the following:

### Purpose and Structure
- [ ] The interface has a clear purpose.
- [ ] Its information hierarchy is defined.
- [ ] Navigation is understandable.
- [ ] Important information is easy to locate.
- [ ] Unnecessary interface elements have been avoided.

### Interaction
- [ ] Interactive elements communicate their purpose.
- [ ] Available states are defined.
- [ ] Input behavior is consistent.
- [ ] Back and cancel behavior is predictable.
- [ ] Errors and destructive actions are handled appropriately.
- [ ] Feedback is provided for meaningful interactions.

### Visual Design
- [ ] Typography is readable.
- [ ] Visual hierarchy is clear.
- [ ] Colors and icons are consistent.
- [ ] Contrast is sufficient.
- [ ] Animations support rather than obstruct interaction.
- [ ] Layouts work at supported resolutions.

### Accessibility
- [ ] Relevant accessibility needs have been considered.
- [ ] Important information does not rely exclusively on color.
- [ ] Input accessibility has been evaluated.
- [ ] Text and visual feedback are readable.
- [ ] Motion and flashing effects have been considered.

### Validation
- [ ] Functional behavior has been tested.
- [ ] Visual presentation has been tested.
- [ ] Usability has been evaluated.
- [ ] Relevant gameplay contexts have been tested.
- [ ] The interface specification is up to date.

## 23. Related Documents

Consult the following documents when relevant:

- `DESIGN_PRINCIPLES.md`
- `GAMEPLAY_DESIGN_GUIDELINES.md`
- `PLAYER_EXPERIENCE_GUIDELINES.md`
- `CORE_LOOP_DESIGN_GUIDELINES.md`
- `MECHANIC_DESIGN_GUIDELINES.md`
- `PROGRESSION_DESIGN_GUIDELINES.md`
- `REWARD_DESIGN_GUIDELINES.md`
- `NARRATIVE_DESIGN_GUIDELINES.md`

Technical implementation MUST also follow the applicable studio technical standards and project-specific architecture documentation.

## 24. Maintenance

This document SHOULD be reviewed periodically and updated when:

- Studio-wide UI/UX practices change.
- New interface design requirements become relevant.
- Existing guidance becomes unclear or outdated.
- Repeated usability or implementation problems reveal missing guidance.

Changes MUST preserve consistency with the studio documentation hierarchy and other game design guidelines.

Game-specific interface designs, wireframes, visual specifications, and interaction decisions MUST be documented in the relevant game project documentation rather than added to this reusable guideline.