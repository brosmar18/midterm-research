# Setting Up Clerk in a Next.js Application

1. **Create a Clerk Account**: Sign up for an account at [Clerk](https://clerk.com/).

2. **Create a New Application**: In your Clerk dashboard, create a new application.

3. **Configure User Sign-In Methods**: Choose the preferred methods for user sign-in within your application.

4. **Select Framework**: Navigate to the "Quickstarts" menu and select the Next.js framework for integration guidance.

5. **Environment File Setup**: In the root directory of your Next.js application, create a `.env.local` file.

6. **Add Environment Variables**: Insert the following environment variables into the `.env.local` file, replacing the placeholders with your actual Clerk keys.
    ```
    NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=<your_publishable_key>
    CLERK_SECRET_KEY=<your_secret_key>
    ```

7. **Install Clerk SDK**: Run the following command in your project directory to install the Clerk package:
    ```
    npm install @clerk/nextjs
    ```

8. **Update App Layout**: Modify your `app/Layout.tsx` file to include the `<ClerkProvider>` component. This wraps the entire application with Clerk's context.
    ```tsx
    import { ClerkProvider } from '@clerk/nextjs'

    export default function RootLayout({ children }: { children: React.ReactNode }) {
      return (
        <ClerkProvider>
          <html lang="en">
            <body>{children}</body>
          </html>
        </ClerkProvider>
      )
    }
    ```

9. **Create Middleware for Authentication**: Set up a `middleware.ts` file to manage route authentication. Use the following template and modify as necessary:
    ```ts
    import { authMiddleware } from "@clerk/nextjs";
    
    // Protects all routes including API/TRPC routes. Modify for public routes.
    export default authMiddleware({});
    
    export const config = {
      matcher: ['/((?!.+\\.[\\w]+$|_next).*)', '/', '/(api|trpc)(.*)'],
    };
    ```

10. **Test Authentication Flow**: Run your application and navigate to `localhost:<PORT>`. You should be redirected to the sign-in page.

11. **Customize Middleware**: Update the `middleware.ts` file to include `publicRoutes` and `ignoredRoutes` as per your application's requirements.

12. **Implement SignedIn and SignedOut Components**: Utilize `<SignedIn>` and `<SignedOut>` components from Clerk to manage content visibility based on the user's authentication status.

#### Citation
[Clerk Documentation - Quickstart for Next.js](https://clerk.com/docs/quickstarts/nextjs)
