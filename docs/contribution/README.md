# Content Guideline

## Where content lives

Content is organized by **age group**, and within each age group, by **subject**:

```
docs/
├── 3-5-years/     (Pre-School)
├── 6-9-years/      (Grade 1 to 4)
├── 10-13-years/    (Grade 5 to 8)
├── 14-15-years/    (Grade 9 to 10)
│   ├── README.md    <- overview / subject index for this age group
│   ├── maths.md
│   ├── science.md
│   ├── english.md
│   └── ethics.md
```

Each subject page (e.g. `docs/6-9-years/maths.md`) holds all topics for that subject and age group.
Add a new topic as a `##` section within the relevant subject page — don't create a new file per topic.

If you want to add a subject that doesn't exist yet for an age group (e.g. `history.md`), create the
file following the same pattern, link it from that age group's `README.md`, and add it to `mkdocs.yaml`'s
`nav:`.

Basic idea is each topic shall be planned as per time required to finish. Do not plan anything larger than 1 hour. Follow below idea to design topic, follwing this template is must:
    
> 1. **Objective** Why is this topic important and shall be taught? What learning outcome will be achieved after completing it?
> 2. **Methodology:** There can be any kind of method to be followed to achieve the objective. It could be youtube video, blog, movie, short-films, documentary, specific book chapter, or you can be creative and add your own ideas of how it shall be taught!
> 3. **Exercise [ Optional] :** Basically homeworks. Focus on quality over quantity here. For example: More difficult task that requires original thinking than number of easy tasks!
> 4. **Evaluation Criteria:** Be Creative here. Not every topic /subject can be evaluated with same pen/paper based written examination. Main idea of this project is to to prepare students to tackle real life challanges and how basic education can help help them to become better overall human being along with useful skills. For example, Topics of history like on world wars and freedom fighters life could not be evaluated by asking them to rewrite history word-to-word as they memorize it! It can be planned as something like group discussions with topics of why it happened, what do they think what went wrong, what could have prevented it, etc. At this point, it's also needed to undestand not each evaluation criteria can be measured in quantitative ways. It can be qualitative as well. In short, **be creative and be relevant**.
> 5. **Contributor:** [ Optional ] If you like to add your name and contact / e-mail details here, in case if someone would like to reach out to you.

## Tags

Every subject page starts with a `tags:` frontmatter block, e.g.:

```markdown
---
tags:
  - maths
  - 6-9-years
---
```

Keep the subject and age-group tags already on the page, and add more as relevant to help visitors
filter content on the site's [Tags](../tags.md) page — for example `video`, `exercise`,
`group-activity`, or a specific topic name like `fractions`. Tags are site-wide, so reuse existing
tags where they fit instead of inventing near-duplicates (check `../tags.md` after building the site).

Once you submit your PR (refer below to understand how it's done), We (hoping adding more volunteers in future) would review it and if it is matching with the current ideology of this project, it will be merged into this main branch and will add your name in contributor's list after 3(!?) contributions. If we feel, PR is not matching with current ideology, or there's chance of improvement in any way, it will be mentioned in that PR specific discussion on github.

Lastly, If you want to contribute but have no idea from where to start, then refer [issues](https://github.com/EkPratishat/Awesome-Shiksha/issues) page and pick any open issues and get started! Happy Learning :)

# Technical Understanding requirement
This website is created based on Python with mkdocs. Related page are written in markdown files. 

I'm planning that any person not familiar to coding environment can also contribute to this project. So, listing out below necessary materials one should refer before starting out.

- Refer [this](https://www.markdownguide.org/basic-syntax/) to know more on how markdown files should be written and its features. 

- Refer [blog](https://dev.to/lynn_mikami_e94e5b9ad7daf/how-to-install-and-use-mkdocs-a-beginners-guide-4d53) to know how you can setup similiar webpage for your project or setup this repo in your computer to contributing this project.

- Learn about basics of [git](https://www.freecodecamp.org/news/learn-the-basics-of-git-in-under-10-minutes-da548267cc91/) that will be used to add more content from various contributor.

## Follow these steps to setup environment on your computer

1. Set up github account
    - Install git
    - Create a github [account](https://github.com/)
    - In your command line terminal type below commands:
    - Use SSH so you don't need to type password. Follow each steps in provided [link](https://docs.github.com/en/authentication/connecting-to-github-with-ssh).
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
# Windows tip: avoid line-ending noise
git config --global core.autocrlf input
```

2. Fork and Clone [Awesome-Shiksha](https://github.com/EkPratishat/Awesome-Shiksha)
    - Click Fork on GitHub
    - Clone forked project in your computer.

```bash
# If SSH not setup
git clone https://github.com/<your-username>/Awesome-Shiksha.git
# With SSH
git@github.com:<your-username>/Awesome-Shiksha.git
cd Awesome-Shiksha
```

3. Create a branch and add all of your stuff there!
```bash
git checkout -b <topic>/short-desc
# examples: maths/calculus, science/grade8
```
 - Write what ever you want to add
 - Add commit 
 - Push to remote

```bash
git add <files> or git add .
git commit -m "added pythagorus theorem"
git push
```
    

4. Open a Pull Request (PR)
    - Go to your account on github and open this repo.
    - Click **Compare & Pull Request**