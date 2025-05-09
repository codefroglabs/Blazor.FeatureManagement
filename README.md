# Blazor.FeatureManagement

Provides a component for integrating with [Microsoft.FeatureManagement](https://learn.microsoft.com/en-us/azure/azure-app-configuration/feature-management-dotnet-reference) in Blazor applications.

# Getting Started
## Installation
Install the NuGet package:

```bash
dotnet add package Blazor.FeatureManagement
```

## Configuration
[Enable Feature Management](https://learn.microsoft.com/en-us/azure/azure-app-configuration/feature-management-dotnet-reference#service-registration) in your `Program.cs`.

## Component usage

By default, if the feature flag is disabled, the content inside the `FeatureFlag` component will not be rendered. You can optionally provide fallback text or a render fragment to display when the feature is disabled.

### Basic usage
```razor
@page "/example"
@using Blazor.FeatureManagement

<h1>Feature Management Example</h1>
<FeatureFlag Name="MyFeature">
    <h2>My Feature is enabled!</h2>
</FeatureFlag>
```

### Disable content with fallback text
```razor
@page "/example"
@using Blazor.FeatureManagement
<h1>Feature Management Example</h1>
<FeatureFlag Name="MyFeature" FallbackText="My Feature is disabled">
    <h2>My Feature is enabled!</h2>
</FeatureFlag>
```

### Disable content with fallback render fragment
```razor
@page "/example"
@using Blazor.FeatureManagement
<h1>Feature Management Example</h1>
<FeatureFlag Name="MyFeature">
    <ChildContent>
        <h2>My Feature is enabled!</h2>
    </ChildContent>
    <FallbackContent>
        <h2>My Feature is disabled</h2>
    </FallbackContent>
</FeatureFlag>