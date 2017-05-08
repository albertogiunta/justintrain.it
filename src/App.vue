<template>
  <div id="app">
    <div class="container">
      <div class="sx">
        <div class="sx-container">
          <img class="icon" :src="icon">
          <div class="title"> {{title}} </div>
          <div class="subtitle"> {{subtitle}} </div>
          <a href='https://play.google.com/store/apps/details?id=com.jaus.albertogiunta.justintrain_oraritreni&pcampaignid=MKT-Other-global-all-co-prtnr-py-PartBadge-Mar2515-1'>
            <img alt='Disponibile su Google Play' src='https://play.google.com/intl/en_us/badges/images/generic/it_badge_web_generic.png'/>
          </a>
          <div class="rating">
            <a :href="cta" class="chip">
              {{ratingmessage}} <i class="fa fa-arrow-right"></i>
            </a>
          </div>
          <br>
          <div class="reviews" v-for="review in reviews">
            <div class="review-stars">
              <div class="review-star" v-for="n in review.stars">⭐️</div>
            </div>
            <div class="review-text"><span class="quote">“</span>{{review.text}}</div>
            <div class="review-title">{{review.name}} <a :href="review.link"><i class="fa fa-link"></i></a></div>
          </div>
        </div>
      </div>
      <div class="dx">
        <div class="screen" v-for="screen in screens">
          <img :src="screen.path">
        </div>
      </div> 
      <a class="made-by" :href="albertogiunta">{{madeby}}</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      cta: "https://play.google.com/store/apps/details?id=com.jaus.albertogiunta.justintrain_oraritreni",
      albertogiunta: "www.albertogiunta.it",
      icon: "./src/assets/logo-jit.png",
      icontitle: "JustInTrain",
      title: "🇮🇹 Orario Treni Trenitalia",
      subtitle: "Fatta da un pendolare, per i pendolari.",
      madeby: "Fatta con ❤️ da Alberto Giunta",
      rating: 4.8,
      reviews: [
          {
            name: "Andrea Braga",
            stars: 5,
            text: "App a misura di pendolare, davvero! Il gesto dello swipe sull'unica tratta da pendolare è ottimo, non pensavo!",
            link: "https://play.google.com/store/apps/details?id=com.jaus.albertogiunta.justintrain_oraritreni&reviewId=Z3A6QU9xcFRPSFFaeFBEZUIyVDdBd3B0SG9taVNMSkI5cGFBUHJYVmhNLURDNVR2dGVYdW0xVURseXZpaHJKaHR5YzRlc0J0TzFYYkY4SWFoVXNwY09WbGVJ",
            path: "",
          },
          {
            name: "",
            stars: 5,
            text: "Veloce, semplice e intuitiva, tutti quello di cui hai bisogno se sei pendolare. La possibilità di monitorare un treno tramite notifica è geniale.",
            link: "https://play.google.com/store/apps/details?id=com.jaus.albertogiunta.justintrain_oraritreni&reviewId=Z3A6QU9xcFRPRWR2NWpHYlBoTWFDdkp6MnZYcDlUaEFvRkdmc01sdEVDRFhxZURiSWt1UVBXN21nQlpCNzVfbTlRY3VzVm9rdG9MNEN5MXR1T2F5NmM2OC1N",
            path: "",
          },
          {
            name: "Paolo Sanavio",
            stars: 5,
            text: "Semplicemente perfetta e completa. Comodissima la notifica. Si vede che è stata creata da chi viaggia in treno.",
            link: "https://play.google.com/store/apps/details?id=com.jaus.albertogiunta.justintrain_oraritreni&reviewId=Z3A6QU9xcFRPRURkYWQydTVGeHpmLTRnampYeEhnWktMU1YzQlE5aXBjb2Z4cEJuTTl1Z0xyYUZJLU5CbUVtd2k4b0pBbC1UTWZIY1RyS29LMGxRajBIWDVv",
            path: "",
          },
          // {
          //   name: "",
          //   stars: "",
          //   text: "",
          //   link: "",
          //   path: "",
          // },
      ],
      screens: [
        {
          title: "1",
          description: "1",
          path: "./src/assets/2swipe.png"
        },
        {
          title: "2",
          description: "2",
          path: "./src/assets/3solutions.png"
        },
        {
          title: "3",
          description: "3",
          path: "./src/assets/4notifications.png"
        },
        {
          title: "4",
          description: "4",
          path: "./src/assets/5details.png"
        },
        {
          title: "5",
          description: "5",
          path: "./src/assets/6settings.png"
        },
      ],
    }
  },
  computed: {
    ratingmessage: function () {
        return "la più apprezzata sul Goole Play Store (" + this.rating + " ⭐️ )"
    }
  }
}
</script>

<style src="./main.sass" lang="sass"></style>