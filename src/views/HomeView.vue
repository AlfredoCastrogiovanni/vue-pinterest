<script>
    import axios from 'axios'

    export default {
        name: "HomeView",
        data() {
            return {
                page: 1,
                images: [],
            }
        },
        methods: {
            getImages() {
                axios.get('https://picsum.photos/v2/list', {
                    params: {
                        'page': this.page,
                        'limit': 35
                    }
                }).then( response => {
                    console.log(response);
                    response.data.forEach(element => {
                        this.images.push(element);
                    });
                }).catch( error => {
                    console.log(error);
                })
            },
            fetchNextPage() {
                this.page++;
                this.getImages()
            },
            handleScroll() {
                if (window.scrollY + window.innerHeight + 300 >= document.body.scrollHeight) {
                    this.fetchNextPage();
                }
            },
        },
        created() {
            this.getImages();
        }
    }
</script>

<template>
    <div class="container" @wheel="handleScroll">
        <div class="item" :class="image.height > image.width ? 'big' : ''" v-for="image in images">
            <img :src=" image.height > image.width ? `https://picsum.photos/id/${image.id}/600/1000` : `https://picsum.photos/id/${image.id}/1000/600` " loading="lazy" quality="50">
            <span class="addButton">Salva</span>
            <span class="absolute shareButton">
                <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M20 13L20 18C20 19.1046 19.1046 20 18 20L6 20C4.89543 20 4 19.1046 4 18L4 13" stroke="#000000" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                    <path d="M16 8L12 4M12 4L8 8M12 4L12 16" stroke="#000000" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
            </span>
            <span class="absolute moreButton">
                <svg fill="#000000" width="22" height="22" viewBox="0 0 32 32" enable-background="new 0 0 32 32" id="Glyph" version="1.1" xml:space="preserve" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                    <path d="M16,13c-1.654,0-3,1.346-3,3s1.346,3,3,3s3-1.346,3-3S17.654,13,16,13z" id="XMLID_287_"/><path d="M6,13c-1.654,0-3,1.346-3,3s1.346,3,3,3s3-1.346,3-3S7.654,13,6,13z" id="XMLID_289_"/><path d="M26,13c-1.654,0-3,1.346-3,3s1.346,3,3,3s3-1.346,3-3S27.654,13,26,13z" id="XMLID_291_"/>
                </svg>
            </span>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '@/assets/scss/partials/_variables.scss' as *;
@use '@/assets/scss/partials/_mixins.scss' as *;

.container {
    display: grid;
    grid-template-columns: repeat(8, 1fr);
    gap: 15px;
    padding: 0 1rem;

    
    .item {
        border-radius: 20px;
        box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
        position: relative;

        img {
            width: 100%;
            height: 100%;
            border-radius: 20px;
            object-fit: cover;
            object-position: center;
            transition: all 0.2s ease-in;
        }

        .addButton {
            padding: .6rem .8rem;
            display: none;

            position: absolute;
            top: 15px;
            right: 15px;
            
            background-color: $primary-color;
            color: white;
            font-weight: 600;
            border-radius: 20px;
            transition: all 0.2s ease-in;
        }

        .moreButton,
        .shareButton {
            width: 30px;
            height: 30px;

            bottom: 15px;

            display: none;

            border-radius: 50%;
            background-color: white;
        }

        .moreButton {
            right: 15px;
        }

        .shareButton {
            right: 55px;
        }

        &.big {
            grid-row-end: span 2;
        }

        &:hover img {
            filter: brightness(50%);
        }

        &:hover .moreButton,
        &:hover .shareButton {
            @include flex(center, center);
        }

        &:hover .addButton {
            display: inline-block;
        }
    }
}

</style>