# 安心回家

[![pipeline status](https://gitlab.com/codogo-b/back-home-safe/badges/master/pipeline.svg)](https://gitlab.com/codogo-b/back-home-safe/-/commits/master)

![logo](https://gitlab.com/codogo-b/back-home-safe/-/raw/master/public/icon-192x192.png)

以 PWA(progressive web app) 形式模擬及實現安心出行功能

## 連結

主要[Dead]: <https://codogo-b.gitlab.io/back-home-safe/> \
分流: <https://codogob.github.io/back-home-safe/>

## 免責聲明

安心回家（下簡稱「本軟件」）只用作漸進式網路應用程式 (Progressive Web Apps) 學術討論用途，\
用於示範不同 mobile app 功能於網頁上的實現方式（如 QR code 掃瞄，前端資料加密等等）。\
本軟件未有以任何方式得到香港特別行政區政府（下簡稱「特區政府」）的認可。\
與特區政府推出的「安心出行」應用程式沒有任何關係，亦不是特區政府官方的追踪程式。\
因此本軟件不應取代特區政府「安心出行」應用程式。\
任何人士在使用本軟件作任何用途前，應先尋求獨立的法律意見或其他專業意見。\
用戶若因使用／未能使用本軟件，或以本軟件作任何誤用行為引致的損失、損害、法律責任或其他後果，作者概不會承擔任何法律責任，並保留追究權利。

## Disclaimer

back-home-safe (hereinafter called ‘this software’) is only used for academic use around PWA (Progressive WebApps).\
To demonstrate the implementation of native app features on the web(like QR Code Scanner, front-end encryption, etc.).\
This software is not in any way endorsed by nor affiliated with the Government of the HKSAR. It is not the official contact tracing app. DO NOT use this software as a substitute for the official LeaveHomeSafe application. The author takes no responsibility and legal liability for any misuse of this software and reserves the right to seek all remedies available by law for any violation of these Terms of Use.

## 功能

- [x] 紀錄出行場所
- [x] 紀錄的士號碼
- [x] 進入多個場所
- [x] 儲存常用場所
- [x] 自動離開
- [x] 定時刪除紀錄
- [x] 查看/刪除記錄
- [x] 加密紀錄
- [x] 導出紀錄
- [x] 隱私模式(不儲存紀錄)
- [x] 生成二維碼
- [x] i18n
- [ ] 查看確診個案

## 開發者專區

### 注意

GitHub Repository 是 Mirror GitLab\
所有 Development 需在 GitLab 進行，在 GitHub 的 PR 將不會理會

此外本人未有甄選 Repo 的 Developer role 的計劃\
所以建議在自行 Fork 的 Repo 進行 Development 再 Merge back

### For GitHub host
```
on:
  push:
    branches:
      - master
permissions:
  contents: write


    steps:
      - name: Checkout 🛎️
        uses: actions/checkout@v2.3.1

      - name: build
        run: |
          npm install --force --legacy-peer-deps
          npm run build

      - name: Deploy 🚀
        uses: JamesIves/github-pages-deploy-action@4.1.5
        with:
          branch: gh-pages # The branch the action should deploy to.
          folder: dist # The folder of build output
 ```
 `npm install`
Local testing `npm start`
Build `npm run build`

將/build 放入自己 web server 就 okay
\*\*註：一定要用 https serve
