<template>
  <div class="truck">
    <div class="cabin">
      <div class="right-window">
        <div class="mirror"></div>
      </div>
       <div class="left-window">
        <div class="mirror"></div>
      </div>
      <div class="mud-guard">
        <div class="tire">
          <span></span>
          <span></span>
          <span></span>
          <span></span>
          <div class="back"></div>
        </div>
      </div>
    </div>
    <div class="truck-container">
      <div class="container-left">
         <div class="mud-guard">
          <div class="tire">
          <span></span>
          <span></span>
          <span></span>
          <span></span>
          <div class="back"></div>
        </div>
      </div>
      </div>
      <div class="container-back">
        <div class="truck-door">
          <strong>Shet.com</strong>
        </div>
      </div>
      <div class="container-right">
        <div class="mud-guard">
          <div class="tire">
          <span></span>
          <span></span>
          <span></span>
          <span></span>
          <div class="back"></div>
        </div>
      </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
$mud-guard-clr: orange;//blueviolet;
$tire-clr: #000;
$truck-clr:  linear-gradient(purple, blueviolet, purple);
$truck-brd-clr: blueviolet;
$mirror-clr: skyblue;
$tire-z: 2.8vw;

.truck {
  width: 40vw;
  height: 40vh;
  position: relative;
  left: 35vw;
  transform-style: preserve-3d;
  // animation: rotate-truck 30s linear infinite;
  // transform: rotateY(180deg) rotateX(2.5deg);

  .truck-container,
  .truck-door,
  .container-back,
  .container-left,
  .container-right,
  .cabin, .cabin::before, .cabin::after {
    position: absolute;
    height: 100%;
    background: $truck-clr;
  }
  .truck-container,
  .container-left,
  .container-right {
    width: 100%;
  }
  .truck-container, .container-back,
  .cabin, .right-window, .left-window,
  .container-left, .container-right,
  .mud-guard {
    transform-style: preserve-3d;
  }
  .mud-guard {
    position: absolute;
    height: 8rem;
    width: 8rem;
    display: grid;
    place-items: center;
    background: var(--primary-color);
    border-top: 1.5rem solid $mud-guard-clr;
    border-right: 1.5rem solid $mud-guard-clr;
    border-radius: 45%;
    transform: rotate(-45deg) translateZ(7vw);

      .tire, .back {
        transform-style: preserve-3d;
      }
      .tire {
            width: 6rem;
            height: 6rem;
            background: $tire-clr;
            border-radius: 50%;
            border: .3rem outset hsl(206, 21%, 94%) ;
            position: absolute;
            display: grid;
            place-items: center;
        
        &::before {
            content: "";
            position: absolute;
            height: 70%;
            width: 70%;
            background: hsl(206, 21%, 94%);
            border-radius: 50%;
            border: .4rem inset #0005;
        }
        span {
            position: absolute;
            height: .6rem;
            width: .6rem;
            background: #fff5;
            border-radius: 50%;
            border: .2rem outset #0009;
            transform: translateX(-50%) translateY(-50%); 
        }
        span:nth-child(1), span:nth-child(2) {
          top: 40%;
        }
        span:nth-child(1) {
          left: 40%;
        }
        span:nth-child(2) {
          left: 60%;
        }
        span:nth-child(3), span:nth-child(4) {
          top: 60%;
        }
        span:nth-child(3) {
          left: 40%;
        }
        span:nth-child(4) {
          left: 60%;
        }
       
        .back {
            position: absolute;
            width: 100%;
            height: 100%;
            background: $tire-clr; 
            display: grid;
            place-items: center;
            border-radius: 50%;
            transform: translateZ(-3rem);
        
        &::before {
            content: "";
            position: absolute;
            width: 50%;
            height: 100%;
            background: $tire-clr;
            transform-origin: right;
            transform: rotateY(90deg) translateZ(-.7rem);
            border-radius: .25rem;
        }
        }
       
        @keyframes rotate-tire {
          to {
            transform: translateZ($tire-z) rotate(225deg) translateX(0rem) rotateY(0deg);
          }
        }
        @keyframes turn-tire {
          0% {
            transform: translateZ($tire-z) rotate(225deg) translateX(-1rem) rotateY(0deg);
          }
          25% {
            transform: translateZ($tire-z) rotate(225deg) translateX(-1rem) rotateY(-15deg);
          }
          50% {
            transform: translateZ($tire-z) rotate(225deg) translateX(-1rem) rotateY(-30deg);
          }
          90% {
            transform: translateZ($tire-z) rotate(225deg) translateX(-1rem) rotateY(-45deg);
          }
          100% {
            transform: translateZ($tire-z) rotate(225deg) translateX(-1rem) rotateY(0deg);
          }
        }
      }
  }
  .cabin {
    width: 40%;
    left: 100%;
    background: none;

    &::before,
    &::after {
      content: "";
      position: absolute;
      width: 100%;
      height: 100%;
      border: .3rem solid $truck-brd-clr;
        clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 72% 100%,
      74% 95%, 73% 90%,  71.5% 85%, 70% 80%, 62.5% 75%, 62% 74%,
      61.5% 73.5%,61% 73.5%,60.5% 73%, 60% 73%, 59.5% 72.5%,59% 72.5%,
      58.5% 72.5%,58% 72.5%,57.5% 72.5%,57% 72.5%,56.5% 72.5%,56% 72.5%,
      55.5% 72.5%,55% 72.5%,54.5% 72.5%,54% 72.5%,53.5% 72.5%,53% 72.5%,
      52.5% 73.5%,52% 73.5%,51.5% 73.5%,51% 73.5%,50.5% 73.5%,50% 73.5%,49.5% 73.5%,
      55.5% 73.5%, 55% 73.5%,54.5% 73.5%, 54% 73.5%, 53.5% 73.5%, 53% 73.5%,
      52.5% 73.5%, 52% 73.5%, 51.5% 72.5%, 51% 72.5%, 50.5% 72.5%, 50% 72.5%,
      49.5% 72.5%, 49% 72.5%, 48.5% 72.5%, 48% 72.5%, 47.5% 72.5%, 47% 72.5%,
      46.5% 72.5%, 46% 72.5%, 45.5% 72.5%, 45% 72.5%, 44.5% 72.5%, 44% 72.5%,
      43.5% 73.5%, 43% 73.5%, 42.5% 73.5%, 42% 73.5%, 41.5% 73.5%, 41% 73.5%,
      40.5% 74.5%, 40% 74.5%, 39.5% 74.5%, 39% 74.5%, 38.5% 75%, 38% 75%, 37.5% 75%,
      37% 76%, 36.5% 76%, 36% 76%, 35.5% 76%, 35% 76.5%, 34.5% 77%,34% 77.5%,
      33.5% 78%,   33% 78.5%,   32.5% 79%,   32% 79.5%,   31.5% 80%, 31% 80.5%,
      30.5% 81%,   30% 82%,   29.5% 82.5%,   29% 83%,   28.5% 83.5%,   28% 84%,
      27.5% 84.5%,   27% 85%,   26.5% 85%,   26% 90%,   25.5% 95%,   25% 100%,
      0% 1000%);
    shape-outside: polygon(0% 0%, 100% 0%, 100% 100%, 72% 100%,
      74% 95%, 73% 90%,  71.5% 85%, 70% 80%, 62.5% 75%, 62% 74%,
      61.5% 73.5%,61% 73.5%,60.5% 73%, 60% 73%, 59.5% 72.5%,59% 72.5%,
      58.5% 72.5%,58% 72.5%,57.5% 72.5%,57% 72.5%,56.5% 72.5%,56% 72.5%,
      55.5% 72.5%,55% 72.5%,54.5% 72.5%,54% 72.5%,53.5% 72.5%,53% 72.5%,
      52.5% 73.5%,52% 73.5%,51.5% 73.5%,51% 73.5%,50.5% 73.5%,50% 73.5%,49.5% 73.5%,
      55.5% 73.5%, 55% 73.5%,54.5% 73.5%, 54% 73.5%, 53.5% 73.5%, 53% 73.5%,
      52.5% 73.5%, 52% 73.5%, 51.5% 72.5%, 51% 72.5%, 50.5% 72.5%, 50% 72.5%,
      49.5% 72.5%, 49% 72.5%, 48.5% 72.5%, 48% 72.5%, 47.5% 72.5%, 47% 72.5%,
      46.5% 72.5%, 46% 72.5%, 45.5% 72.5%, 45% 72.5%, 44.5% 72.5%, 44% 72.5%,
      43.5% 73.5%, 43% 73.5%, 42.5% 73.5%, 42% 73.5%, 41.5% 73.5%, 41% 73.5%,
      40.5% 74.5%, 40% 74.5%, 39.5% 74.5%, 39% 74.5%, 38.5% 75%, 38% 75%, 37.5% 75%,
      37% 76%, 36.5% 76%, 36% 76%, 35.5% 76%, 35% 76.5%, 34.5% 77%,34% 77.5%,
      33.5% 78%,   33% 78.5%,   32.5% 79%,   32% 79.5%,   31.5% 80%, 31% 80.5%,
      30.5% 81%,   30% 82%,   29.5% 82.5%,   29% 83%,   28.5% 83.5%,   28% 84%,
      27.5% 84.5%,   27% 85%,   26.5% 85%,   26% 90%,   25.5% 95%,   25% 100%,
      0% 1000%
      );
    }
    &::before {
      border-top-right-radius: 50%;
      transform: translateZ(9.9vw);
    
    }
    &::after {
      border-top-left-radius: 50%;
      transform: rotateY(180deg) translateZ(7vw);
    }
    .right-window {
      position: absolute;
      top: 10%;
      left: 10%;
      width: 80%;
      height: 40%;
      background: $mirror-clr;
      border: .3rem solid #fff;
      border-top-right-radius: 50%;
      transform: translateZ(10vw);

      .mirror {
        position: absolute;
        bottom: 0;
        right: -7.5%;
        width: 20%;
        height: 60%;
        border: .3rem solid #fff;
        border-radius: 40%;  
        transform-origin: right;
        transform: rotateY(80deg);

        &::before, &::after {
          content: "";
          position: absolute;
        }

        &::before {
          top: 10%;
          left: 10%;
          width: 80%;
          height: 80%;
          border: .3rem solid #fff;
          transform-origin: left;
          transform: rotateY(-3600deg);
        }

        &::after {
            width: 100%;
            height: 100%;
            border: 1rem solid #fff;
            transform-origin: left;
            transform: rotateY(3600deg);
        }

      }
    }
     .left-window {
      position: absolute;
      top: 10%;
      left: 10%;
      width: 80%;
      height: 40%;
      border: .3rem solid #fff;
      border-top-right-radius: 50%;
      transform: translateZ(-10vw);

      .mirror {
        position: absolute;
        bottom: 0;
        right: -7.5%;
        width: 20%;
        height: 60%;
        border: .3rem solid #fff;
        border-radius: 40%;  
        transform-origin: right;
        transform: rotateY(-80deg);

        &::before, &::after {
          content: "";
          position: absolute;
        }

        &::before {
          top: 10%;
          left: 10%;
          width: 80%;
          height: 80%;
          border: .3rem solid #fff;
          transform-origin: left;
          transform: rotateY(-3600deg);
        }

        &::after {
            width: 100%;
            height: 100%;
            border: 1rem solid #fff;
            transform-origin: left;
            transform: rotateY(3600deg);
        }

      }
    }
    .mud-guard {
      left: 25%;
      bottom: -12.5%;

      .tire {
        transform: translateZ($tire-z) rotate(45deg) translateX(0)
                  rotateY(0);   
        animation: rotate-tire 3s linear 1,
                  turn-tire 3s linear 3s 1;        
      }
    }
  }
  .container-left {
    transform: rotateY(180deg) translateZ(10vw);

    .mud-guard {
      right: 10%;
      bottom: -14.5%;

      .tire {
        transform: translateZ(-7.2vw) rotate(45deg);
      }
    }
  }
  .container-right {
    transform: translateZ(10vw);

    .mud-guard {
    left: 10%;
    bottom: -14.5%;

    .tire {
      transform: translateZ(-7.2vw) rotate(45deg);
      animation: rotate-tire 3s linear 1
    }
    }
  }
  .container-left, .container-right, .container-left, .truck-door {
    border: .3rem groove $truck-brd-clr;
  }
  .container-back {
    left: -25%;
    width: 50%;
    transform: rotateY(270deg);

    .truck-door {
      width: 100%;
      height: 100%;
      display: grid;
      place-items: center;
      transform-origin: bottom;
      // transform: rotateX(360deg);
      // animation: door 10s linear infinite;

      strong {
        font-size: 3.5rem;
        transform: rotate(-35deg);
      }
    }
  }
  @keyframes rotate-truck {
    to {
      transform: rotateY(360deg);
    }
  }
  @keyframes door {
    from {
      transform: rotateX(225deg);
    }
    to {
      transform: rotateX(360deg);
    }
  }
}
</style>