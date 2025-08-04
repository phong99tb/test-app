<template>
    <div class="over" style="background-color: #FCF9FC; ">
        <div class="container">
            <p class="mb-50" style="font-size: 16px;">トップ > 掲示板 > 老人ホームの種類 > 住宅型有料老人ホーム > 住宅型有料老人ホームについて</p>
            <div class="flex" style="gap: 100px;">
                <div style="flex-grow: 1;">
                    <p style="font-size: 32px; margin-bottom: 30px;">老人ホームの種類</p>
                    <div class="flex" style="align-items: center; margin-bottom: 25px;">
                        <p style="color: #999999; font-size: 18px; margin-right: 20px;">2022.05.08</p>
                        <button class="button" style="font-size: 12px;">介護付き有料老人ホーム </button>
                    </div>
                    <div class="flex" style="gap: 15px; align-items: center; margin-bottom: 30px;">
                        <div style="display: flex; align-items: center; gap: 10px;">
                            <img src="../assets/img/Edit Property.svg" alt="edit" />
                            <p style="font-size: 20px;">介護保険制度</p>
                        </div>
                        <div style="display: flex; align-items: center; gap: 10px;">
                            <img src="../assets/img/Help.svg" alt="help" />
                            <p style="font-size: 20px;">その他</p>
                        </div>
                    </div>
                    <div class="flex">
                        <p class="overText mr-10" style="background-color: #FFB2B2;">Q</p>
                        <div style="display: flex; flex-direction: column; gap: 10px;">
                            <p style="font-size: 30px;">住宅型有料老人ホームについて</p>
                            <p style="font-size: 24px;">住宅型有料老人ホームで、介護サービスを受けることはできるのですか？</p>
                            <p style="font-size: 20px;">大阪府、40代、男性、くまのプーさん</p>
                        </div>
                    </div>
                    <img src="../assets/img/banner.svg" alt="banner" style="width: 100%; object-fit: contain;" />
                    <div class="flex">
                        <p class="overText mr-10" style="background-color: #FFF0F0;">A</p>
                        <div style="display: flex; flex-direction: column; gap: 10px;">
                            <p style="font-size: 30px;">可能ですが、介護付有料老人ホームと比べると、劣る部分もあります</p>
                            <p style="font-size: 20px;">はい、可能です。</p>
                            <p style="font-size: 20px;">
                                ただ住宅型有料老人ホームで介護を受ける時は、外部の介護業者と契約を締結した後になりますので、介護付有料老人ホームと比較すると対応の柔軟さやサービス頻度の部分は望めません。
                            </p>
                            <p style="font-size: 20px;">そのため住宅型有料老人ホームは、介護があまり必要でない自立した方向けの施設と言えます。</p>
                        </div>
                    </div>
                    <p style="font-size: 30px; margin-top: 30px; margin-bottom: 10px;">答えてくれたのは…</p>
                    <div class="card" style="display: flex; padding: 60px; gap: 80px;">
                        <div class="flex" style="flex-direction: column; align-items: center;">
                            <img src="../assets/img/Avatar.png" alt="avatar" style="width: 150px;" />
                            <button class="buttonZoom">zoomで相談する</button>
                        </div>
                        <div style="margin-top: 25px;">
                            <p style="font-size: 26px;">ケアマネージャー</p>
                            <p style="font-size: 26px;">吉本達志さん</p>
                            <p style="font-size: 17px;">【経歴】</p>
                            <p style="font-size: 17px;">〇〇〇〇年生まれ。</p>
                            <p style="font-size: 17px;">〇〇〇〇年、〇〇〇〇大学を卒業後、約〇〇年〇〇〇〇として〇〇〇〇に勤務。</p>
                            <p style="font-size: 17px;">〇〇〇〇年、介護支援専門員（ケアマネジャー）の資格取得。</p>
                        </div>
                    </div>
                </div>
                <div style="max-width: 470px;">
                    <div class="cardMini">
                        <img src="../assets/img/2people.svg" />
                        <p style="font-size: 30px;">介護なんでも相談室について</p>
                    </div>
                    <div style="margin-top: 60px;">
                        <div class="viewTitle mb-50" >
                            <p style="font-size: 36px;">Article Ranking</p>
                            <p style="font-size: 16px; margin-bottom: 10px;">人気記事ランキング</p>
                        </div>
                        <News v-for="(item, index) in newsList" :key="index" :img="item.img" :date="item.date"
                            :likes="item.likes" :title="item.title" :isFirst="index === 0"
                            :isLast="index === newsList.length - 1" />
                    </div>
                    <div class="viewTitle" style="margin-top: 85px; margin-bottom: 50px;">
                        <p style="font-size: 36px;">Popular keywords</p>
                        <p style="font-size: 16px; margin-bottom: 10px;">人気キーワード</p>
                    </div>
                    <div style="display: flex; gap: 20px; flex-wrap: wrap;">
                        <div v-for="(tag, index) in tags" :key="index" class="tag">
                            {{ tag }}
                        </div>
                    </div>
                </div>
            </div>
            <div style="margin-top: 185px;">
                <div class="viewTitle" style="margin-bottom: 45px;">
                    <p style="font-size: 36px;">Consultation Method</p>
                    <p style="font-size: 16px; margin-bottom: 10px;">相談方法</p>
                </div>
                <p style="font-size: 24px; line-height: 40px; max-width: 900px; margin: 0 auto; text-align: center;">
                    電話、zoomでのご相談は、平日の9：00～18：00の時間帯で受け付けています。掲示板、メール、LINEでのご相談は、24時間受け付ています。</p>
                <div class="grid-5" style="display: grid; gap: 25px; margin-top: 35px;">
                    <Consultation v-for="(item, index) in consultations" :key="index" :title="item.title"
                        :time="item.time" :bg="item.bg" />
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import Consultation from '../components/Consultation.vue';
import News from '../components/News.vue';
import imgNew from '../assets/img/img-new.svg'

