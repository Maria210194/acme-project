<template>
    <footer>
        <div class="black_footer d_flex color_white">
            <div class="logo_footer">
                <img src="@/assets/img/logo_white.png" alt="Logo_Acme_Corporation">
            </div>
            <h2 class="title_footer">Acme Corp Inc.</h2>
            <span class="fs_plus">Via Emilio De Marchi 4, Milano(MI) - ITALY</span>
            <span class="fs_plus"><a href="#" id="link" class="color_white tx_dec">info@acmecorp.com</a></span>
            <span class="fs_min">Designed by Deeelp</span>
        </div>
        <div class="red_footer d_flex">
            <ul class="link_footer d_flex">
                <li><a class="color_white tx_dec" href="#">2022 Acme Corp Inc. - P.IVA 01234567890</a></li>
                <li><a class="color_white tx_dec" href="#">PRIVACY POLICY</a></li>
                <li><a class="color_white tx_dec" href="#">COOKIE POLICY</a></li>
                <li><a class="color_white tx_dec" href="#">COOKIES PREFERENCES</a></li>
            </ul>
        </div>
    </footer>
</template>

<script>
export default {
    name: 'FooterComponent'
}
</script>

<style lang="scss" scoped>
footer{
    width: 100%;

    .black_footer{
        width: 100vw;
        overflow-x: none;
        justify-content: center;
        align-items: center;
        display: flex;
        flex-direction: column;
        background-color: #211E1E;
        color:white;
        padding: 15px 0 10px 0;

        .logo_footer{
            padding: 1.5rem 1.1rem 1.1rem 1.1rem;  
        }

        .logo_footer img {
            width: 150px;
        }

        .title_footer{
            font-size: 1rem;
            padding-bottom: 1.1rem;

        }
        
        #link {
            color: white !important;
            text-decoration: none;
        }

        .fs_plus{
            font-size: 0.9rem;
            padding: 5px 0;
        }

        .fs_min{
            font-size: 0.7rem;
            padding-top: 10px;
        }
    }

    .red_footer{
        width: 100%;
        overflow-x: none;
        justify-content: center;
        align-items: center;
        display: flex;
        background-color: #d70f0f;
        padding: 14px 0;

        .company_footer{
            color:white;
            padding: 0 10px;
        }

        .link_footer li{
            color:white;
            padding: 0 5px;
            text-decoration: none;
            font-size: 0.8rem;
        }

        .link_footer{
            justify-content: center;
            align-items: center;
            display: flex;
            list-style: none;
            padding: 0 10px;
        }

        .link_footer li a{
            color:white;
            padding: 0 5px;
            text-decoration: none;
        }
    }
}

@media screen and (max-width: 700px) {
    footer {
        .red_footer {

            .link_footer {
                flex-direction: column;
                padding: 0;
            }
            .link_footer li a{
                font-size: 11px;
            }
        }
    }
}

// @media screen and (max-width: 350px) {
//     footer {
//         .red_footer {
//             .link_footer li a{
//                 flex-direction: column;
//                 padding: 10px;
//             }
//         }
//     }
// }

</style>