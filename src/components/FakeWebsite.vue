<template>
  <div>
    <header>
      <div class="upLink">
        <div style="width: 75px">
          <a href="https://www.dcard.tw/f"><img src="../../public/logo.svg" id="DC_logo" alt="DC_logo" /></a>
        </div>
      </div>
    </header>

    <div class="all_thing">
      <div class="left_thing">
        <div class="dcard_QR">
          <img src="../../public/border.webp" id="border" alt="border" />
          <img src="../../public/QRcode.webp" id="qrcode" alt="qrcode" />
          <p id="qrText">立即掃描下載 Dcard App！</p>
        </div>

        <div class="content">
          <h1 id="left">年輕人都在 Dcard 上討論</h1>
          <p>不想錯過任何有趣的話題嗎？<br />趕快加入我們吧！</p>
          <a href="https://www.dcard.tw/f">先看討論區</a>
        </div>

        <div class="market_icon_block">
          <a href="https://reurl.cc/pLRe0Q"><img src="../../public/googlePlayIcon.webp" class="marketIcon" alt="googlePlayIcon" /></a>
          <a href="https://reurl.cc/Adlvv3"><img src="../../public/appStoreIcon.webp" class="marketIcon" alt="appStoreIcon" /></a>
        </div>
      </div>

      <div class="right_thing">
        <div class="thing_in_right">
          <div style="height: 400px">
            <div id="sign_up_title">註冊 / 登入</div>
            <div style="justify-content: space-between;">
              <div style="flex-direction: row; display: flex; justify-content: space-between;">
                <p id="signingMode" style="font-size: 14px;">常用信箱</p>
                <a id="signingChange" style="font-size: 14px; margin-top: 8px" @click="changeMode()">使用手機登入</a>
              </div>
              <div id="upon" style="flex-direction: row; display: flex; justify-content: space-between;">
                <input class="EmailAndPassword" id="inputMode" name="email" autocomplete="email" placeholder="輸入信箱" type="email" v-model="email" />
              </div>
            </div>
            <div style="justify-content: space-between;">
              <p style="font-size: 14px;">密碼</p>
              <input class="EmailAndPassword" name="password" autocomplete="current-password" placeholder="輸入密碼" type="password" v-model="password" />
            </div>
            <button type="submit" id="send_botton" @click="login">
              <div style="color: white">註冊 / 登入</div>
            </button>
            <div class="otherway">
              <a>未收到驗證信</a>
              &nbsp;&nbsp;
              <a>忘記密碼</a>
            </div>
          </div>
        </div>
        <p style="font-size: 14px; line-height: 2; margin-top: 30px; margin-bottom: 20px; text-align: center; color: #7f7f7f">註冊/登入即代表您同意遵守 <a style="color: #7f7f7f; text-decoration: underline;" href="https://www.dcard.tw/terms">Dcard 使用協議</a></p>
      </div>
    </div>
  </div>
</template>

<script>
let mode = 1;
export default {
  data() {
    return {
      email: '',
      password: ''
    };
  },
  methods: {
    changeMode() {
      if (mode === 1){
        document.getElementById("signingChange").textContent = "使用email註冊/登入";
        document.getElementById("signingMode").textContent = "手機號碼";

        document.getElementById("inputMode").placeholder="請輸入手機號碼";

        let parentDiv = document.getElementById("upon");
        let MySelect = document.createElement("select");
        MySelect.setAttribute("id", "newSelect");

        let option1 = document.createElement("option");
        option1.text="+886";
        MySelect.add(option1);
        let option2 = document.createElement("option");
        option2.text="+852";
        MySelect.add(option2);
        let option3 = document.createElement("option");
        option3.text="+853";
        MySelect.add(option3);
        let option4 = document.createElement("option");
        option4.text="+1";
        MySelect.add(option4);
        let option5 = document.createElement("option");
        option5.text="+7";
        MySelect.add(option5);
        let option6 = document.createElement("option");
        option6.text="+20";
        MySelect.add(option6);
        let option7 = document.createElement("option");
        option7.text="+27";
        MySelect.add(option7);



        let OldInput = document.getElementById("inputMode");
        parentDiv.insertBefore(MySelect, OldInput);

        OldInput.style.width="300px";

        mode = 2;
      } else if (mode === 2){
        document.getElementById("signingChange").textContent = "使用手機登入";
        document.getElementById("signingMode").textContent = "常用信箱";

        document.getElementById("inputMode").placeholder="輸入信箱";

        document.getElementById("newSelect").remove();
        document.getElementById("inputMode").style.width="100%";


        mode = 1;
      }
    },
    login() {
      // Implement the login functionality here
    }
  }
};
</script>

<style scoped>

</style>