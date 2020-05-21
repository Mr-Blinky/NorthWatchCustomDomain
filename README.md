# NorthWatch Custom Domain
Setup a Custom Domain on NorthWatch with FREE SSL and Hosting!  You need NorthWatch PRO to change the bank name once logged in, but this will allow you to purchase a domain (or get a free domain) and set it up with NorthWatch.  [Click here](https://evanspy1.github.io/NorthWatchCustomDomain/) for a demo of what your finished site will look like.

[Click here](#step-1) if you don't care about how it works and just want to set it up!

## Background/More Information/How Does This Work?
I am the developer for NorthWatch, and I made this so people can easily integrate NorthWatch on their own domain.  GitHub Pages is super simple Static Site hosting.  The [NorthWatchCustomDomain script](https://github.com/evanspy1/NorthWatchCustomDomain/blob/master/index.html) is super simple, and it all fits on one line.  All it does is create a fullscreen embed of NorthWatch, that you are hosting on your own domain, using GitHub Pages for hosting, and NameCheap, GoDaddy, or similar for the domain.  It is important to note that **this IS NOT the code for NorthWatch.**

NorthWatch is closed source, all this script does is embed NorthWatch on your domain.  This means that your domain will follow the up/downtime, updates, etc. alongside NorthWatch since your domain is just an embed of NorthWatch, you aren't hosting the NorthWatch code.  This is typically good since NorthWatch has [very good uptime](https://status.northwatchbank.com) for a project of its size, and 

I appoolgise if you were looking for a way to self-host NorthWatch, since that is not an option at this time.  Due to the complex nature of NorthWatch (and my inability to help *everyone* learn how to use and manage multiple clustered linux servers and databases), I doubt it will be an option any time in the future.  Also, we have strong evidence that scammers would abuse it.

## Step 1
Fork this repository using the "Fork" button towards the top right-hand corner of the screen.

## Step 2
Go to the settings page of your newly-forked version of this repository (there should be a "Settings" tab towards the top of the screen when you scroll up to the top of your repository), and scroll down to the "GitHub Pages" section.  Select "master branch" for source.

## Step 3
In the "Custom Domain" text box, enter your domain name.

## Step 4
Create these DNS records on your website depending if you want to route NorthWatch to the root of your domain (xxx.com), or a subdomain (yyy.xxx.com).
### Root of Domain (xxx.com)
| Record Type | Name | Value           | TTL (Time to Live) |
|-------------|------|-----------------|--------------------|
| A           | @    | 185.199.108.153 | Auto               |
| A           | @    | 185.199.109.153 | Auto               |
| A           | @    | 185.199.110.153 | Auto               |
| A           | @    | 185.199.111.153 | Auto               |
### Subdomain (yyy.xxx.com)
| Record Type | Name       | Value                | TTL (Time to Live) |
|-------------|------------|----------------------|--------------------|
| CNAME       | [SUBDOMAIN]| [USERNAME].github.io | Auto               |

Be sure to replace [USERNAME] with your GitHub username and replace [SUBDOMAIN] with the subdomain you want (the "yyy" part of the example in the header of this section).
## Step 5
You should be done!  All you need to do is go to the GitHub Pages section of your repository settings and wait for the SSL certificate to issue, and enable it!

## Common Problems/Solutions
**CSRF (Cross Site Request Forgery) Errors**

If you are using a browser like brave, or privacy extentions, make sure you have cross-site cookies ENABLED.  They are typically disabled for good reason (they can cause lots of problems and are typically terrible for being tracked online), but due to the nature of how this system works, they **may** be required.  NorthWatch does not use any malicous cross-site cookies (some tracking scripts that are all on-premise, and a few things for Stripe, our payment processor), so we hope you can trust us enough to turn off tracking.  On Brave, you can click the lion at the top-right-hand corner of your URL bar, and flip the switch, to disable trackers.

**GitHub Pages Not Detecting URL Using CloudFlare or Similar**

GitHub Pages is incompatible with CloudFlare or any similar proxies.  If you are using CloudFlare, click "Edit" on your DNS record(s), and click the orange cloud so it turns grey, they click "Save".  If you are using the root domain (xxx.com), you will need to edit this for all four records.  If you are using a subdomain, (yyy.xxx.com), you will only need to edit it for the one record.

**Other GitHub Pages Issues**

GitHub Pages has Documentation for some more common problems, [click here](https://help.github.com/en/github/working-with-github-pages/troubleshooting-custom-domains-and-github-pages) to read that.
