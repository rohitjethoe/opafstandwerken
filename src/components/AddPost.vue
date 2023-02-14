<template>
  <div class="add-post">
    <div class="add-post-detail add-post-companyname">
        <div class="add-post-detail-title">
            Bedrijfsnaam
        </div>
        <input type="text" v-model="vacancyDetails.name">
    </div>
    <div class="add-post-detail add-post-vacancy">
        <div class="add-post-detail-title">
            Vacature
        </div>
        <input type="text" v-model="vacancyDetails.vacancy">
    </div>
    <div class="add-post-detail add-post-type">
        <div class="add-post-detail-title">
            Dienstverband
        </div>
        <select v-model="vacancyDetails.type">
            <option value="Fulltime">Fulltime</option>
            <option value="Parttime">Parttime</option>
            <option value="Bijbaan">Bijbaan</option>
        </select>
    </div>
    <div class="add-post-detail add-post-location">
        <div class="add-post-detail-title">
            Locatie
        </div>
        <input type="text" v-model="vacancyDetails.location">
    </div>
    <div class="add-post-detail add-post-location">
        <div class="add-post-detail-title">
            Email
        </div>
        <input type="email" v-model="vacancyDetails.email">
    </div>
    <div class="add-post-publish">
        <a @click="publishPost()">Publiceer</a>
    </div>
  </div>
</template>

<script>
export default {
    name: "AddPost",
    data() {
        return {
            vacancyDetails: {
                name: "Optiver",
                vacancy: "Asset Manager",
                type: "Fulltime",
                location: "Amsterdam",
                email: "example@example.com",
                logoUri: ""
            }
        }
    },
    methods: {
        publishPost: async function () {
            const response = await fetch('http://opafstandwerken-api-production-19e9.up.railway.app/api/VacancyItems', {
                method: 'POST',
                mode: 'no-cors',
                headers: {
                    'Accept': 'application/json',
                    'Content-Type': 'application/json'
                },
                body: this.vacancyDetails
            });

            const data = await response.json();

            console.log(data);
        }
    }
}
</script>

<style lang="scss" scoped>
    .add-post {
        margin-left: 10%;
        padding-bottom: 30px;
        .add-post-detail {
            .add-post-detail-title {
                font-size: 24px;
                margin: 10px 0px;
            }
            select {
                font-size: 24px;
            }
            input {
                border: none;
                padding: 4px;
                width: 300px;
                font-size: 24px;
                border-bottom: 1px solid #eee;
                box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
                transition: 0.5s all;
            }
        }
        .add-post-publish {
            margin: 30px 0px;
            a {
                background: linear-gradient(90deg, #B47AEA 18.27%, #FFC4EB 101.24%);
                color: #fff;
                font-size: 24px;
                padding: 10px 20px;
            }
            a:hover {
                cursor: pointer;
            }
        }
    }
</style>