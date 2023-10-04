## Connecting to multiple GitHub accounts via SSH

It's not possible to use a single SSH key to connect to multiple accounts at GitHub.

To solve that:

1. Ensure that a dedicated SSH key is registered to each GitHub account
2. Modify ssh config, for example

    ```
    # default one
    Host github.com
       HostName github.com
       IdentityFile ~/.ssh/id_rsa
       IdentitiesOnly yes
    
    # one for work
    Host github-my-client
       HostName github.com
       IdentityFile ~/.ssh/id_rsa_work
       IdentitiesOnly yes
    ```

3. Update the git remotes to point to the newly defined ssh host, for example:

    ```shell
    $git remote add origin git@github-my-client:MyCompany/MyRepo.git
    ```

Note that email from the git config is used for commits, not for ssh authentication.

More info:

- https://gist.github.com/alejandro-martin/aabe88cf15871121e076f66b65306610


