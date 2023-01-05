# GitHub doesn't delete organization repos

To my wondrous surprise, GitHub keeps all of an organizations repos around even if the organization is disbanded (yes, even the private ones). To get at them you need to use the API, however, or have all the names memorized.

Here's my `~/.config/gh/config.yaml` file with the `repos` alias in it. I was able to pull up all my old `skilstak` stuff with it.

```yaml
git_protocol: ssh
editor: vim
prompt: enabled
pager: less
aliases:
    co: pr checkout
    del: |
        !gh api -X DELETE "repos/$GITUSER/$1"
    priv: |
        !gh api -X PATCH "repos/$GITUSER/$1" -f private="true" | jq .private
    pub: |
        !gh api -X PATCH "repos/$GITUSER/$1" -f private="false" | jq .private
    status: |
        !gh api graphql -f emoji="${1%% *}" -f msg="${1#* }" -f query='mutation ($msg: String!, $emoji: String) {changeUserStatus(input:{message:$msg,emoji:$emoji}) {status { message, emoji }}}'
    repos: |
        !gh api --paginate graphql -f owner="$1" -f query='
          query($owner: String!, $per_page: Int = 100, $endCursor: String) {
            repositoryOwner(login: $owner) {
              repositories(first: $per_page, after: $endCursor, ownerAffiliations: OWNER) {
                  nodes { nameWithOwner }
                  pageInfo { hasNextPage endCursor }
                }
              }
            }
          ' | jq -r '.data.repositoryOwner.repositories.nodes[].nameWithOwner' | sort
    orgs: |
        !gh api --paginate graphql  -f query='
        query {
          viewer {
            id
            name
            organizations(first: 100) {
              nodes {
                id
                name
              }
            }
          }
        } ' | jq -r '.data.viewer.organizations[][] | .id + " " + .name'
    defmain: |
        !gh api -X PATCH "repos/$1" -f default_branch="main" | jq .default_branch
```
