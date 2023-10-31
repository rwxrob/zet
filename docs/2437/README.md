# Bitnami produces regularly inferior products

I've been in the middle of migrating from Bitnami `SealedSecrets` to `VaultStaticSecrets` and although I realize there are different design goals I could not help but realize how much more elegant the Vault controller approach is to the horrendeous problem SealedSecrets provide because you have to secure the certs that are used to create those and if they are managed poorly can provide a very brittle point of failure in the whole architecture. Vault has nothing of the sort.

Then there's Helm, perhaps the biggest piece of steaming cloud-native dog-shit software in all of the industry. The code base is absolutely ludicrous to read. So long as you don't ever have to use it or maintain it, you'll get a good laugh out of it.

It's rather unremarkable that VMware bought Bitnami in 201.9 (Probably because VMware was dupped into thinking Helm is actually good.)