import bg1 from '../assets/img/consultation1.svg'
import bg2 from '../assets/img/consultation2.svg'
import bg3 from '../assets/img/consultation3.svg'
import bg4 from '../assets/img/consultation4.svg'
import bg5 from '../assets/img/consultation5.svg'

const consultations = [
    { title: '掲示板', time: '受付時間：24時間受付', bg: bg1 },
    { title: 'メール', time: '受付時間：24時間受付', bg: bg2 },
    { title: '電話', time: '受付時間：平日9：00～18：00', bg: bg3 },
    { title: 'zoom', time: '受付時間：平日9：00～18：00', bg: bg4 },
    { title: 'LINE', time: '受付時間：24時間受付', bg: bg5 },
]

const tags = [
    '老人ホーム',
    '費用',
    '訪問',
    '通所',
    '看護',
    'リハビリ',
];
const newsList = [
    {
        img: imgNew,
        date: '2022.04.08',
        likes: 258,
        title: '県外の介護付き有料老人ホームに入居可能か？'
    },
    {
        img: imgNew,
        date: '2022.03.12',
        likes: 198,
        title: '介護施設の費用はどれくらいかかる？'
    },
    {
        img: imgNew,
        date: '2022.02.25',
        likes: 134,
        title: '訪問介護と通所介護の違いとは？'
    },
    {
        img: imgNew,
        date: '2022.01.30',
        likes: 322,
        title: '介護リハビリの基本的な流れ'
    },
    {
        img: imgNew,
        date: '2021.12.15',
        likes: 411,
        title: '看護師が教える安心の介護術'
    }
]

</script>

<style scoped>
.viewTitle {
    display: flex;
    align-items: end;
    gap: 10px;
}
.mb-50 {
    margin-bottom: 50px;
}
.container {
    width: 85%;
    margin: 0 auto;
    padding: 0 0 30px;
}

.over {
    width: 100%;
    max-width: 100%;
}

.tag {
    height: 60px;
    padding: 0 35px;
    box-shadow: 0px 2px 10px 0px #00000040;
    border-radius: 60px;
    line-height: 60px;
    display: inline-block;
    font-size: 24px;
}

.buttonZoom {
    font-size: 15px;
    background-color: #0D2340;
    box-shadow: 0px 2px 10px 0px #00000026;
    color: #fff;
    border-radius: 10px;
    padding: 7px 15px;
    /* max-width: 150px; */
}

.cardMini {
    display: flex;
    gap: 28px;
    border-radius: 10px;
    padding: 20px;
    background-color: #FFFFFF;
    min-width: 470px;
    align-items: center;
    text-align: center;
    box-shadow: 0px 2px 10px 0px #00000040;
}

.card {
    border-radius: 20px;
    box-shadow: 0px 2px 10px 0px #00000040;
    background-color: #FFFFFF;
}

.button {
    height: 37.5px;
    width: 200px;
    background-color: #fff;
    border: 1px solid #000;
    border-radius: 5px;
}

.flex {
    display: flex;
}

.mr-10 {
    margin-right: 10px;
}

.overText {
    width: 40px;
    min-width: 40px;
    height: 40px;
    min-height: 40px;
    box-shadow: 0px 2px 10px 0px #00000040;
    border-radius: 1000px;
    text-align: center;
    line-height: 40px;
    font-size: 20px;
}

.grid-5 {
    grid-template-columns: repeat(5, 1fr);
}

@media (max-width: 768px) {
    .viewTitle {
        flex-direction: column;
        align-items: start;
    }
    .mb-50 {
        margin-bottom: 20px;
    }
    .container {
        width: 90%;
        padding: 0 0 20px;
    }

    .flex {
        flex-direction: column;
        gap: 20px !important;
    }

    .tag {
        font-size: 18px;
        height: auto;
        padding: 10px 20px;
        line-height: 1.5;
    }

    .cardMini {
        flex-direction: column;
        gap: 20px;
        min-width: unset;
        /* width: 100%; */
        text-align: center;
    }

    .card {
        flex-direction: column;
        padding: 30px;
        gap: 30px;
    }

    .card img {
        width: 100px;
    }

    .buttonZoom {
        width: 100%;
        text-align: center;
    }

    .button {
        width: 100%;
    }

    .overText {
        font-size: 16px;
        width: 30px;
        height: 30px;
        /* line-height: 30px; */
    }

    .mr-10 {
        margin-right: 0;
        margin-bottom: 10px;
    }

    .grid-5 {
        grid-template-columns: repeat(1, 1fr);
    }

    .article-title {
        font-size: 24px !important;
    }

    .article-subtitle,
    .article-user,
    .article-answer {
        font-size: 18px !important;
    }
}
</style>
