# Do NOT disable host-checking in ssh unnecessarily

I saw this idiocy on StackExchange:

```dockerfile
RUN echo "Host github.com\n\tStrictHostKeyChecking no\n" >> /root/.ssh/config
```

It is obviously better to do this the proper way:

```
          mkdir -p ~/.ssh
          ssh-keyscan github.com >> ~/.ssh/known_hosts
          ssh-agent -a $SSH_AUTH_SOCK > /dev/null
          ssh-add - <<< "${{ secrets.GO_MODULE_PRIVATE_KEY }}"
```

