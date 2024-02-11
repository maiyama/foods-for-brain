---
layout: post
title:  "Blog with GitHub Pages and Jekyll"
author: mai
categories: [ Jekyll, technology ]
image: assets/images/8.jpg
tags: 
---
I started my blog project using GitHub Pages about two weeks ago. I always wanted to have my own website but I did not have a motivation to do so for a while. All the fun of daily 'struggle & learn' began once I made up my mind to finally do it. <br/> 
So, below are the decisions made and actions taken to get to where I am now. 

#### Blog Name/Domain Name: What to write about? Is there a common theme? 

I knew I wanted to write about science and food but also about some random cultural insights, technology and career. It took me a while to decide a name for my blog because I didn't want to have a name that is too specific (e.g. Food&Science) or too general (e.g. Mai's blog).   There are many tools out there that randomly join your key words and generate names. You can check availability of the selected domain through these tools as well. Some examples are;

- [LeanDomainSearch] 
- [NameMesh] 
- [NameBoy]

For example, when I type in *Science* and *Food* as key words, I get choices such as;

- DigitalScienceFood
- ScienceFoodCloud
- ClickScienceFood

It can be useful to get some new ideas you haven't thought about. <br/>
This process was fun but I actually landed on **Foods for Brain** based on one of my Dropbox folders, **Brain Food**, where I kept interesting but irrelevant articles that I found during Ph.D. research. Each of our curious brain needs new stimulation (i.e. foods) to stay active and healthy! 

#### WordPress or GitHub Pages & Jekyll? 

According to [Blogging Basics 101], almost half of bloggers are using WordPress. <br/> 
Main reasons why so many people use WordPress seem to be;<br/> 

- Easy to use and "free" (of course, with some restrictions)
- Many people use it, hence there are a lot of support forums 

There are other reasons such as the speed of loading as mentioned in [Blogging Basics 101], but the ease of use and support are probably the main reasons why many blogging newbies choose WordPress over others. 

#### WHAT is and WHY GitHub Pages & Jekyll over WordPress? 

First of all, **GitHub** is;<br/>

The world's leading software development platform with version control using Git (Git is an open-source version control system started by Linus Torvalds, who created Linux). Developpers make constant changes when creating software, app, etc., and these changes should be tracked so that they can go back to where things went wrong. This is version control. <br/>
GitHub also allows open collaboration because people who are not in the development team can look and download codes and documentations. If you want to participate in the project, you `pull` the up-to-date version and `push` request to incorporate your changes. <br/>
Then, **GitHub Pages** turns your project on your GitHub account into a static website. If you have some projects on GitHub that you would like to showcase, it is very straightforward to host your "portfolio page" on GitHub Pages. Everything is on your GitHub account, nicely organized! <br/>
**Jekyll** is a static website generator, which is tightly bound to GitHub Pages. It takes text contents and turns into a nicely formatted HTML site. There are so many templates available on `jekyllthemes.org` so you have many options on how you want your site to look like!<br/> 
<br/>
Despite the popularity of WordPress, I chose to use GitHub Pages to host my blog site because;

