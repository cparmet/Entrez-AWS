# Entrez AWS

## Purpose
This project forks the Entrez module from Biopython. It modifies the code slightly so the PubMed API functions will work when deployed to Lambda on Amazon Web Services.

## Motivation
I was deploying a web app, Bella, to AWS Lambda. I ran into errors because the Biopython module I was using, "Entrez," creates a new directory and files while processesing results from the PubMed API. This works swimmingly when it runs on a local machine with standard permissions. But AWS Lambda doesn't allow Python functions to have write access and create new files & directories -- except in one specific Lambda directory, "tmp". This "tmp" directory only exists while the Lambda function is running.

This fork of Entrez makes it create these temporary files only in that safe directory on Lambda.

