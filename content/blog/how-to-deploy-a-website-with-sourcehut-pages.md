+++
title = "How To Host A Website on Sourcehut Pages (With a Custom Domain)"
date = 2023-12-20
+++

Sourcehut pages, similar to GitHub pages, is a service where you can host a static website.

Deploying a website to Sourcehut pages utilizes two of Sourcehut's services - git and builds respectively.

### Understanding Sourcehut Builds

builds, as you might expect, is a build service. It essentially runs tasks for you, such as building and deploying a website. This is what you'll use to deploy your website.

To use the builds service, you need to create a build manifest. This is a YAML file which describes some information about your website to be used with sourcehut builds.

Inside of your git repository, create a file called `.build.yml` which will form your build manifest. 

By placing a `.build.yml` file in a git repository (that is also using sourcehut’s git service), your build will be submitted everytime you push.

This is great because it means every time that you update your website, the build will publish the new version automatically for you.


### Creating a Build Manifest

A build manifest takes some properties, such as `image` and `tasks` and runs them accordingly.

Inside of your `.build.yml` file, you can start adding the following properties.

```yaml
image: alpine/edge
oauth: pages.sr.ht/PAGES:RW
packages:
  - hut
  - zola
environment:
  site: example.com
tasks:
  - build: |
      cd personal-website
      zola build
  - package: |
      cd personal-website
      tar -C public -cvz . > ../site.tar.gz
  - upload: |
      hut pages publish -d $site site.tar.gz
```

What each property in the build manifest does:
- `image` sets the operating system to run your build on. `alpine/edge` is a minimal Linux distribution which aims to be efficient for servers. There is a full list of compatible images [here](https://man.sr.ht/builds.sr.ht/compatibility.md).
- `oauth` generates an oauth token for read/write permissions to be used with the sourcehut pages API.
- `packages` designates what packcages you’re going to need for the build process. The one you need to publish your site is `hut`, so that’s why we include it here. You also need to add any other dependencies you need to build you site. This means if you are using a SSG like Hugo you need to add `hugo`, if you’re using Astro you need to add `node`, etc.
- `environment` sets environment variables. If you’ve used environment variables on Linux, this will feel familiar to you. Here you should set `site` with your domain.
- `tasks` is a bit harder to define. If you have some plain HTML, CSS, and JS, you can just generate a tarball from the directory. However, if you are using a static site generator, you will need to build the website and make a tarball of the output. 

In the example above, I build the website with `zola build`, then tarball the `public` directory where the website output is created. Tarballing it just compresses it so you’re sending it zipped to users browsers, so smaller files to to be sent.

Uploading uses the `hut` cli tool installed earlier, and passes the domain you want to deploy to with `-d` flag with the `$site` environment variable. You can use a custom domain here or use your Sourcehut username followed by `.srht.site` e.g. `name.srht.site`.

To use a custom domain, in your domain settings (wherever you purchased the domain) you need to set up a new A record, with the name `@` and the value `173.195.146.139` .

### Deploying Your Website

Once you have the `.build.yml` created and in your git repository, every time you push to Sourcehut it will deploy your website.

I hope you enjoyed!
