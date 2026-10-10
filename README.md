# Beveled connector for Claude

Create product mockups, App Store screenshot sets and showreel videos through Beveled's hosted MCP connector. This repository contains only integration metadata and the product-mockups skill. Beveled's product source is private.

Install in Claude Code:

```
/plugin marketplace add iambilalazhar/beveled-mcp
/plugin install beveled@beveled
```

The connector uses https://mcp.beveled.app/mcp over Streamable HTTP without authentication. No npm installation or API key is needed. The five tools are list_mockup_options, create_mockup, capture_page_mockup, create_app_store_set and create_showreel.

The hosted connector processes supplied images, videos and public webpage URLs on Cloudflare, and returns a preview and an embedded finished file. Local file paths and localhost URLs require the local package. Video renders can take several minutes; hosts with fixed one-minute timeouts may stop waiting before rendering completes. Use non-sensitive demo content.

[Setup and troubleshooting](https://beveled.app/mcp.html) · [Privacy](https://beveled.app/privacy.html) · [Terms](https://beveled.app/terms)

This integration is publicly readable under a proprietary license; it is not open-source software. See LICENSE.
