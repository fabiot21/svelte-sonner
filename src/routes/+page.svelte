<script lang="ts">
import { Toaster } from '$lib';
import type { Position as PositionType } from '$lib/types';
import Expand from '../components/Expand.svelte';
import Footer from '../components/Footer.svelte';
import Hero from '../components/Hero.svelte';
import Installation from '../components/Installation.svelte';
import Other from '../components/Other.svelte';
import Position from '../components/Position.svelte';
import Types from '../components/Types.svelte';
import Usage from '../components/Usage.svelte';

let expand = false
let position: PositionType = 'bottom-right'
let richColors = false
let closeButton = false
</script>

<svelte:head>
  <title>Svelte Sonner</title>
  <meta content="width=device-width, initial-scale=1" name="viewport" />
  <meta name="description" content="An opinionated toast component for Svelte." />
  <meta name="keywords" content="svelte, toast, notification, web" />
  <meta name="author" content="Robert Soriano" />
  <meta name="og:title" content="Svelte Sonner" />
  <meta name="og:description" content="An opinionated toast component for Svelte." />
  <meta property="og:site_name" content="Svelte Sonner" />
  <meta property="og:url" content="https://svelte-sonner.vercel.app" />
  <meta property="og:image" content="https://og-image.vercel.app/Svelte%20Sonner" />
  <link rel="icon" href="/favicon.ico" />
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:site" content="@wobsoriano" />
  <meta name="twitter:description" content="An opinionated toast component for Svelte." />
  <meta name="twitter:title" content="Svelte Sonner" />
  <meta name="twitter:image" content="https://og-image.vercel.app/Svelte%20Sonner" />
</svelte:head>

<Toaster {expand} {position} {richColors} {closeButton} />
<main class="container">
  <Hero />
  <div class="content">
    <Installation />
    <Usage />
    <Types />
    <Position {position} on:setPosition={({detail}) => position = detail} />
    <Expand {expand} on:setExpand={({detail}) => expand = detail} />
    <Other on:setCloseButton={() => closeButton = !closeButton}  on:setRichColors={({ detail }) => richColors = detail}  />
  </div>
</main>
<Footer />
