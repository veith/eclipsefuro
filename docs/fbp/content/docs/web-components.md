---
title: "furo web"
weight: 10
# bookFlatSection: false
bookToc: false
bookHidden: true
# bookCollapseSection: false
# bookComments: true
---

# フロー Furo Web Components

Furo Web Components provides an enterprise ready set of web components which play seamlessly with Furo. 
Based on web standards and future proved. Compliant with any technology of choice. 
With minimal footprint it includes all enterprise standards, i18n, theming and much more.

The furo web components are a wide set of components which covers everything you need to write a web application.
They consume the same types which are defined with furo.

{{< columns >}}
## [Powered by lit](https://lit.dev/)
Many of the world's most forward-looking organizations are building with Lit. We too.
![lit](https://lit.dev/images/logo.svg)

*Most of our components are using lit or elsewhere native web components.*  
<--->

## Programmable HTML
Furo FBP is like programmable HTML, no deep javascript knowledge is needed to write an application.
![viz](/viz.png)
*The flowbased programming paradigm results in less complex and more flexible code.* 
{{< /columns >}}

{{< columns >}}
## [SAP UI5](https://components.furo.pro/?t=furo-ui5), [Google Material](https://components.furo.pro/?t=furo-data-input) or any other design system

A set of input elements which will work with the furo data structure out of the box, are available for a wide set of types.

Our ui5 components i.e. are just extending the excellent [UI5 Web Components](https://sap.github.io/ui5-webcomponents/), the Enterprise-flavored sugar on top of native APIs!.

![UI5 Logo](https://sap.github.io/ui5-webcomponents/assets/images/ui5.png)

*If this is not enough, it is no problem to write your own components, by using the data adapter.*
<--->

## [Data Integration](https://components.furo.pro/?t=furo-data)
The transparent data agents are responsible for the communication with the APIs and the adapters for the UI interaction.
{{< mermaid >}}
    graph TD
    UI[UI elements]-- HTML ---agent[Data Agents]
    agent-- REST ---API
{{< /mermaid >}}
{{< /columns >}}

