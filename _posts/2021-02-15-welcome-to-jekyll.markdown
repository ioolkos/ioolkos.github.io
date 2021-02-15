---
layout: post
title:  "Setting up a Github pages blog"
date:   2021-02-15 09:10:55 +0100
categories: jekyll update
---
This is using the `minima` template. It does not look great imho, so I tried switching to another (Github supported) Jekyll template. Not easily possible without adaptations, it seems.

Erlang code looks like this:

```erlang
-spec netsplit_statistics() -> {non_neg_integer(), non_neg_integer()}.
netsplit_statistics() ->
    case catch ets:lookup(?VMQ_CLUSTER_STATUS, ready) of
      [{ready, {_Ready, NetsplitDetectedCount, NetsplitResolvedCount}}] ->
        {NetsplitDetectedCount, NetsplitResolvedCount};
      {'EXIT', {badarg, _}} -> {error, vmq_status_table_down} % we don't have a vmq_status ETS table
    end.    
```

Anyway, this should be about the content, not the looks :)