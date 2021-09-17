<script>
  import { init, register } from "svelte-i18n";

  register("en", () => import("../i18n/en.json"));
  register("pt", () => import("../i18n/pt.json"));

  init({
    fallbackLocale: "en",
    initialLocale: "en"
  });
</script>