1. I can gain control & ownership on my contents 
2. It is completely free (except for a domain name, but that's all) 
3. I already have a GitHub account 

The first point is a double-edged sword; you need to know or will learn some HTML and CSS to have the power to control what you have. No pain, no gain!<br/> By hosting your blog on GitHub Pages, what you make is yours, unlike the free version of WordPress. <br/>
Going into the point about the cost, you can actually start your blog without paying absolutely anything by following simple steps outlined on [GitHub Pages] but your domain name would not be pretty. It would be something like `yourname.github.io`. <br/>
Getting a domain can be as cheap as $2.99/year. I got mine through [GoDaddy] because I have used it before wihtout any troubles, and it offers cheap domain names. You can also look at a comparison of other options as showcased in [wpbeginner].

#### Step-by-Step 

0. [This step can happen after step 6] Come up with a blog name and buy a domain name
1. Pick a theme on `jekyllthemes.org`
2. Fork the theme you picked so that you have the copy on your repo. 
3. Go into the Settings (circled in red below) and change your repository name from the name set by the theme creator. (in my case, I changed it from "mundana-theme-jekyll" to "foods-for-brain")
4. Go down to **GitHub Pages** section. Change the **Source** from None to master branch if you are using the master branch. 

<div style="text-align:center"><img src="{{ site.url }}/assets/images/github1.png" alt="github" width="500"/></div>

5. In the same section, add custom domain if you already got one, and make sure to check **Enforce HTTPS** If not, you can leave it as is.

<div style="text-align:center"><img src="{{ site.url }}/assets/images/github2.png" alt="github2" width="500"/></div>

That's it for the first part. You already have your page with URL looking like `yourname.github.io/your_repository`. All the contents are the same as the template you got at this point and it is up to you to customize and populate the content! 

#### Next: how to play with your content locally

It makes sense to be able to make changes on your site locally in your environment, instead of visiting your GitHub account directly, right? <br/> By installing Ruby and Jekyll, you can deploy and browse your site locally on your computer as you make changes before publishing (i.e.pushing all the changes to your master branch)! <br/>
[Jekyll] offers a super helpful guide, and I simply followed it. It definitely helps to use Linux or Mac environment as Windows is not officially supported, but there is a [way] to get around it. 

1. Install Ruby (language used to write Jekyll) & Gems (code that allows functionalities such as converting Ruby object to JSON, Interacting with GitHub, etc.). Installation guide for different operating systems can be found [here]. I followed the steps for Ubuntu. 
2. Install Jekyll and bundler gems
```
gem install jekyll bundler 
```

3. Create your local clone by clicling the green button that says **Clone or download**. <br/>
<img src="{{ site.url }}/assets/images/github4.png" alt="clone" width="500"/>
4. Get the URL.
5. Go to your teminal, change the current working directory to where you want the local copy to be and type in the following command with your URL. Now you should have a folder with the same name as your repository in the directory you specified. 
```
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
```
6. Create a new Jekyll site at your working directory
```
jekyll new YOUR-REPOSITORY
```
7. Change the directory into your blog site
8. Build the site locally
```
bundle exec jekyll serve
```
9. Now, you should be able to browse your site locally `http://localhost:4000`

##### Trouble shooting tips

- Check your jekyll and ruby version to see if they are properly installed
```
jekyll -v
ruby -v
bundler -v
```

- Check **Gemfile** and **Gemfile.lock** and make sure version names are compatible with what you have, and there are no discrepancies among the settings. In my case, the Gemfile and Gemfile.lock that were already included in the theme had something that did not match with my jekyll version so I had to change it. 

#### Next: set up a domain name

If you have decided to buy a domain and get more involved, the following steps that I took might be useful. My examples are based on GoDaddy interface but similar should apply to others.<br/>

1. Get a domain 
2. At where you got the domain from, go to **Manage DNS** and add/change the record as shown below. Don't worry about the order. 

<div style="text-align:center"><img src="{{ site.url }}/assets/images/godaddy.png" alt="DNS" width="750"/></div>

3. Go back to your GitHub account, Settings, where you left off with in the step 5 of the last section. When you type in your custom domain and check **Enforce HTTPS**, there should be a file called **CNAME** automatically created in your main repository. DO NOT CHANGE IT! Mine looks like below.

<div style="text-align:center"><img src="{{ site.url }}/assets/images/github3.png" alt="CNAME" width="650"/></div>

This last step of configuring DNS settings and getting the HTTPS certificate may take some time. I think mine took about one day. <br/>

There are many helpful tips out there, and GitHub Pages also offers a [guide to configure a custom domain]. I found the tips offered by [HACKERNOON] very helpful.

##### Help! My site shows '404 Not Found'!

After getting everything set up, my site was running fine locally BUT not on the web. 'Not Found' page showed up as I typed in `foodsforbrain.com`. <br/>
It took me a while to figure out but changing the **baseurl** section on *_config.yml* file helped. It was originally `baseurl: '/foods-for-brain'` and I had to change it to `url: 'https://foodsforbrain.com'`. <br/>

Topics that I covered here were by no means comprehensive but I hope this post would be helpful to someone out there who is thinking about starting a blog site! 


<div style="text-align:center"><img src="{{ site.url }}/assets/images/2.jpg" alt="tobimaru" width="650"/></div>


**Credit for the title photo:**

<a style="background-color:black;color:white;text-decoration:none;padding:4px 6px;font-family:-apple-system, BlinkMacSystemFont, &quot;San Francisco&quot;, &quot;Helvetica Neue&quot;, Helvetica, Ubuntu, Roboto, Noto, &quot;Segoe UI&quot;, Arial, sans-serif;font-size:12px;font-weight:bold;line-height:1.2;display:inline-block;border-radius:3px" href="https://unsplash.com/@flysi3000?utm_medium=referral&amp;utm_campaign=photographer-credit&amp;utm_content=creditBadge" target="_blank" rel="noopener noreferrer" title="Download free do whatever you want high-resolution photos from Simon Abrams"><span style="display:inline-block;padding:2px 3px"><svg xmlns="http://www.w3.org/2000/svg" style="height:12px;width:auto;position:relative;vertical-align:middle;top:-2px;fill:white" viewBox="0 0 32 32"><title>unsplash-logo</title><path d="M10 9V0h12v9H10zm12 5h10v18H0V14h10v9h12v-9z"></path></svg></span><span style="display:inline-block;padding:2px 3px">Simon Abrams</span></a>

[LeanDomainSearch]:https://leandomainsearch.com/
[NameMesh]:https://www.namemesh.com/
[NameBoy]:https://www.nameboy.com/
[Blogging Basics 101]:https://www.bloggingbasics101.com/how-do-i-start-a-blog/
[GitHub Pages]:https://pages.github.com/
[GoDaddy]:https://godaddy.com/
[wpbeginner]:https://www.wpbeginner.com/beginners-guide/how-to-choose-the-best-domain-registrar/
[guide to configure a custom domain]:https://help.github.com/en/github/working-with-github-pages/configuring-a-custom-domain-for-your-github-pages-site
[HACKERNOON]:https://hackernoon.com/how-to-set-up-godaddy-domain-with-github-pages-a9300366c7b
[Jekyll]:https://jekyllrb.com/docs/
[way]:https://jekyllrb.com/docs/installation/windows/
[here]:https://jekyllrb.com/docs/installation/

