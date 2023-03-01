<script setup>
import HoverCard from './components/HoverCard.vue';
import Carrot from 'vue-material-design-icons/Carrot.vue';
import MapMarker from 'vue-material-design-icons/MapMarker.vue';
import FruitCherries from 'vue-material-design-icons/FruitCherries.vue';
import Basket from 'vue-material-design-icons/Basket.vue';
import Cow from 'vue-material-design-icons/Cow.vue';
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
  Basket: {
    // img: "https://images.unsplash.com/photo-1635774855717-0aec182f92cc?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80",
    title: "Nos paniers hebdomadaires",
    text: "Du Marché en ligne à votre panier, frais, local et responsable.",
    description: "Votre abonnement vient avec un panier de base automatique hebdomadaire rempli de 30 $ de fruits et légumes de saison, mais vous avez toujours le choix de personnaliser votre commande ou de l’annuler jusqu’à minuit la veille de votre livraison.",
    text2: "SANS ENGAGEMENT"
  },
  Carrot: {
    // img: "https://images.unsplash.com/photo-1635774855717-0aec182f92cc?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80",
    title: "De nos toits à votre assiette",
    text: "Chaque jour, nous livrons directement à notre communauté d’adeptes - les Lufavores! - des milliers de paniers d’épicerie contenant des légumes cultivés dans nos fermes sur les toits.",
    description: "Nous avons mis sur pied un réseau de centaines de points de cueillette de quartier, pour livrer le plus directement possible aux Lufavores nos aliments et ceux de nos partenaires."
  },
  Cow: {
    // img: "https://images.unsplash.com/photo-1635774855717-0aec182f92cc?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80",
    title: "Bâtir un meilleur système alimentaire.",
    text: "Un réseau de fermiers et de producteurs locaux",
    description: "Les fermes sur les toits n’ont d’aucune façon l’intention de remplacer les fermes et les producteurs ruraux. Nous travaillons avec des partenaires qui partagent ces valeurs pour offrir aux citadins une sélection variée de produits."
  },
  FruitCherries: {
    // img: "https://images.unsplash.com/photo-1635774855717-0aec182f92cc?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80",
    title: "Une communauté locale de Lufavores",
    text: "Participez à la création d’un système alimentaire durable.",
    description:
      `Lufa c'est
      60 000 Lufavores,
      20 000 paniers chaques semaines,
      Plus de 100 points de cueillette de quartier,
      Un réseau de fermiers et de producteurs locaux,
      8 500 produits frais et locaux.`
  }
};
</script>

<template>
  <div class='w-full h-screen'>
        <img class='absolute w-full h-full object-cover' src="https://images.unsplash.com/photo-1610348725531-843dff563e2c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2940&q=80" alt="vegetables" />
        <img class="absolute top-0 w-[120px] mt-10 ml-10 z-[100]" src="/images/lufa-logo.png" alt="lufa logo">
        <div class='flex flex-col bg-[#79a032]/80 pt-10 z-40 items-center justify-center h-screen absolute'>
          <div class='rounded w-12 pt-2 mx-10 my-4 border-transparent border-b-4 hover:border-b-white duration-300' @mouseover="onIconHover('Basket'), showCard = true" @mouseleave="onIconLeave(), showCard = false">
            <Basket fillColor='#ffffff' :size='40' class="cursor-pointer flex items-center justify-center" />
          </div>
          <div class='rounded w-12 pt-2 mx-10 my-4 border-transparent border-b-4 hover:border-b-white duration-300' @mouseover="onIconHover('Carrot'), showCard = true" @mouseleave="onIconLeave(), showCard = false">
            <Carrot fillColor='#ffffff' :size='40' class="cursor-pointer flex items-center justify-center" />
          </div>
          <div class='rounded w-12 pt-2 mx-10 my-4 border-transparent border-b-4 hover:border-b-white duration-300' @mouseover="onIconHover('Cow'), showCard = true" @mouseleave="onIconLeave(), showCard = false">
            <Cow fillColor='#ffffff' :size='40' class="cursor-pointer flex items-center justify-center" />
          </div>
          <div class='rounded w-12 pt-2 mx-10 my-4 border-transparent border-b-4 hover:border-b-white duration-300' @mouseover="onIconHover('FruitCherries'), showCard = true" @mouseleave="onIconLeave(), showCard = false">
            <FruitCherries fillColor='#ffffff' :size='40' class="cursor-pointer flex items-center justify-center" />
          </div>
        </div>

        <div class="absolute w-full h-screen flex items-center px-4 z-10">
          <div class='w-[400px] h-[500px] mx-auto bg-white rounded-xl text-black duration-500' :class="{'opacity-100': showCard, 'opacity-0': !showCard}">
            <HoverCard v-if="hoveredIcon !== null" :img="iconInfo[hoveredIcon]?.img ?? ''" :title="iconInfo[hoveredIcon]?.title ?? ''" :text="iconInfo[hoveredIcon]?.text ?? ''" :description="iconInfo[hoveredIcon]?.description ?? ''" :text2="iconInfo[hoveredIcon]?.text2 ?? ''" />
          </div>
          <div class='w-[500px] h-[700px] mr-20 bg-white rounded-xl text-black'>
            <div class='mx-auto p-10'>
              <h1 class='text-3xl py-2'>Créer un compte</h1>
              <p class='text-sm'>Joignez-vous aux <span class="font-bold">60 756</span> Lufavores qui mangent frais, local et responsable.</p>
              <form class='w-full flex flex-col py-1'>
                <div class="flex items-center justify-between">
                  <p>Prénom <span class="text-red-600">*</span></p>
                  <input
                    class='p-2 my-2 border rounded w-[60%]'
                    type="text"
                    placeholder='Nathalie'
                  />
                </div>
                <div class="flex items-center justify-between">
                  <p>Nom <span class="text-red-600">*</span></p>
                  <input
                    class='p-2 my-2 border rounded w-[60%]'
                    type="text"
                    placeholder='Tremblay'
                  />
                </div>
                <div class="flex items-center justify-between">
                  <p>Courriel <span class="text-red-600">*</span></p>
                  <input
                    class='p-2 my-2 border rounded w-[60%]'
                    type="email"
                    placeholder='exemple@mail.com'
                    autoComplete='email'
                  />
                </div>
                <div class="flex items-center justify-between">
                  <p>Mot de passe <span class="text-red-600">*</span></p>
                  <input
                    class='p-2 my-2 border rounded w-[60%]'
                    type="password"
                    placeholder='onaimedonclesbourdons'
                    autoComplete='current-password'
                  />
                </div>
                <div class="flex items-center justify-between">
                  <p>Téléphone <span class="text-red-600">*</span></p>
                  <input
                    class='p-2 my-2 border rounded w-[60%]'
                    type="tel"
                    placeholder='(514) 669-3559'
                  />
                </div>
                <div class="flex items-center justify-between">
                  <p>Adresse <span class="text-red-600">*</span></p>
                  <input
                    class='p-2 my-2 border rounded w-[60%]'
                    type="address"
                    placeholder='3075 Boulevard Thimens, Ville Saint Laurent'
                  />
                </div>
                <p class="text-sm pt-2">
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
