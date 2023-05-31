<script setup lang="ts">
const style_strs = [
  `--s: 50px; /* control the size */
  --c1: #F8B195;
  --c2: #355C7D;
  --_g:
     var(--c2) 6%  14%,var(--c1) 16% 24%,var(--c2) 26% 34%,var(--c1) 36% 44%,
     var(--c2) 46% 54%,var(--c1) 56% 64%,var(--c2) 66% 74%,var(--c1) 76% 84%,var(--c2) 86% 94%;
  background:
    radial-gradient(100% 100% at 100% 0,var(--c1) 4%,var(--_g),#0008 96%,#0000),
    radial-gradient(100% 100% at 0 100%,#0000, #0008 4%,var(--_g),var(--c1) 96%)
    var(--c1);
  background-size: var(--s) var(--s);`,
  `  --s: 10px; /* control the size */
  --c1: #000;
  --c2: #d2d3d5;
  --c3: #727c7e;

  --g1: conic-gradient(at calc(250%/3) calc(50%/3),var(--c2) 60deg,#0000 0 300deg,var(--c1) 0);
  --g2: conic-gradient(at calc(50%/3) 50%,#0000 75%,var(--c1) 0);
  --g3: conic-gradient(at calc(100%/3) 50%,#0000 75%,var(--c2) 0);
  --g4: conic-gradient(from 59deg at calc(200%/3) calc(249%/9),var(--c3) 61deg,#0000 62deg);
  --g5: conic-gradient(from 60deg at 50% calc(250%/3),#f1f1f1 /*4th color*/ 60deg,var(--c1) 0 120deg,#0000 0);
  --_p: calc(9*tan(30deg)*var(--s));
  background:
    var(--g1) calc(-1*var(--s)) 0,var(--g1) calc(2*var(--s)) var(--_p),
    var(--g2),var(--g2) calc(3*var(--s)) var(--_p),
    var(--g3),var(--g3) calc(3*var(--s)) var(--_p),
    var(--g4),var(--g4) calc(3*var(--s)) var(--_p),
    var(--g5) calc(3*var(--s)) 0,var(--g5) 0 var(--_p) var(--c3);
  background-size: calc(6*var(--s)) calc(2*var(--_p))
}

@supports not (opacity:tan(1deg)) {
  html {
    --_p: calc(9*.577*var(--s));
  }`,
  `
  --r: 58px; /* control the size */
  --c1: #3FB8AF /*color 1*/ 99%,#0000 101%;
  --c2: #FF9E9D /*color 2*/ 99%,#0000 101%;

  --s:calc(var(--r)*.866);  /* .866 = cos(30deg) */
  --g0:radial-gradient(var(--r),var(--c1));
  --g1:radial-gradient(var(--r),var(--c2));
  --f:radial-gradient(var(--r) at calc(100% + var(--s)) 50%,var(--c1));
  --p:radial-gradient(var(--r) at 100% 50%,var(--c2));
  background:
    var(--f) 0 calc(-5*var(--r)/2),
    var(--f) calc(-2*var(--s)) calc(var(--r)/2),
    var(--p) 0 calc(-2*var(--r)),
    var(--g0) var(--s) calc(-5*var(--r)/2),
    var(--g1) var(--s) calc( 5*var(--r)/2),
    radial-gradient(var(--r) at 100% 100%,var(--c1)) 0 calc(-1*var(--r)),
    radial-gradient(var(--r) at 0%   50% ,var(--c1)) 0 calc(-4*var(--r)),
    var(--g1) calc(-1*var(--s)) calc(-7*var(--r)/2),
    var(--g0) calc(-1*var(--s)) calc(-5*var(--r)/2),
    var(--p) calc(-2*var(--s)) var(--r),
    var(--g0) calc(-1*var(--s)) calc(var(--r)/ 2),
    var(--g1) calc(-1*var(--s)) calc(var(--r)/-2),
    var(--g0) 0 calc(-1*var(--r)),
    var(--g1) var(--s) calc(var(--r)/-2),
    var(--g0) var(--s) calc(var(--r)/ 2)
    #FF9E9D; /*color 2 again here (yes I got lazy defining a variable ) */
  background-size: calc(4*var(--s)) calc(6*var(--r));
Resources1× 0.5× 0.25×Rerun`,
  `  --s: 64px; /* control the size */
  --c1: #EB6841;
  --c2: #EDC951;

  background:
    conic-gradient(from -45deg,var(--c1) 90deg,#0000 0 180deg,var(--c2) 0 270deg,#0000 0)
      0 calc(var(--s)/2)/var(--s) var(--s),
    conic-gradient(from 135deg at 50% 0,var(--c1) 90deg,var(--c2) 0)
      0 0/calc(2*var(--s)) var(--s); `,
  `--s: 37px; /* control the size */

  --c:#0000,#2FB8AC .5deg 119.5deg,#0000 120deg;
  --g1:conic-gradient(from  60deg at 56.25% calc(425%/6),var(--c));
  --g2:conic-gradient(from 180deg at 43.75% calc(425%/6),var(--c));
  --g3:conic-gradient(from -60deg at 50%   calc(175%/12),var(--c));
  background:
    var(--g1),var(--g1) var(--s) calc(1.73*var(--s)),
    var(--g2),var(--g2) var(--s) calc(1.73*var(--s)),
    var(--g3) var(--s) 0,var(--g3) 0 calc(1.73*var(--s))
    #ECBE13;
  background-size: calc(2*var(--s)) calc(3.46*var(--s));
  /* 3.46 = 2*sqrt(3)
     1.73 = sqrt(3)
  */`,
  `
   --s: 50px; /* control the size */
  --c1: #5E412F;
  --c2: #FCEBB6;

  background:
    radial-gradient(25% 50%,var(--c1) 98%,#0000)
     var(--s) 0/calc(2*var(--s)) var(--s),
    radial-gradient(25% 50%,var(--c2) 98%,#0000)
     0 0/calc(2*var(--s)) var(--s),
    repeating-conic-gradient(var(--c1) 0 25%,var(--c2) 0 50%)
     0 0/calc(2*var(--s)) calc(2*var(--s));`,
  `
      --s: 29px; /* control the size */
  --b: 3; /* control the thickness*/

  --g:#0000 calc(100% - var(--s)/var(--b) - 1px),#615375 /* 1st color*/
      calc(100% - var(--s)/var(--b)) calc(100% - 1px),#0000;
  --r:calc(2.414*var(--s));
  --p:calc(1.414*var(--s));
  background:
    radial-gradient(var(--r) at 0    0   ,var(--g)) var(--r) var(--r),
    radial-gradient(var(--s) at 0    0   ,var(--g)) var(--p) var(--p),
    radial-gradient(var(--r) at 0    100%,var(--g)) 0 var(--p),
    radial-gradient(var(--s) at 0    100%,var(--g)) calc(-1*var(--s)) var(--r),
    radial-gradient(var(--r) at 100% 0   ,var(--g)) var(--p) 0,
    radial-gradient(var(--s) at 100% 0   ,var(--g)) var(--r) calc(-1*var(--s)),
    radial-gradient(var(--r) at 100% 100%,var(--g)) calc(-1*var(--s)) calc(-1*var(--s)),
    radial-gradient(var(--s) at 100% 100%,var(--g)) #8EB2C5 /* 2nd color */;
  background-size: calc(2*var(--r)) calc(2*var(--r));`,
  `
   --s: 30px; /* control the size */
  --c1: #E5FCC2;
  --c2: #45ADA8;

  --_s:37.5% 12.5% at 62.5%;
  --_g:34% 99%,#0000 101%;
  --g1:radial-gradient(var(--_s) 100%,#0000 32%,var(--c1) var(--_g));
  --g2:radial-gradient(var(--_s) 0   ,#0000 32%,var(--c1) var(--_g));
  --g3:radial-gradient(var(--_s) 100%,#0000 32%,var(--c2) var(--_g));
  --g4:radial-gradient(var(--_s) 0   ,#0000 32%,var(--c2) var(--_g));
  background:
    var(--g1),
    var(--g2) 0                calc(3*var(--s)),
    var(--g3) var(--s)         calc(3*var(--s)),
    var(--g4) var(--s)         calc(6*var(--s)),
    var(--g1) calc(2*var(--s)) calc(6*var(--s)),
    var(--g2) calc(2*var(--s)) calc(9*var(--s)),
    var(--g3) calc(3*var(--s)) calc(9*var(--s)),
    var(--g4) calc(3*var(--s)) 0,
    repeating-linear-gradient(var(--c1) 0 25%,var(--c2) 0 50%);
  background-size: calc(4*var(--s)) calc(12*var(--s));`,
  ` --s: 80px; /* the size */
  --c: #5E8C6A;

  --_s: calc(2*var(--s)) calc(2*var(--s));
  --_g: 35.36% 35.36% at;
  --_c: #0000 66%,#BFB35A 68% 70%,#0000 72%;
  background:
    radial-gradient(var(--_g) 100% 25%,var(--_c)) var(--s) var(--s)/var(--_s),
    radial-gradient(var(--_g) 0    75%,var(--_c)) var(--s) var(--s)/var(--_s),
    radial-gradient(var(--_g) 100% 25%,var(--_c)) 0 0/var(--_s),
    radial-gradient(var(--_g) 0    75%,var(--_c)) 0 0/var(--_s),
    repeating-conic-gradient(var(--c) 0 25%,#0000 0 50%) 0 0/var(--_s),
    radial-gradient(var(--_c)) 0 calc(var(--s)/2)/var(--s) var(--s)
    var(--c);`,
  ` --s: 75px; /* control the size */

  --_c:#0000,#fff 1deg 79deg,#0000 81deg;
  --g0:conic-gradient(from 140deg at 50% 87.5% ,var(--_c));
  --g1:conic-gradient(from 140deg at 50% 81.25%,var(--_c));
  --g2:conic-gradient(from 140deg at 50% 75%   ,var(--_c));
  --g3:conic-gradient(at 10% 20%,#0000 75%,#fff 0);
  background:
    var(--g0) 0 calc(var(--s)/-4),var(--g0) var(--s) calc(3*var(--s)/4),
    var(--g1) ,var(--g1) var(--s) var(--s),
    var(--g2) 0 calc(var(--s)/ 4),var(--g2) var(--s) calc(5*var(--s)/4),
    var(--g3) calc( var(--s)/-10) var(--s),
    var(--g3) calc(9*var(--s)/10) calc(2*var(--s)),
    repeating-conic-gradient(from 45deg,#a31e39 0 25%,#31570e 0 50%);
  background-size: calc(2*var(--s)) calc(2*var(--s));`,

]
</script>

<template>
  <div>
    <GradientCard v-for="item, index in style_strs" :key="item" :style_str="item" :index="index" />
  </div>
  <a href="https://dev.to/afif/i-created-100-unique-css-patterns-the-best-collection-31cl"> 作者链接 </a>
</template>

<route lang="yaml">
meta:
  layout: home
</route>
