<script>
    import { css, keyframes } from "emotion";
    import { range } from "./utils";
    export let size = 60;
    export let color = '#FF3E00';
    export let unit = "px"

    const sync = keyframes`
      33% {transform: translateY(10px);}
      66% {transform: translateY(-10px);}
      100% {transform: translateY(0);}
    `;
    const wrapper = css`
      height: ${size+unit};
      width: ${size+unit};
      display: flex;
      align-items: center;
      justify-content: center;
    `;
    const balls = css`
      height: ${size/4+unit};
      width: ${size/4+unit};
      background-color: ${color};
      margin: 1px;
      display: inline-block;
      border-radius: 100%;
    `;
  </script>
  <div class="{wrapper}">
      {#each range(3, 1) as version}
      <div 
      class="{balls}"
      style="animation: 0.6s ease-in-out {version === 1 ? '0.07s' : version === 2 ? '0.14s' : version === 3 ? '0.21s' : ''} infinite normal both running {sync};"
      />
      {/each}
  </div>
  