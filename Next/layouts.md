# Layouts in Next.js

## Overview
In Next.js, a layout is a shared UI component used across multiple pages, designed to maintain state and interactivity across navigations without re-rendering. 

## In Simple Terms
Layouts are like common frames or templates for pages, providing consistent design elements (like headers, or footers) across different pages. 

## Key Terms
- **Shared UI**: User interface elements shared between pages. 
- **State Preservation**: Maintaining data state during navigation. 
- **Nested Layouts**: Hierarchical organization of layouts. 

## Syntax
```tsx
// Define a layout in a `layout.js` file
export default function MyLayout({ children }) {
  return (
    <div>
      {/* Shared components */}
      {children}
    </div>
  );
}
```

## Example 
```tsx
import Footer from "@/components/shared/Footer"
import Header from "@/components/shared/Header"

export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <div className="flex h-screen flex-col">
      <Header />
      <main className="flex-1">{children}</main>
      <Footer />
    </div>
  )
}
```

### Breakdown 
- In this example, pages will share the `<Header />` and `<Footer />` components. 
- **Default export**: Layouts are exported as default React components. 
- **Children Prop**: Accepts child layouts or pages. 
- **Nesting**: Parent layouts wrap child layouts/pages. 
- **State and Interactivity**: Layouts preserve state and maintain interactive. 

## Summary
Layouts are essentia for creating a consistent UI across multiple pages, enabling state preservation and interactivity during navigation. They can be nested and are defined in `Layout.jsx` files, with the root layout being a special case that encompasses the entire app structure. 

#### Citations
[Next.js Documentation - Pages and Layouts](https://nextjs.org/docs/app/building-your-application/routing/pages-and-layouts)
