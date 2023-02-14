<template>
  <div class="latest">
    <div class="latest-title">
      <h1>{{ page.title }}</h1>
    </div>
    <div class="latest-search">
      <div class="latest-search-by latest-search-by-vacancy">
        <div class="latest-search-by-heading">
          Zoek op <span>functie</span>
        </div>
        <input 
          type="text" 
          :placeholder="page.search.vacancy.placeholder"
          v-model="settings.title"
          @change="fetchListings()"
        >
      </div>
      <div class="latest-search-by latest-search-by-company">
        <div class="latest-search-by-heading">  
          Zoek op <span>bedrijf</span>
        </div>
        <input 
          type="text" 
          :placeholder="page.search.company.placeholder"
          v-model="settings.company"
        >
      </div>
    </div>
    <div class="listings">
      <!-- <Listing /> -->
      <Listing 
        v-for="item in listingData"
        v-bind:key="item.id"
        :listing="item"
        :searchTitleContent="settings.title"
        :searchCompanyContent="settings.company"
      />
    </div>
  </div>
</template>

<script>
import Listing from '../components/Listing.vue';

export default {
    name: "Latest",
    data() {
      return {
        settings: {
          title: "",
          company: ""
        },
        page: {
          title: "De nieuwste vacatures",
          search: {
            vacancy: {
              placeholder: "Bijv: Developer..."
            },
            company: {
              placeholder: "Bijv: Ziggo..."
            }
          }
        }
      }
    },
    components: {
      Listing
    },
    props: {
      API_URI: String,
      listingData: JSON
    }
}
</script>

<style lang="scss" scoped>
  .latest {
    width: 90vw;
    margin: 30px auto;
    margin-bottom: 60px;
    .latest-title {
      h1 {
        font-weight: 400;
      }
    }
    .latest-search {
      .latest-search-by {
        display: inline-block;
        margin: 20px 0px;
        .latest-search-by-heading {
          display: inline-block;
        }
        input {
          padding: 8px 8px;
          border: 1px solid #7d7d7d;
          margin: 0px 8px;
        }
      }
    }
  }

  @media only screen and (max-width: 700px) {
    .latest {
      width: 84vw;
    }
  }

  @media only screen and (min-width: 1240px) {
    .latest {
      width: 1000px;
    }
  }
</style>