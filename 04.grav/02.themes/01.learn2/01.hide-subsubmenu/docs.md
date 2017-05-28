---
title: 'Hide Sub-Submenüs'
published: true
date: '28-05-2017 10:55'
publish_date: '28-05-2017 10:55'
taxonomy:
    category:
        - docs
    tag:
        - grav
        - templates
        - themes
        - learn2
    framework:
        - grav
menu: 'Hide SubSubMenüs'
slug: hide-sub-sub
---

[Refferenz](https://github.com/getgrav/grav-theme-learn2/issues/15)  

Dieses CSS versteckt alle Sub Menüs von Submenüs, so lange sie nicht aktiv sind
```css
/* Hides the sub-menu item if parent not active */
.dd-item .dd-item ul li {
    display: none;
}

.dd-item .dd-item.active ul li,
.dd-item.parent > ul > li {
    display: block;
}

/* Hides the sub-sub-menu menu-item if parent not active */
.dd-item.parent > ul > li.dd-item.active > ul > li > ul > li {
    display: none;
}

.dd-item.parent > ul > li.dd-item.active > ul > li {
    display: block;
}
```