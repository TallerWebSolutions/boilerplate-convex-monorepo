Run:

1. `npx create-expo-app .`

2. `npm install convex`

3. Add the Convex provider in to the root file `app/_layout.tsx`:
````typescript
// app/_layout.tsx
import { ConvexProvider, ConvexReactClient } from "convex/react";
import { Stack } from "expo-router";

const convex = new ConvexReactClient(process.env.EXPO_PUBLIC_CONVEX_URL!, {
  unsavedChangesWarning: false,
});

export default function RootLayout() {
  return (
    <ConvexProvider client={convex}>
      <Stack>
        <Stack.Screen name="index" />
      </Stack>
    </ConvexProvider>
  );
}
````