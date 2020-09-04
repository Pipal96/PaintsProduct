<template>
    <div id="app-header">
        <b-container>
            <div class="wrapper">
                <b-container fluid>
                    <b-row>
                        <b-col>
                            <div class="app-header__top">
                                <div class="logo"><a href="#" aria-label="логотип 'краска'">
                                        <picture>
                                            <source srcset="/img/Logo.webp, /img/Logo@2x.webp 2x, /img/Logo@3x.webp 3x"
                                                type="image/webp">
                                            <img src="/img/Logo.png" alt="логотип краски"
                                                srcset="/img/Logo@2x.png 2x, img/Logo@3x.png 3x">
                                        </picture>
                                    </a>
                                </div>
                                <div class="contact d-none d-sm-flex">

                                    <div class="contact__block">
                                        <div class="contact__link "><a class="text-dark"
                                                href="tel:+79787654321">{{tel}}</a></div>
                                        <!-- править атрибут телефона -->
                                        <div class="contact__link"><a class="text-dark"
                                                href="tel:+79787654321">{{tel}}</a></div>
                                    </div>

                                    <div class="contact__block">
                                        <div class="contact__link d-none d-lg-flex">
                                            <p>{{work_time_weekdays}}</p>
                                        </div>
                                        <!-- править атрибут телефона -->
                                        <div class="contact__link d-none d-lg-flex">
                                            <p>{{work_time_weekend}}</p>
                                        </div>
                                    </div>

                                    <div class="contact__block contact__block_disabled">
                                        <div class="contact__link"><a class="text-dark" href="#">{{addressPart1}}
                                                <br>
                                                {{addressPart2}}</a></div>
                                    </div>
                                </div>
                            </div>
                        </b-col>
                    </b-row>
                </b-container>
            </div>
        </b-container>
        <app-navbar></app-navbar>
    </div>
</template>

<script>
    import Navbar from './Navbar.vue';


    export default {
        components: {
            'app-navbar': Navbar,
        },
        data() {
            return {
                tel: '+7(978)765-43-21',
                addressPart1: 'г. Симферополь',
                addressPart2: 'ул. Киевская,12',
                visibilityAddressCell: true,
                work_time_weekdays: 'пн-пт:  с 9 до 17',
                work_time_weekend: 'сб-вс: с 10 до 14'
            }
        },
        methods: {},
    }
</script>


<style lang="scss" scoped>
    $white_color: #f8f4ee;
    $heigth_top_header_max: 180px;
    $heigth_top_header_min: 90px;

    #app-header {
        width: 100%;
        background-color: $white_color;
        // max-height: $heigth_top_header_max;
        // min-height: $heigth_top_header_min;
    }

    a {
        font-size: 14px;
    }

    @media screen {
        a {
            font-size: 12px
        }
    }

    .app-header__top {
        display: flex;
        justify-content: space-between;
        align-items: center;
        max-height: $heigth_top_header_max;
        min-height: $heigth_top_header_min;
        height: 130px;
    }

    .wrapper {
        min-width: 320px;
        max-width: 1603px;
        height: 100%;
        margin: 0;
        padding: 0 5px;
        box-sizing: border-box;
        max-height: $heigth_top_header_max;
        min-height: $heigth_top_header_min;
    }

    // @media all and (min-width:480px) {
    //     .wrapper {
    //         padding: 0 60px;
    //     }
    // }

    .logo img {
        width: 163px;
        height: 60px;
        margin-top: -21px;
    }

    @media all and (max-width: 480px) {
        .logo img {
            width: 120px;
            height: 45px;
        }
    }


    .contact {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 660px;

        .contact__block {
            margin-left: 10px;

            .contact__link a,
            .contact__link p {
                font-size: 16px;
            }
        }

        p {
            margin: 0;
        }
    }

    @media all and (max-width: 560px) {
        .contact__block_disabled {
            display: none;
        }

        .contact {
            justify-content: flex-end;
        }
    }

    @media all and(max-width:370px) {
        .contact {
            max-width: 0px;
            min-width: 0px;
            width: 0px;
        }
    }
</style>