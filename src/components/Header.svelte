<script>
    export const segment = undefined;
  
    import {
      SkipToContent,
      Header,
    } from "carbon-components-svelte";

    import { getContext } from "svelte";
  
    const ctx = getContext("Theme");
  
    $: if (ctx) {
      ctx.dark.subscribe((value) => {
        //console.log("dark mode?", value);
      });
      ctx.light.subscribe((value) => {
        //console.log("light mode?", value);
      });
      ctx.updateVar("--cds-productive-heading-06-font-size", "4rem");
    }
  </script>
  
  <Header company="rstuff" platformName="Svelte Barcode Scanner" href="/">
    <div slot="skip-to-content">
      <SkipToContent />
    </div>
    
  </Header>
  