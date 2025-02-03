<script setup>
import ArtPiece from "@/components/ArtPiece.vue";
import img1 from "@/assets/icons/img_1.jpg";
import img2 from "@/assets/icons/img_2.jpg";
import img3 from "@/assets/icons/img_3.jpg";
import img4 from "@/assets/icons/img_4.jpg";
import img5 from "@/assets/icons/img_5.jpg";
import img6 from "@/assets/icons/img_6.jpg";
import img7 from "@/assets/icons/img_7.jpg";
import img8 from "@/assets/icons/img_8.jpg";
import img9 from "@/assets/icons/img_9.jpg";
</script>

<template>
  <div
    class="relative font-[Poppins] min-h-screen w-full gradient_bg gap-4 flex flex-col"
  >
    <div
      class="mt-8 md:mt-10 lg:mt-24 justify-center text-center text-xl md:text-3xl lg:text-4xl xl:text-5xl px-8 text-[#000000] leading-[1.4] lg:leading-[1.5] xl:leading-[1.6] break-words"
    >
      All these pieces are
      <span class="font-bold underline"
        >stunning, emblematic, and historic</span
      >. We have gathered numerous historical items and brought them here for you to enjoy.
    </div>
    <div
      class="underline mt-8 md:mt-12 justify-center text-center text-lg md:text-xl lg:text-2xl px-8 text-[#000000] leading-[1.4] lg:leading-[1.5] xl:leading-[1.6] break-words"
    >
      Click/Hover over images to see more info
    </div>
    <div
      class="px-10 mt-6 mb-10 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-10 justify-items-center"
    >
      <ArtPiece
        :image="img1"
        title="Mona Lisa, Vincent Van Gogh"
        price="$1.01B"
        desc="The woman sits markedly upright in a pozzetto armchair with her arms folded, a sign of her reserved posture. Her gaze is fixed on the observer."
      />
      <ArtPiece :image="img2" title="Self-Portrait with a Straw Hat, Vincent Van Gogh" price="$150M" desc="This work depicts the artist wearing a wide-brimmed straw hat. The painting is an example of Van Gogh's Post-Impressionist style and is considered one of his most iconic works." />
      <ArtPiece :image="img3" title="Girl with a Pearl Earring, Johannes Vermeer" price="Out of stock" desc="A painting of a young woman wearing an oriental turban and a large pearl earring. The painting is an example of a Dutch tronie, which is a type of portraiture that depicts an idealized character or type." />
      <ArtPiece :image="img4" title="Self-Portrait, Vincent Van Gogh" price="$35M" desc="This is a self-portrait by Vincent van Gogh, painted in 1889 while he was staying at the Saint-Paul-de-Mausole asylum in Saint-Rémy-de-Provence, France." />
      <ArtPiece :image="img5" title="Self-Portrait in a Straw Hat, Elisabeth Louise Vigée Le Brun" price="Sold" desc="This depicts the artist, confidently looking directly at the viewer, wearing a simple, fashionable dress and a straw hat, while holding a palette." />
      <ArtPiece :image="img6" title="Portrait of Dr. Gachet, Vincent van Gogh" price="82.5M" desc="This artwork depicts Dr. Paul Gachet in a state of melancholy. The painting is known for its heavy colors, the doctor's sad expression, and the books and flowers on the table. " />
      <ArtPiece :image="img7" title="Self-Portrait, Vincent Van Gogh" price="$60M" desc="Van Gogh depicts himself as a painter, wearing a blue smock and holding a palette and brushes. " />
      <ArtPiece :image="img8" title="Portrait of a Young Girl, Petrus Christus" price="Out of Stock" desc="A young woman, likely of high social standing, is depicted in a three-quarter view." />
      <ArtPiece :image="img9" title="The Blue Boy, Thomas Gainsborough" price="$11M" desc="The painting depicts a young boy, believed to be Jonathan Buttall, the son of a wealthy hardware merchant and an acquaintance of Gainsborough. " />
    </div>
  </div>
</template>
