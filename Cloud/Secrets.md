Secrets are strings and include things such as:
- database passwords
- private encryption keys
- personal access tokens
For enhanced security, many people also consider that anything that could help an attacker should be considered a secret: for example, the URL to your production database could be seen as a secret. 

The rationale is that this kind of information is sensitive by nature, the less information available in your code, the better.

## Zero Trust
The concept of Zero Trust is that no one should be blindly trusted and allowed to access company resources.

## Zero Secrets
Web applications shouldn't have secrets stored in their code or in their final binaries.

# Git Repositories
Even if your Git repository is private, putting any secret in your source code is a bad practice:
- Anybody having access to your repository will know your sensitive data
- Anybody having access to your application binary will be able to extract secrets from it
Also, once a secret has been stored into Git, attackers can always find it by looking in the repository's history, where it can be forgotten for a long time.

Even if that seems practical, you should never store any secrets in your source code repository. To avoid this issue, you can use automatic tools that regularly check your repository and will send warnings if they find a password or database URL stored by mistake.

