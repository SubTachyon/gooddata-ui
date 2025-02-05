---
id: framework_overview
title: Architecture Overview
sidebar_label: Architecture Overview
copyright: (C) 2007-2018 GoodData Corporation
---

GoodData.UI follows principles of the layered architecture and draws a clean line between the different UI components and
the backend server that calculates the data to render. The UI components integrate with a backend server through an interface
that we call **Analytical Backend**.

The **Analytical Backend** is designed as a Service Provider Interface (SPI) with clearly described contracts that
you can implement to work even with your own arbitrary backend. For now, the full documentation of the SPI is provided
only at the code level. For more information, see the [`@gooddata/sdk-backend-spi`](https://github.com/gooddata/gooddata-ui-sdk/tree/master/libs/sdk-backend-spi/src) package.

GoodData.UI comes with a full implementation of the Analytical Backend SPI for the [GoodData platform](01_intro__platform_intro.md) (codename `bear`) and a near-full implementation for [GoodData Cloud and GoodData.CN](06_cloudnative__introduction.md) (codename `tiger`).

The Analytical Backend abstraction ultimately allows you to develop applications that can be backend-agnostic. To learn more about guidelines and practices to fully leverage this abstraction, see [Building backend-agnostic applications](30_tips__backend_agnostic_apps.md).

**NOTE:** GoodData.UI uses the `bear` and `tiger` codenames in all developer-facing artifacts and APIs. We find that these can better withstand the test of time.

## Available packages

GoodData.UI consists of several packages, each with its own set of responsibilities and exposed APIs. As a developer, you can pick and choose packages according to requirements of your application. For instance, even if you cannot use our React components, you can still benefit from the convenience layer of the Analytical Backend abstraction, which is agnostic to any frontend technology.

| Package | Contents |
| :--- | :--- |
| @gooddata/api-client-bear | The REST API client for the GoodData platform (formerly known as `gooddata-js`) |
| @gooddata/api-model-bear | The type definitions for the GoodData platform REST API client (formerly known as `typings`) |
| @gooddata/sdk-backend-bear | The analytical backend implementation for the GoodData platform |
| @gooddata/api-client-tiger | The REST API client for GoodData Cloud and GoodData.CN |
| @gooddata/sdk-backend-tiger | The analytical backend implementation for GoodData Cloud and GoodData.CN |
| @gooddata/sdk-model | The APIs and models used to construct inputs to executions and charts |
| @gooddata/sdk-ui | The React infrastructure and headless components such as the Execute component |
| @gooddata/sdk-ui-charts | The React components for all charts |
| @gooddata/sdk-ui-geo | The React components for the Geo Pushpin Chart component |
| @gooddata/sdk-ui-pivot | The React component for the Pivot Table component |
| @gooddata/sdk-ui-filters | The filtering components |
| @gooddata/sdk-ui-ext | The components for embedding insights created in Analytical Designer |
| @gooddata/sdk-ui-all | An umbrella package that depends on all `sdk-ui-` packages and re-exports their public API |
