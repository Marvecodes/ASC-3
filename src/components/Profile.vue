<template>
    <div class="container">
        <div class="image"><img src="https://avatars.githubusercontent.com/u/107967184?v=4" alt="avi" /></div>
        <div class="profile-content">
            <h2>{{ data.name }}</h2>
            <p>@{{ data.login }}</p>
            <h5>Front-End Developer</h5>
            <section class="section">
                <div class="stat" id="repos">
                    <p class="profile-figures" id="repo-fig">{{ data.public_repos }}</p>
                    <h3 class="profile-details"> Repositories</h3>
                </div>
                <div class="stat">
                    <p class="profile-figures">{{ data.followers }}</p>
                    <h3 class="profile-details"> Followers</h3>
                </div>
                <div class="stat">
                    <p class="profile-figures">{{ data.following }}</p>
                    <h3 class="profile-details">Following</h3>
                </div>
            </section>
        </div>
    </div>
</template>

<script>
import axios from "axios"
export default {
    name: 'ProfileSection',
    data() {
        return {
            data: "",
        };
    },
    mounted() {
        axios.get("https://api.github.com/users/marvecodes")
            .then(response => response.data)
            .then((data) => { this.data = data; })
        // console.log(data)
    }
}
</script>

<style lang="scss" scoped>
@use 'sass:math';

/* variables*/
$primary: #e38726;
$base-gap: 30px;
$text-color: #845218;
$background: rgb(254, 239, 224);
$breakpoint-minipc: 1500px;
$breakpoint-tablet: 1350px;
$breakpoint-minitab: 990px;
$breakpoint-phone: 767px;
$breakpoint-miniphone: 500px;

.container {
    display: flex;
    gap: $base-gap;
    align-items: center;
    background: rgba(177, 41, 26, 0.03);
    border: 1px solid rgba(77, 115, 248, 0.15);
    padding: $base-gap;
    border-radius: $base-gap/3;


    .image {
        width: 222px;
        height: 222px;
        padding: 5px;
        position: relative;
        border-radius: 50%;
        background: linear-gradient(to bottom, rgb(235, 183, 131), rgba(77, 115, 248, 0.15));

        img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
        }
        @media(max-width: $breakpoint-miniphone){
            width: 180px;
            height: 180px;
        }
    }

    .profile-content {
        line-height: 15px;

        @media(max-width: $breakpoint-minitab){
            line-height:normal;
            text-align:center;
        }

        h2 {
            font-family: 'Roboto';
            font-style: normal;
            font-weight: 700;
            font-size: 30px;
            color: $text-color;
        }

        p {
            font-weight: 400;
            font-size: 20px;
            color: #ef590f;
            font-family: 'Times New Roman';
            line-height: 10px;
        }

        h5 {
            font-weight: 600;
            font-size: 20px;
            color: $text-color;
            line-height: 10px;
        }

        .section {
            display: flex;
            gap: $base-gap;

            .stat {
                padding: $base-gap/3;
                width: 150px;
                background: rgba(96, 62, 35, 0.2);
                Font-color:$text-color;
                border-radius: 4px;
                text-align: center;
                line-height: $base-gap/3;
            }

            @media(max-width: $breakpoint-phone) {
flex-direction: column;
justify-content: center;
align-items: center;            }
        }
    }

    @media(max-width: $breakpoint-minitab) {
        flex-direction: column;
        text-align: center;
    }
}
</style>