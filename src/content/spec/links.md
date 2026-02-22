---
title: "友情链接"
description: "加友链联系TG哦"
template: "page"
---

<div style="display: flex; flex-wrap: wrap; gap: 1rem; margin-top: 2rem;">
  {
    friendsLinks.map((link) => (
      <div style="border: 1px solid var(--color-border); border-radius: 0.75rem; padding: 1rem; width: calc(50% - 0.5rem); box-sizing: border-box;">
        <a href={link.url} target="_blank" style="display: flex; align-items: center; gap: 0.75rem; text-decoration: none;">
          <img src={link.avatar} alt={link.name} style="width: 48px; height: 48px; border-radius: 50%; object-fit: cover;">
          <div>
            <div style="font-weight: 600;">{link.name}</div>
            <div style="font-size: 0.9rem; color: var(--color-text-light);">{link.description}</div>
          </div>
        </a>
      </div>
    ))
  }
</div>

<script>
import { friendsLinks } from "../../data/friends";
</script>