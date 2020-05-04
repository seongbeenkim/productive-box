<p align="center">
  <a href="http://lovera.maxam.now.sh/">
    <img src="https://user-images.githubusercontent.com/25841814/79395484-5081ae80-7fac-11ea-9e27-ac91472e31dd.png" alt="screenshot" width="500">
  </a>
  <h3 align="center">📌✨productive-box</h3>
</p>

<p align="center">
   <img src="https://img.shields.io/badge/language-typescript-blue?style"/>
   <img src="https://img.shields.io/github/license/maxam2017/productive-box"/>
   <img src="https://img.shields.io/github/stars/maxam2017/productive-box"/>
   <img src="https://img.shields.io/github/forks/maxam2017/productive-box"/>
</p>
<p align="center">
   Are you an early 🐤 or a night 🦉?
   <br/>
   When are you most productive during the day?
   <br/>
   Let's check out in gist!
</p>

---
<p align="center">
  <b>
    <a href="https://github.com/maxam2017/productive-box"> maxam2017/productive-box</a>의 설치 과정을 한국어로 번역하고 </br>
  코드 일부분을 한국어 사용자들에 맞게 수정한 저장소입니다.</br>
  번역이 매끄럽지 않거나 수정해야할 부분이 있을 경우 말씀해주시면 감사하겠습니다.
</b>
</p>   

> This project is inspired by an awesome pinned-gist project.   
__이 프로젝트는 awesome pinned-gist project에 의해 영감을 받았습니다.__   
   
> Find more in https://github.com/matchai/awesome-pinned-gists   
__해당 프로젝트에 대해서는 https://github.com/matchai/awesome-pinned-gists 에서 확인해보세요.__

## Overview
This project uses GitHub graphQL API to get the commit histories and write into the gist by [rest.js](https://github.com/octokit/rest.js#readme)   
__이 프로젝트는 [rest.js](https://github.com/octokit/rest.js#readme)로 commit 히스토리들을 가져오고 gist에 명시하기 위해서 GitHub graphQL API를 사용하였습니다.__   

## Setup

### Prep work(사전 준비 작업)
1. Create a new public GitHub Gist (https://gist.github.com/)   
__새로운 Github Gist를 생성해주세요.__   
2. Create a token with the `gist` and `repo` scope and copy it. (https://github.com/settings/tokens/new)   
__'gist'와 'repo' 영역에 체크를 해주시고 토큰을 생성해주세요.__ (https://github.com/settings/tokens/new)   
__+ 토큰이 생성되면 해당 토큰의 값을 따로 기록해 놓으세요__
   > enable `repo` scope seems **DANGEROUS**   
   > __'repo' 영역을 체크하는 것이 위험해 보일 수 있습니다.__   
   > but this GitHub Action only accesses your commit timestamp in repository you contributed.   
   > __하지만 해당 Github Action은 오직 사용자가 기여한 repository에서의 commit timestamp만 접근합니다.__

### Project setup(프로젝트 설치)

1. Fork this repo   
__해당 저장소를 fork 해주세요.__
2. Open the "Actions" tab of your fork and click the "enable" button   
__fork한 저장소의 "Actions" 탭을 열고 "enable" 버튼을 클릭해주세요.__   
3. ~~Edit the [environment variable](https://github.com/maxam2017/productive-box/blob/master/.github/workflows/schedule.yml#L17-L18) in `.github/workflows/schedule.yml`:~~   
__+ 환경 변수부분을 조금 변경해놓았습니다. 아래의 내용을 참고해주세요.__   

   - **GIST_ID:** The ID portion from your gist url: `https://gist.github.com/maxam2017/`**`9842e074b8ee46aef76fd0d493bae0ed`**.   
   __**GIST_ID:** 사전 준비 작업에서 생성한 gist url: `https://gist.github.com/maxam2017/"9842e074b8ee46aef76fd0d493bae0ed"` 에서 ""에 있는 ID 부분__   
   - ~~**LOCALE:** The locale of your country, eg. `zh-TW` for Taiwan, `en-US` for America, etc.~~
   - __LOCALE은 ko-KR로 미리 변경을 해놓았습니다.__   
   - __+ GH_TOKEN: 사전 준비 작업에서 생성한 토큰 값 `bf9757eaacd6cd1df431e6fb8e6dae3f3518dc9c`__

4. Go to the repo **Settings > Secrets**   
__저장소의 Setting > Secrets 창으로 이동해주세요.__   
5. Add the following environment variables:   
__아래의 환경변수를 추가해주세요.__   
   - **GH_TOKEN:** The GitHub token generated above.   
   __GH_TOKEN: 변수 이름을 "GH_TOKEN"로 작성하고 사전 준비 작업에서 생성한 Github 토큰의 값을 넣어줍니다.__   
   - __+ GIST_ID: 변수 이름을 "GIST_ID"로 작성하고 위의 3을 참고하여 GIST_ID 값을 넣어줍니다.__   
6. [Pin the newly created Gist](https://help.github.com/en/github/setting-up-and-managing-your-github-profile/pinning-items-to-your-profile)   
__[새롭게 생성된 Gist를 자신의 github 페이지에 고정해주세요](https://help.github.com/en/github/setting-up-and-managing-your-github-profile/pinning-items-to-your-profile)__
