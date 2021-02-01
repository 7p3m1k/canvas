<script>
  import { isActive, url, layout } from "@roxi/routify";
  import { onMount } from "svelte";
  
</script>

<ul class="canvas-side-bar">
    {#each $layout.children as { path, title }}
        {#if title !== "template"}
        <li class:active={$isActive(path)}>
            <a href={$url(path)}>{title}</a>
        </li>
        {/if}
    {/each}
</ul>

<div class="canvas-contents">
    <slot></slot>
</div>

<style>
    .canvas-side-bar {
        position: fixed;
        left: 0;
        top: 0;
        bottom: 0;
        background-color: #eeeeee;
        padding: 50px 0;
        overflow-x: scroll;
    }

    .canvas-side-bar li {
        display: block;
    }

    .canvas-side-bar li a {
        display: block;
        width: 200px;
        padding: 8px 16px;
        font-family: 'Noto Sans KR', sans-serif;
        font-weight: 300;
        font-size: 16px;
        color: black;
        transition: 0.2s all;
        background-color: #eeeeee;
    }

    .canvas-side-bar li a:hover {
        background-color: #dddddd;
    }

    .canvas-contents {
        padding: 50px 50px 50px 250px;
    }
</style>