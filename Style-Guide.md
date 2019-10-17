# API compatibility

Currently, aws-okta is v0, so technically we can change the API however we want. However, this makes internal development from multiple sources difficult. It means the sequence of merging PRs and the conflict resolution thereof is more work.

So in general, we'd prefer if the API expanded rather than changed.

For example, say you'd like to add a parameter `region` to constructor function `NewClient()`. Instead of modifying the signature of `NewClient()`, add a new function `NewClientWithRegion(region string)` and have `NewClient` call `NewClientWithRegion` with a default region.

Eventually this leads to API sprawl, so instead of inventing `NewClientWithRegionAndHTTPClient` or something, it's probably the time to introduce something like `NewClientWithOptions(opts ...ClientOpt)`.