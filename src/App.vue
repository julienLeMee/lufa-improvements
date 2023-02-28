<script setup>
import Magnify from 'vue-material-design-icons/Magnify.vue';
import HomeOutline from 'vue-material-design-icons/HomeOutline.vue';
import TrendingUp from 'vue-material-design-icons/TrendingUp.vue';
import Television from 'vue-material-design-icons/Television.vue';
import HoverCard from './components/HoverCard.vue';
import { ref } from 'vue';

const showCard = ref(false);
const hoveredIcon = ref(null);

function onIconHover(iconName) {
  hoveredIcon.value = iconName;
}

function onIconLeave() {
  hoveredIcon.value = null;
}

const iconInfo = {
  magnify: {
    title: "Titre 1",
    text: "Texte 1",
    description: "Description 1"
  },
  HomeOutline: {
    title: "Titre 2",
    text: "Texte 2",
    description: "Description 2"
  },
  TrendingUp: {
    title: "Titre 3",
    text: "Texte 3",
    description: "Description 3"
  },
  Television: {
    title: "Titre 4",
    text: "Texte 4",
    description: "Description 4"
  }
};
</script>

<template>
  <div class='w-full h-screen'>
        <img class='absolute w-full h-full object-cover' src="https://images.unsplash.com/photo-1610348725531-843dff563e2c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2940&q=80" alt="vegetables" />
        <img class="absolute top-0 w-[120px] mt-10 ml-10 z-[100]" src="/images/lufa-logo.png" alt="lufa logo">
        <div class='flex flex-col bg-[#79a032]/80 pt-10 z-40 items-center justify-center h-screen absolute'>
          <div class='rounded w-12 pt-2 mx-10 my-4 border-transparent border-b-4 hover:border-b-white' @mouseover="onIconHover('magnify'), showCard = true, setCardContent('magnify')" @mouseleave="onIconLeave(), showCard = false">
            <Magnify fillColor='#ffffff' :size='40' class="cursor-pointer flex items-center justify-center" />
          </div>
          <div class='rounded w-12 pt-2 mx-10 my-4 border-transparent border-b-4 hover:border-b-white' @mouseover="onIconHover('HomeOutline'), showCard = true, setCardContent('HomeOutline')" @mouseleave="onIconLeave(), showCard = false">
            <HomeOutline fillColor='#ffffff' :size='40' class="cursor-pointer flex items-center justify-center" />
          </div>
          <div class='rounded w-12 pt-2 mx-10 my-4 border-transparent border-b-4 hover:border-b-white' @mouseover="onIconHover('TrendingUp'), showCard = true, setCardContent('TrendingUp')" @mouseleave="onIconLeave(), showCard = false">
            <TrendingUp fillColor='#ffffff' :size='40' class="cursor-pointer flex items-center justify-center" />
          </div>
          <div class='rounded w-12 pt-2 mx-10 my-4 border-transparent border-b-4 hover:border-b-white' @mouseover="onIconHover('Television'), showCard = true, setCardContent('Television')" @mouseleave="onIconLeave(), showCard = false">
            <Television fillColor='#ffffff' :size='40' class="cursor-pointer flex items-center justify-center" />
          </div>
        </div>

        <div class="absolute w-full h-screen flex items-center px-4 z-10">
          <div class='w-[400px] h-[500px] mx-auto bg-white rounded-xl text-black duration-300' :class="{'opacity-100': showCard, 'opacity-0': !showCard}">
            <HoverCard v-if="hoveredIcon !== null" :title="iconInfo[hoveredIcon]?.title ?? ''" :text="iconInfo[hoveredIcon]?.text ?? ''" :description="iconInfo[hoveredIcon]?.description ?? ''" />
          </div>
          <div class='w-[500px] h-[700px] mr-20 bg-white rounded-xl text-black'>
            <div class='mx-auto p-10'>
              <h1 class='text-2xl py-2'>Créer un compte</h1>
              <p class='text-sm'>Joignez-vous aux <span class="font-bold">60 756</span> Lufavores qui mangent frais, local et responsable.</p>
              <form class='w-full flex flex-col py-1'>
                <div class="flex items-center justify-between">
                  <p>Prénom <span class="text-red-600">*</span></p>
                  <input
                    class='p-2 my-2 border rounded'
                    type="text"
                    placeholder='Nathalie'
                  />
                </div>
                <div class="flex items-center justify-between">
                  <p>Nom <span class="text-red-600">*</span></p>
                  <input
                    class='p-2 my-2 border rounded'
                    type="text"
                    placeholder='Tremblay'
                  />
                </div>
                <div class="flex items-center justify-between">
                  <p>Courriel <span class="text-red-600">*</span></p>
                  <input
                    class='p-2 my-2 border rounded'
                    type="email"
                    placeholder='exemple@mail.com'
                    autoComplete='email'
                  />
                </div>
                <div class="flex items-center justify-between">
                  <p>Mot de passe <span class="text-red-600">*</span></p>
                  <input
                    class='p-2 my-2 border rounded'
                    type="password"
                    placeholder='onaimedonclesbourdons'
                    autoComplete='current-password'
                  />
                </div>
                <div class="flex items-center justify-between">
                  <p>Téléphone <span class="text-red-600">*</span></p>
                  <input
                    class='p-2 my-2 border rounded'
                    type="tel"
                    placeholder='(514) 669-3559'
                  />
                </div>
                <div class="flex items-center justify-between">
                  <p>Adresse <span class="text-red-600">*</span></p>
                  <input
                    class='p-2 my-2 border rounded'
                    type="address"
                    placeholder='3075 Boulevard Thimens, Ville Saint Laurent'
                  />
                </div>
                <p class="text-sm">
                  <span class="font-bold">Pas de téléphone cellulaire?</span> Contactez notre service à la clientèle à l’aide de notre <span class="text-[#79a032] cursor-pointer">formulaire de contact</span>  pour terminer votre inscription.
                </p>
                <div class="flex items-center mx-auto w-[50%] pt-4">
                  <input class='mr-2' type="checkbox" checked />
                  <p class="text-center text-xs mx-auto">Abonnez-vous aux alertes sur votre commande et à l'infolettre</p>
                </div>
                <button className='w-[70%] mx-auto bg-[#79a032] mt-6 py-2 rounded cursor-pointer text-white'>Suivant: Vérification</button>
              </form>
            </div>
          </div>
        </div>

      </div>
</template>
