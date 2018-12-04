---
title: Change docs/index.md
summary: Change This
---
# Changing the Site URL

First, edit the site name in the [Netlify Control Panel]()

![Setting a url for the site](https://i.imgur.com/dweJGw3.png)

# Creating your Discord Wiki

So, you probably already pressed that netlify button, gave your repository name.

## Mkdocs.yml configuration

First, edit your `mkdocs.yml` in the root of this repository.
You can edit it through the github site.

to find where your repos are you can click on your avatar on the top right corner while logged into github:
![repo location](https://i.imgur.com/POrxqb0.png)

navigate through the files and open the one you want to edit. there should be an edit button like below.

![editing the mkdocs.yml](https://i.imgur.com/7rvAiao.png)

edit the following entries:

- line 2 `site_name`
- line 3 `site_description`
- line 4 `site_author`
- line 5 `site_url`
- line 8 `repo_name` (this one is your discord link text)
- line 9 `repo_url` (this one is a permanent invite link to your discord)
- line 16 `social: link`

> Optional: You can edit the nav to customize the menu ordering and names. If you don't, mkdocs build it manually. (see line 29)

---

## Creating the admin screen

We're done for the mkdocs.yml file, now you need to configure the Admin interface where you can edit/create pages easily.

You will need to edit the file `docs/admin/config.yml`

edit the following entry:
- line 6 `repo`: Insert your repo path, this should be your githubusername/yourreponame. the repo name is what you've inserted into the name field when you've clicked into the netlify deploy button.

now you should be good to go, but if you want to add new categories in the side menu you have to do it here.
Check line 14 in the config.yml file.

You can just copy the following structure over and edit it to create a new category inside the `collections:`

```yml
  - name: "General"
    label: "General"
    folder: "docs"
    create: true
    slug: "{{slug}}"
    fields:
    - {label: "Title", name: "title", widget: "string"}
    - {label: "Summary", name: "summary", widget: "string"}
    - {label: "Body", name: "body", widget: "markdown"}
```

**Make sure in folder you put the correct folder name**, you can check the ones that are already there for an example.

## Creating Users

The final Step is to add authentication. This part will be done in the [Netlify Control Panel](https://app.netlify.com/).
Click on your site and proceed.

Go to the Identity tab

![Identity](https://i.imgur.com/E5anoSO.png)

Scroll down to Registration and do as so:

![Registration](https://i.imgur.com/Gv51pCU.png)

Scroll down to Services and enable git gateway:

![Git Gateway](https://i.imgur.com/GuyPQF0.png)

Now go to the Identity area in the top menu:

![Identity on top menu](https://i.imgur.com/6NxRNgl.png)

You can Invite users from there. Just put their gmail there and they will recieve a link. When you click the link you will be on your site, with a popup asking for you to register. Do as they say and you will be in the Admin Page.  Send an invite for yourself to continue.

To go to the admin page, just go to the home page and add `/admin` to the end of the url in your browser. Click the button and login.

You will be on this screen:
![admin interface](https://i.imgur.com/ejLt2uB.png)

You're free to edit your pages there.
