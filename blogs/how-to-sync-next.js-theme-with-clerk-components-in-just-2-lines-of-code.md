Switching between light and dark mode is cool — until you have to sync it across multiple integrations. If you’re using Next.js and Clerk, though, it’s a breeze! In just two lines of code, you can sync Clerk’s theme with Next.js and keep everything looking on point. Here’s the quick and easy way to make sure your theme is in harmony.

#### Before We Begin:

_Make sure you’ve installed next-themes and @clerk/themes:_
\`\`\`bash
npm install next-themes @clerk/themes
\`\`\`

#### The Magic Code

_Now, pop this into your Clerk component to sync its theme with your app’s theme. Below is an example using the UserProfile component._
\`\`\`tsx
"use client"
import { UserProfile } from "@clerk/nextjs";
import { dark } from "@clerk/themes";
import { useTheme } from "next-themes";
const UserProfilePage = () => {
const { resolvedTheme } = useTheme();
return (
<UserProfile
appearance={{
        baseTheme: resolvedTheme === "dark" ? dark : undefined,
      }}
path="/profile"
/>
);
};
export default UserProfilePage;
\`\`\`
With this, Clerk components will automatically switch between light and dark mode based on your app’s current theme. Clean, simple, and all in just two lines! \n
**Tech Stack :** Next.js , ShadCN UI , Clerk.js
