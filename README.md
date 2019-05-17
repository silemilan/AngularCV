<p align="center">
  <img src="https://github.com/StegSchreck/AngularCV/blob/master/src/assets/img/AngularCV.png" width="300px">
</p>

# AngularCV

This project serves the purpose of having a simple, self-hosted online-CV outside of LinkedIn, Xing, etc.

For a live demo, you can visit [cv.schreck.berlin](http://cv.schreck.berlin), for which this project was created initially.


## Third Party Stuff

It uses [Angular](https://angular.io/) and the [Material Design components for Angular](https://material.angular.io/).
Furthermore, the following third-party sources are included:
* [Roboto](https://fonts.google.com/specimen/Roboto)
* [Roboto Slab](https://fonts.google.com/specimen/Roboto+Slab)
* [IcoMoon Free](https://icomoon.io/#preview-free)
* [jsPDF](https://github.com/MrRio/jsPDF)

The images in the `/src/assets/img/item-thumbnails` directory in this repository are property of their respective right owners and do not fall under the license of this repository. They're included for show-case purposes.


## Configuration

The CV items for the experience, education, projects and volunteering sections are configured in a JSON format in `/src/app/cv-item/cv-item.data.ts`.
Please notice the division of the education section, which is applied here. This enables you to re-arrange the the sections to your likings.

In the end, this is just an example of how it can be done. Feel free to take it as a template and adjust everything to your needs.

### Set Your Own Data

Here is what you will have to change in order to adapt this project for yourself.

* `src/app/cv-item/cv-items.data.ts` contains all the configurable content data for the page
  * You can use the current version as a template, but you will need to replace the data with your own
  * There are different use cases configured, so you can see different sets of data, which will be displayed differently in the rendered page
  * Some fields are required, for others there are checks in the frontend. Please try it yourself
  * I recommend sorting the items by descending end-date, so the newest item will be shown on top
* Replace `src/assets/img/avatar.jpg` with your profile picture (avatar)
* Replace `src/assets/img/cover.jpg` with an image for your overview page, imagine it as a kind of book cover
* Please delete all images in `src/assets/img/item-thumbnails` and add the ones you need (depending on what you configure in `src/app/cv-item/cv-items.data.ts`)
* Please delete all files in `src/assets/attachments` and add the ones you need (depending on what you configure in `src/app/cv-item/cv-items.data.ts`)
* Replace `src/favicon.ico`, it contains the icon your browser displays in the task bar

In order to comply with the license of this project and the third-party elements in it, please leave the "About" section unchanged as well as the link to it in the footer.

### Feature Toggles

AngularCV offers some feature toggles (a.k.a. feature switches) to adjust the experience of the website. However, some features are part of the basic functionality and should not be deactivated and thus do not have a feature toggle, e.g. the work experience tab.
The feature toggles are defined in `src/app/feature-toggle/feature-toggles.data.ts`. Currently, these feature toggles are implemented:
* `downloadable_pdf`: whether to offer a PDF version of the data (download button will be placed in the header and on the contact page)
* `tab_publications`: whether to shot the "publications" tab
* `tab_projects`: whether to shot the "projects" tab
* `tab_volunteering`: whether to shot the "volunteering" tab
* `contact_show_about_section`: whether to show the "about this website" section on the contact page
* `contact_email_link`: whether to link the email address on the contact page with `mailto:`
* `contact_email_remove_at_sign`: whether to replace the `@` sign when displaying the email address on the contact page (in order to make it harder to scrape for a crawler)
* `default_language`: which language to use for the navigation menu entries, page titles, etc.
* `localization`: whether to offer the visitor of the website to switch the localization language

### Localization

By switching the `default_language` feature toggle (see above), you can define which language to choose for navigation menu entries, page titles, etc. You can also let the user switch the language by activating the `localization` feature toggle. You will still need to adapt your data in `src/app/cv-item/cv-items.data.ts` to adapt the same language.


## Angular Basics

See the [Angular basic guide](ANGULAR.md) for the basics. For more information, visit the [Angular](https://angular.io/) website.


## Deployment to Production

<p align="center">
  <img src="https://github.com/StegSchreck/AngularCV/blob/master/src/assets/img/AngularCV_Deployment.png" width="450px">
</p>

After you cloned/forked this project and adjusted it to your needs (and configuring with your data), you might want to deploy it in order to make it available to anyone.

See my [AWS deployment guide](DEPLOYMENT_ON_AWS.md) for a possible way how to achieve this with [Amazon Web Services (AWS)](https://aws.amazon.com/).

Alternatively, you can use [Uberspace](https://uberspace.de/), see the corresponding [Uberspace deployment guide](DEPLOYMENT_ON_UBERSPACE.md).

As another option, you can use [Github Pages](https://pages.github.com/), see the corresponding [Github Pages 
deployment guide](DEPLOYMENT_ON_GITHUB_PAGES.md).
