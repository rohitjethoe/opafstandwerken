<template>
    <div class="listing" v-if="listing.name.includes(searchTitleContent) && listing.company.includes(searchCompanyContent)">
        <div class="listing-logo">
            <img v-if="listing.logoUri !== ''" :src="listing.logoUri" alt="Logo">
            <div class="listing-logo-default" v-else>
                <div></div>
            </div>
        </div>
        <div class="listing-about">
            <div class="listing-about-company">
                {{listing.company}}
            </div>
            <div class="listing-about-vacancy">
                {{listing.name}}
            </div>
            <div class="listing-about-type">
                {{listing.type}}
            </div>
        </div>
        <div class="listing-apply">
            <a :href="`mailto:${listing.email}`">Solliciteer</a>
        </div>
    </div>
</template>

<script>
export default {
    name: "Listing",
    props: {
        listing: JSON,
        searchTitleContent: String,
        searchCompanyContent: String
    }
}
</script>

<style lang="scss" scoped>
    .listing {
        background-color: #fff;
        border: 1px solid #ebebec;
        margin: 4px 0px;
        padding: 15px;
        display: flex;
        flex-direction: row;
        align-items: center;
        .listing-logo {
            height: 40px;
            width: 20px;
            img {
                width: 40px;
                height: 40px;
                border-radius: 100%;
            }
            .listing-logo-default {
                width: 40px;
                height: 40px;
                border-radius: 100%;
                background: linear-gradient(75.45deg, #B47AEA 18.27%, #FFC4EB 101.24%);
                display: flex;
                div {
                    background-color: #fff;
                    width: 32px;
                    height: 32px;
                    border-radius: 100%;
                    margin: auto;
                }
            }
            flex-grow: 1;
        }
        .listing-about {
            flex-grow: 12;
            .listing-about-vacancy {
                margin: 2px 0px;
                font-weight: 500;
            }
        }
        .listing-apply {
            flex-grow: 0;
            a:link, a:visited {
                background: linear-gradient(90deg, #B47AEA 18.27%, #FFC4EB 101.24%);
                padding: 6px 12px;
                color: #fff;
                font-weight: 500;
                text-decoration: none;
            }
        }
    }
</style>