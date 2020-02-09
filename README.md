# Typescript Linting Styling Storybook Custom CRA Template

Includes TypeScript,  Prettier,  Eslint,  Styled-Components,  Styled-Systems, Storybook.

## Storybook

To add a story to the storybook add a `<component name>.stories.tsx` file in the [CSF format](https://storybook.js.org/docs/formats/component-story-format/).

## Linting

Add the following property to the VSCode Settings (JSON) to enable prettier and eslint linting automatically on document save. On Mac `CMD + Shift + P` and select `Preferences: Open Settings (JSON)`.

```json
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true
}
```

## Styling

Customize `[src/]utils/theme.ts` as described at the [styled-systems docs](https://styled-system.com/theme-specification).
The following creates a box with a padding of `16px` based on the theme value.

```tsx
const PaddedBox: React.FC = ({ children }) => {
  return <Box p={3}>{children}</Box>;
};

// [src/]utils/theme.ts
// ...
const space = [0, 4, 8, 16, 32, 64, 128, 256, 512];
```

The `ThemeDecorator` is applied as a wrapper in the `AppProvider` component at `[src/]components/AppProvider.tsx`.

