<template>
  <header>
    <div class="logo">
        <h1>
            Op afstand werken<span class="text-gradient">.</span>
        </h1>
    </div>
    <div class="navigation">
        <div 
            @click="openNavigation(this)"
            class="burger-icon"
            :class="{ opened: navHandler.opened }"
        >
            <div class="burger-icon-bar1"></div>
            <div class="burger-icon-bar2"></div>
            <div class="burger-icon-bar3"></div>
        </div>
        <div class="navigation-list" :class="{ navOpened: navHandler.opened }">
            <div class="navigation-list-title">
                <h1>Op afstand, is de <span class="text-gradient">moderne vorm</span> van werken<span class="text-gradient">.</span></h1>
                <p>Ervaar hoe geweldig en productief op afstand werken kan zijn.</p>           
            </div>
            <ul>
                <h1>Menu</h1>
                <li
                    v-for="item in siteMap"
                    v-bind:key="item.id"
                >
                    <a :href="item.url">{{ item.title }}</a>
                </li>
            </ul>
        </div>
    </div>
  </header>
</template>

<script>
export default {
    data: () => {
        return {
            navHandler: {
                opened: false
            },
            siteMap: {
                Home: {
                    id: 0,
                    url: "./",
                    title: "Home"
                },
                About: {
                    id: 1,
                    url: "./about",
                    title: "Over ons"
                }
            }
        }
    },
    methods: {
        openNavigation: (data) => {
            data.navHandler.opened = !data.navHandler.opened;
        }
    }
}
</script>

<style lang="scss">
    header {
        background-color: #fff;
        border-bottom: 1px solid #E3E3E3;
        .logo {
            float: left;
            margin: 5px 30px;
            margin-top: 0px;
            padding: 10px 0px;
            h1 {
                color: #000;
                font-size: 24px;
                text-transform: uppercase;
                .text-gradient {      
                    font-size: 36px;              
                    background-image: var(--accent-gradient);
                    -webkit-background-clip: text;
                    -webkit-text-fill-color: transparent;
                    background-size: 400%;
                    background-position: 0%;
                }
            }
        }
        .navigation {
            float: right;
            .burger-icon {
                margin: 25px 30px;
                cursor: pointer;
                div {
                    width: 36px;
                    height: 3px;
                    margin: 6px 0px;
                    background-color: #27332F;
                }
                .burger-icon-bar1 {
                    transform: translateY(5px);
                    transition: 0.5s;
                }
                .burger-icon-bar2 {
                    background-color: #fff;
                }
                .burger-icon-bar3 {
                    transition: 0.5s;
                }
            }
            .opened {
                .burger-icon-bar1 {
                    transform: translateY(10px);
                }
                .burger-icon-bar3 {
                    transform: translateY(-8px);
                    transition: 0.5s;
                }
            }
            .navigation-list {
                position: fixed;
                top: 0;
                left: 0;
                margin-top: 73px;
                margin-left: 10%;
                width: 90%;
                height: calc(100vh - 73px);
                transform: translateX(90vw);
                transition: 0.7s;
                background-color: #fff;
                z-index: 2;
                .navigation-list-title {
                    float: left;
                    margin: 50px;
                    width: 50%;
                    color: #27332F;
                    h1 {
                        font-size: 36px;
                        .text-gradient {
                            background: #B47AEA;
                            background: linear-gradient(to right, #B47AEA 23%, #FFC4EB 100%);
                            -webkit-background-clip: text;
                            -webkit-text-fill-color: transparent;
                        }
                    }
                    p {
                        margin: 10px 0px;
                        color: rgb(107, 107, 107);
                    }
                }
                ul {
                    float: left;
                    margin: 50px;
                    h1 {
                        font-size: 24px;
                    }
                    li {
                        list-style-type: none;
                        margin: 5px 0px;
                        a:link, a:visited {
                            color: #27332F;
                            text-decoration: none;
                            font-size: 20px;
                        }
                    }
                }
            }
            .navOpened {
                transform: translateX(0px);
            }
        }
    }
    header::after {
        clear: both;
        content: "";
        display: table;
    }

    @media only screen and (max-width: 600px) {
        header {
            .logo {
                h1 {
                    font-size: 20px;
                }
            }
            .navigation {
                .navigation-list {
                    .navigation-list-title {
                        margin-bottom: 0px;
                        h1 {
                            font-size: 24px;
                        }
                    }
                    ul {
                        h1 {
                                font-size: 20px;
                        }
                        li {
                            a:link, a:visited {
                                font-size: 18px;
                            }
                        }
                    }
                }
            }
        }
    }

@media only screen and (min-width: 950px) {
    header {
        .navigation {
            .navigation-list {
                .navigation-list-title {
                    h1 {
                        font-size: 46px;
                    }
                    p {
                        font-size: 20px;
                    }
                }
                ul {
                    h1 {
                            font-size: 32px;
                    }
                    li {
                        a:link, a:visited {
                            margin: 10px 0px;
                            font-size: 24px;
                        }
                    }
                }
            }
        }
    }
}
</style>
