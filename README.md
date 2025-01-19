# PurgeCSS and Dynamically Added Tailwind Classes

This repository demonstrates a common issue encountered when using PurgeCSS with Tailwind CSS: the removal of classes that are added to the DOM dynamically.  PurgeCSS, while effective at removing unused CSS, might miss classes that are added after the initial page load.

This issue is particularly relevant when using frameworks such as Vue.js, React, or Svelte, where content is often updated dynamically.

**The Problem:**

Classes added to elements after PurgeCSS has analyzed the HTML may be missing from the final CSS output, leading to styling issues.

**The Solution:**

The solution is to ensure that PurgeCSS correctly identifies all the CSS classes that may be present in the application.  This typically requires using a mechanism to explicitly tell PurgeCSS which classes are dynamically generated, or to ensure those classes are added in a way that PurgeCSS can detect them.  This can often involve adjusting your build pipeline.