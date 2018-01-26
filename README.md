# Entrez AWS

When deploying a web app, Bella, to AWS Lambda, I ran into an issue that the Biopython module "Entrez" creates a temporary directory for processing files. This works on a local machine. But when the app is deployed to AWS Lambda, it doesn't work. Because Lambda doesn't allow write access -- except in one folder, tmp, which only exists while the Lambda function is running.

This project forks the Entrez module and modifies it so it will create its temporary files in the appropriate directory on Lambda.