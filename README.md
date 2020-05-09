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

Customize `[src/]utils/theme/default` (or more themes) as described at the [styled-systems docs](https://styled-system.com/theme-specification).
The following creates a box with a padding of `16px` based on the theme value.

```tsx
const PaddedBox: React.FC = ({ children }) => {
  return <Box p="M">{children}</Box>;
};

// [src/]utils/theme/default/space.ts
const space = {
  NONE: 0,
  XXS: 4,
  XS: 8,
  S: 12,
  M: 16,
  L: 24,
  XL: 32,
  XXL: 48,
  H: 64,
} as const;
// ...
```

The `ThemeDecorator` is applied as a wrapper in the `AppProvider` component at `[src/]components/AppProvider.tsx`.

The `Box` component is included and useful to extend for custom styled components.

## Misc

The `baseUrl` property in the `tsconfig.json` is set to `src`.
