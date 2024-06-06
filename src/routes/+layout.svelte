<script lang="ts">
    import { ModeWatcher } from "mode-watcher";
    import Menu from "lucide-svelte/icons/menu";
    import { Button } from "$lib/components/ui/button";
    import * as Sheet from "$lib/components/ui/sheet";
    import { Moon, Sun } from "lucide-svelte";
    import { toggleMode } from "mode-watcher";
    import "../app.css";
  </script>
  
  
<ModeWatcher />
<slot />

  
 