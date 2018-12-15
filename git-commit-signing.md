# Steps
- Install gnupg
    `brew install gnupg`

- Generate your key
    `gpg --list-secret-keys --keyid-format LONG`
        In the prompts:
            1) RSA and RSA
            4096 keysize
            Key doesn't expire

- Set up git to sign with your key
    `git config --global gpg.program gpg`
    
    `git config --global commit.gpgsign true`

    `gpg --list-secret-keys --keyid-format LONG`
        Find your key in the list. The first line should look like
            `sec   rsa4096/806C61EA0242934B 2018-12-15 [SC]`
        Your {GPG_KEY_ID} is `806C61EA0242934B` in this example

    `git config --global user.signingkey {GPG_KEY_ID}`

- Export your key
    `gpg --armor --export {GPG_KEY_ID} | pbcopy`

    Paste key value into GitHub, etc.



# Links
https://help.github.com/articles/generating-a-new-gpg-key/