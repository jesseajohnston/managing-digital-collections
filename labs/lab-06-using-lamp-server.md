---
title: "Lab 6: Setting Up and Using Your LAMP Server"
---

This lab asks you to confirm you can log on to your LAMP server and interact with the server to serve content to the Web. The process is a bit different than the process for the serverless sites, although the outcome (a published website that can host your digital content) will be similar.

Your site will run on UMSI servers that are preconfigured with a LAMP stack. We are using some variation of a "Platform as a Service" model (PaaS), where the Platform (the server running Linux with Apache, MySQL, and PHP) is provided by UMSI. In other words, UMSI is your cloud provider. The school is providing the compute power, storage, database management, server connections, and domain registration to publish to the Web. You, meanwhile, are setting up the content on the server (ultimately, this will be Omeka S) and making configurations to modify the backend and frontend of the set up to publish content to the Web.

Ultimately, the server, database, and program scripts that generate the HTML pages; Omeka S will provide all of the instructions to these systems to create the administration interface (backend) and the presentation for the public (frontend). We are able to interact with these systems using a shell interface (using basically the same commands and interactions that we used locally using the SSH or Secure Shell which provides security of data packets across the internet layer) and using the browser (we will be using an interface called cPanel, which opens up in the browser and provides access to the server).

For this first lab with your servers, create an `index.html` file in the `public_html` directory. This can be a plain text file with just a few words or a phrase in it (with or without any actual HTML markup). Once the content is visible, then the lab is done! Provide the URL as your response to this lab.
