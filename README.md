# 一、注意事项（必看）

1. 银行卡: OpenAI ChatGPT订阅不支持国内的VISA等银行卡，港澳的也不支持，**会拒付**，需要使用国外的银行卡。

2. IP必须是纯净的当地IP。

3. **不要使用之前白嫖过免费Team或者免费超低价Plus的账号，尽量使用新号！**

# 二、准备银行卡

推荐两个卡商，都支持开通半价双席位。

1. [Roogoo](https://wap.roogoo.money/register?inviteCode=2hrwu4) **乐享卡 **，使用邀请码首次免5美元开卡费和7天0费率。
2. [Vcc](https://vcc.agency?referrer=pi3ke7chozme4ywnw3ss)：需身份证正反面（不用KYC人脸，可找我免费获取），开卡费2美金，美国卡都支持。
3. 注意：如果开卡可指定账单地址，最好选择美国免税州的地址，不然会有税费；如果不支持指定账单地址可忽略。美国免税地址生成：https://usaddressgen.com/tax-free-address

# 三、准备家宽纯净VPN（日本）

1. SSONE（注册送1小时体验）: https://m.ssone.io/#/register?code=3RHD7UIG
2. Novproxy（联系客服领500M）：https://novproxy.com

# 四、开始订阅席位

1. 登录ChatGPT账号，这个号只有不能白嫖过会员，尽量使用国外Gmail。

2. 选择节点到日本纯净IP节点。

3. 打开优惠码优惠链接：https://chatgpt.com/?promoCode=archinesjp

4. 使用日本纯净IP节点打开链接会弹出优惠弹窗，点击升级，相当于24美元。

   ![](https://img.notionusercontent.com/s3/prod-files-secure%2F75679222-dc78-81b6-85e2-0003b96bdc6e%2F307e553f-4570-49b8-99da-359b7999483a%2Fimage.png/size/w=1410?exp=1781262536&sig=zR1wYzsDHHtcQGta4GZpvtvp-MaAfTmm9PmDEu7QG3U&imgBuildSrc=presignImageUrl&id=37b79222-dc78-80d4-b2ad-d26688e4bbbd&table=block&mtd=com)

5. 进入后选择**2个**席位；使用长链脚本打开支付页面。

   ![](https://img.notionusercontent.com/s3/prod-files-secure%2F75679222-dc78-81b6-85e2-0003b96bdc6e%2F334d0b2c-b116-430f-8188-486d12e83189%2Fimage.png/size/w=1410?exp=1781262660&sig=EWTwtfryNyn-H2TKT0TcrqX_dOPa8mXtcxe2SxWV3QU&imgBuildSrc=presignImageUrl&id=37b79222-dc78-80fd-9efc-dc0df8f2b06a&table=block&mtd=com)

   ![](https://img.notionusercontent.com/s3/prod-files-secure%2F75679222-dc78-81b6-85e2-0003b96bdc6e%2Fb965418e-9555-4b92-b8c4-799d147983b4%2Fimage.png/size/w=1410?exp=1781262808&sig=WJWrg2lX7OuMiTnBCJwA3No_g_ftNvbCTxxUbKKUnew&imgBuildSrc=presignImageUrl&id=37979222-dc78-801a-9643-cb3f50bc9a46&table=block&mtd=com)

```javascript
(async function () {
    console.log("⏳ 正在为 archinesjp 生成日本版支付长链接...");
    try {
        const session = await fetch("/api/auth/session").then((r) => r.json());
        if (!session.accessToken) {
            throw new Error("无法获取 Token，请确保已登录 ChatGPT");
        }
        const payload = {
            plan_name: "chatgptteamplan",
            team_plan_data: {
                workspace_name: "myWorkspace",
                price_interval: "month",
                seat_quantity: 2
            },
            billing_details: {
                country: "JP",
                currency: "JPY"
            },
            cancel_url: "https://chatgpt.com/?promoCode=archinesjp",
            promo_code: "archinesjp",
            checkout_ui_mode: "hosted"
        };
        const response = await fetch(
            "https://chatgpt.com/backend-api/payments/checkout",
            {
                method: "POST",
                headers: {
                    Authorization: `Bearer ${session.accessToken}`,
                    "Content-Type": "application/json",
                },
                body: JSON.stringify(payload),
            }
        );
        const data = await response.json();
        if (data.url) {
            console.clear();
            console.log("%c✅ 成功生成带 archinesjp 优惠的长链接：", "color: #10a37f; font-size: 22px; font-weight: bold;");
            console.log(data.url);
            console.log("\n%c直接点开这个链接 → 应该能看到 2席位 ¥3850（48个月锁定）", "color: gray; font-size: 16px;");
        } else {
            console.error("❌ 生成失败，响应：", data);
        }
    } catch (e) {
        console.error("❌ 执行出错:", e);
    }
})();
```

6. 粘贴长链脚本到控制台回车等待获取支付长链接，点击打开支付长链接。填写银行卡和账单地址，然后点击订阅即可。免税地址生成：https://usaddressgen.com/tax-free-address。

   ![](https://img.notionusercontent.com/s3/prod-files-secure%2F75679222-dc78-81b6-85e2-0003b96bdc6e%2Fe72dab2c-7d9d-4c0a-b2d7-41951c726e74%2Fimage.png/size/w=1410?exp=1781263286&sig=q0wN8Tyx08NGS7ye7Ik3eAzrmvVN5W2lU7Cc_jLrIHw&imgBuildSrc=presignImageUrl&id=37b79222-dc78-8025-b3a1-d2dc1f363ed8&table=block&mtd=com)

   