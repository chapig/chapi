<script lang="ts">
    import Header from '$lib/components/header/header.svelte';
	import { page } from '$app/stores';
    import { Button } from "$lib/components/ui/button";
    import * as Card from "$lib/components/ui/card";
    import { Input } from "$lib/components/ui/input";
    import { Label } from "$lib/components/ui/label";
    
    import { Phone, Linkedin, Mail, Download, Eye } from "lucide-svelte";
  
</script>

<Header />

  
<div class="error-page">
<Eye class="icon"/>
<h1>{$page.status}</h1> 
<p>The page you were looking for could not be found.</p>
</div>
  
  <style>
    .error-page {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      min-height: 100vh; /* Center vertically */
      text-align: center;
    }
  
    .icon {
      width: 64px;
      height: 64px;
      color: #0dff00; /* Customize color */
      margin-bottom: 20px;
    }
  
    h1 {
      font-size: 3rem;
      font-weight: bold;
      margin-bottom: 10px;
    }
  
    p {
      font-size: 1.2rem;
    }
  </style>