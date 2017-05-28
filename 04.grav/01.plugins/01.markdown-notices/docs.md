---
title: 'Markdown Notices'
published: true
date: '28-05-2017 01:12'
publish_date: '28-05-2017 01:12'
taxonomy:
    category:
        - docs
    tag:
        - grav
        - plugin
    framework:
        - grav
menu: 'Markdown Notices'
slug: markdown-notices
---

This plugin display's nice Notices. Like the one below.  
Usage is just 1 to 4 exclamation mark's


!!! Use this css for the nice Notices

```
div.notices {
  margin: 2rem 0;
  position: relative; }
  div.notices p {
    padding: 15px;
    display: block;
    font-size: 1.1rem;
    margin-top: 0rem;
    margin-bottom: 0rem;
    color: #666; }
    div.notices p:first-child:before {
      position: absolute;
      top: 2px;
      color: #fff;
      font-family: FontAwesome;
      content: '';
      left: 10px; }
    div.notices p:first-child:after {
      position: absolute;
      top: 2px;
      color: #fff;
      left: 2rem; }
  div.notices.info p {
    border-top: 30px solid #F0B37E;
    background: #FFF2DB; }
    div.notices.info p:first-child:after {
      content: 'Info'; }
  div.notices.warning p {
    border-top: 30px solid rgba(217, 83, 79, 0.8);
    background: #FAE2E2; }
    div.notices.warning p:first-child:after {
      content: 'Warning'; }
  div.notices.note p {
    border-top: 30px solid #6AB0DE;
    background: #E7F2FA; }
    div.notices.note p:first-child:after {
      content: 'Note'; }
  div.notices.tip p {
    border-top: 30px solid rgba(92, 184, 92, 0.8);
    background: #E6F9E6; }
    div.notices.tip p:first-child:after {
      content: 'Tip'; }

```

Add ``` info, warning, tip, note ``` to the config of the plugin