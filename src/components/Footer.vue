<template>
    <div class="footer-background w-100">
        <b-container class="py-4">
            <div class="logo py-4"><a href="#" aria-label="логотип 'краска'">
                    <picture>
                        <source srcset="/img/Logo.webp, /img/Logo@2x.webp 2x, /img/Logo@3x.webp 3x" type="image/webp">
                        <img src="/img/Logo.png" alt="логотип краски" srcset="/img/Logo@2x.png 2x, img/Logo@3x.png 3x">
                    </picture>
                </a>
            </div>

            <div class="d-flex justify-content-between">
                <div v-for="(block, index) in headlines_footer" :key="index" class="headline py-4">
                    <span class="font-weight-bold footer__headline-contact_condition">{{block.headline}}</span>
                    <ul class="list-group py-4">
                        <li class="my-1" v-for="(link, index) in block.links" :key="index">
                            <a class="text-dark footer-link_condition" href="#">{{link}}</a>
                        </li>
                    </ul>
                </div>
            </div>
            <span class="copyright">{{copyright + years}}.</span>
        </b-container>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                headlines_footer: [{
                        headline: 'Каталог',
                        links: {
                            link1: 'Краски',
                            link2: 'Эмали',
                            link3: 'Краски эмали декоративные краски, штукатурки',
                            link4: 'Лаки и масла',
                            link5: 'Герметики',
                            link6: 'Растворители',
                            link7: 'Покрытие для дерева',
                            link8: 'Инструменты',
                        },
                    },
                    {
                        headline: 'Для покупателей',
                        links: {
                            link1: 'Акции',
                            link2: 'Информация о доставке',
                            link3: 'Информация об оплате',
                            link4: 'Возврат и гарантия',
                            link5: 'Личный кабинет',
                            link6: 'Политика конфиденциальности',
                        },
                    },
                    {
                        headline: 'Контакты',
                        links: {
                            link1: 'г. Симферополь' + 'ул.Ленина д.1, этаж 2',
                            link2: '+7(978)765-43-21',
                            link3: 'magazinkrasok_simf@mail.ru',
                        },
                    },
                ],
                copyright: '© Магазин по продаже лакокрасочных материалов ',
                years: 2020,

            }
        },
    }
</script>

<style lang="scss" scoped>
    $background-color: #ccffff;
    $link-color: #f5be19 !important;
    $headline-contact-color: #336a73 !important;

    .footer-background {
        background-color: $background-color;
        min-height: 560px;
    }

    .logo img {
        height: 50px;
        width: 150px;
    }

    .list-group {
        list-style: none;
    }

    .footer-link_condition:hover {
        color: $link-color;
    }

    .footer__headline-contact_condition {
        color: $headline-contact-color;
    }

    .copyright {
        font-size: 15px;
    }
</style>