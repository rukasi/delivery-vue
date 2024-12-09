<template>
    <section class="products">
        <div class="container">
            <div class="products-wrapper" id="good-container">

                <div class="products-card" v-for="good in goodArray" :key="good.id">
                    <div class="products-card__image">
                        <img :src="getUrl(good.image)" alt="good-1">
                    </div>
                    <div class="products-card__description">
                        <div class="products-card__description-row">
                            <h5 class="products-card__description--name">
                                {{ good.title }}
                            </h5>
                        </div>
                        <div class="products-card__description-row">
                            <p class="products-card__description--text">
                                {{ good.text }}
                            </p>
                        </div>
                        <div class="products-card__description-row">
                            <div class="products-card__description-controls">
                                <button class="btn btn-primary">
                                    В корзину
                                    <img src="../assets/images/icons/shopping-cart.svg" alt="shopping-cart">
                                </button>

                                <span class="products-card__description-controls--price">
                                    {{ good.price }} ₽
                                </span>
                            </div>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>
</template>

<script setup>
import { goodArray } from '../constants/good';
const getUrl = (name) => {
    return new URL(`../assets/images/goods/${name}`, import.meta.url)
}
</script>
