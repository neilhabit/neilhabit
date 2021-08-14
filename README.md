# 建構 Hugo Website

### 安裝與設定

Step1. Install Huro

```linux
brew install hugo
```

To verify your new install

```linux
hugo version
```

Step2. Create a new site

```linux
hugo new site {Site Folder Name}
```

Step3. Add a theme

```linux
cd {Site Folder Name}
git init
git config user.name
git config user.email
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/{Properties theme in config.toml}
```

replace theme into the project

```linux
cp -a themes/{Properties theme in config.toml}/exampleSite/* .
```

Step4. Edit baseurl and build your site

```linux
hugo serve
```

And see the result at http://localhost:1313/.

### Hugo 網站上架至 Github Pages

Step1. 將前述建立的 Repo 先 Push 至 Github 呈現 Repo Page site
此時透過 http://{your-github-account}.github.com/{Site Folder Name}

Step2. 建立 Organization site(個人主頁，一個帳號只能有一個)

> - Github repo 必需取名為 .github.io
> - master 分支中的內容會被 Build 及發佈到你的 Github Page 中 (專案主頁是利用 gh-pages 分支，這點不太一樣)

1. 建立 repo 並命名{your-github-account}.github.io
2. 新增 .github.io public as submodule

```linux
git submodule add git@github.com:{your-github-account}/{your-github-account}.github.io.git public
git config user.name
git config user.email
```

待 Github Page 編譯發佈後，訪問 http://{your-github-account}.github.io 即可看到結果。

---

References:

- [Hugo 官方資源](https://gohugo.io/getting-started/quick-start/)
- [在 Github Pages 建立 Hugo 靜態網站](https://kaichu.io/2015/07/12/my-first-post/)
