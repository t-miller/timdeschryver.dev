---
title: Show stacktrace when dotnet core API doesn't start
slug: show-stacktrace-when-dotnet-core-api-doesnt-start
description: A snippet on how to get a stacktrace when a .NET Api fails to start.
date: 2020-07-22
tags: .NET, debugging
---

## Show stacktrace when dotnet core API doesn't start

### Use case

When you have an API that doesn't start and doesn't show an error log.

### Solution

Update the `web.config` and set the `ASPNETCORE_DETAILEDERRORS` environment variable to `true`.

```html
<system.webServer>
	<httpErrors errorMode="Detailed" />
	<aspNetCore processPath="dotnet">
		<environmentVariables>
			<environmentVariable name="ASPNETCORE_DETAILEDERRORS" value="true" />
		</environmentVariables>
	</aspNetCore>
</system.webServer>
```
