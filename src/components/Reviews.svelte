<script>
  import SectionWrapper from "./SectionWrapper.svelte";
  import reviews from "../data/review.js";
  import ReviewCard from "./ReviewCard.svelte";
  let lim = true;
  let reviewList = reviews;
</script>

<SectionWrapper id="reviews">
  <div
    class="flex flex-col gap-10 sm:gap-14 md:gap-24 py-20 flex-1 items-center justify-center"
  >
    <div class="flex flex-col gap-2">
      <p class="opacity-60 text-base sm:text-lg md:text-xl text-center">
        Don't just take our word for it
      </p>
      <h3
        class="text-4xl sm:text-5xl md:text-6xl max-w-[1000px] mx-auto w-full font-semibold text-center"
      >
        See What <span class="text-indigo-400">Others</span> Have To Say
      </h3>
    </div>
    <div class="flex flex-col md:flex-row gap-8 w-fit mx-auto">
        <div class="flex flex-col gap-8">
            {#each lim ? reviewList.slice(0,4) : reviewList as reviewItem, index}
            <ReviewCard {reviewItem} left={true} {index}/>
            {/each}
        </div>
        <div class="w-[1px] bg-slate-950 hidden md:flex"></div>
        <div class="flex flex-col gap-8">
            {#each lim ? reviewList.slice(0,4) : reviewList as reviewItem, index}
            <ReviewCard {reviewItem} {index}/>
            {/each}
        </div>
    </div>
  </div>
</SectionWrapper>
