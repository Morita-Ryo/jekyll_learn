{% assign ext = include.page.url | remove: include.page.id %}{% assign path = include.page.url | remove: ext | remove: include.page.slug %}{{ path }}
