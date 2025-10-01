# ADR 004: Frontend HTML, CSS (Tailwind)

**Date:** 2025-09-30  
**Status:** Proposed  

## Context  
We need to build the front end of our Chrome extension. The front end must be lightweight, responsive, and easy to maintain. Since the extension will be used by students across different devices and screen sizes, consistent styling and rapid development are important.  

## Decision  
We will implement the frontend using **HTML** and **CSS with TailwindCSS**. Tailwind was chosen for its utility-first approach, ease of customization, and ability to speed up development with pre-defined classes. It integrates well with modern Typescript frameworks and reduces the need for writing extensive custom CSS.  

## Consequences  
- **Positive:**  
  - Faster prototyping and development due to utility classes.  
  - Responsive design out-of-the-box.  
  - Consistent UI styling across components.  
  - Small learning curve for contributors already familiar with CSS.  

- **Negative:**  
  - Can lead to verbose HTML if not structured properly.  
  - Requires build tools (e.g., PostCSS, Vite) to optimize for production.  
  - Semantic CSS or other frameworks may be preferred.  

## Alternatives Considered  
- **Option A: Plain CSS:**  
  - Pros: No dependency on external frameworks, full control over styles.  
  - Cons: Slower development, more boilerplate, less maintainable for a growing project.  

- **Option B: Bootstrap:**  
  - Pros: Mature, widely adopted, offers prebuilt components.  
  - Cons: More opinionated, harder to fully customize, may feel heavy for a lightweight Chrome extension.  

## References
- [HTML Standard Documentation](https://html.spec.whatwg.org/)
- [CSS Documentation](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs/installation/using-postcss)