# 了解 OpenShift 4 中的身份验证

> 原文：<https://acloudguru.com/blog/engineering/understanding-authentication-in-openshift-4>

*想了解更多关于 OpenShift 4 身份验证的信息并熟悉用户和组管理吗？在这篇文章中，我们将深入探讨 OpenShift 认证的一些组成部分。*

OpenShift 包含一个内置的 OAuth 服务器，然后为用户分发访问令牌以对 API 进行身份验证。您可以配置一个名为身份提供者的东西来确认您的身份，以允许您的 OAuth 服务器进行访问。通过身份验证后，用户、组和服务帐户可以被授予角色，这些角色具有由 RBAC 控制的特定访问类型。这些只是组成 OpenShift 4 认证过程的一部分。

让我们深入研究构成 OpenShift 身份验证的不同部分。

### **内部 OAuth 服务器**

如上所述，OpenShift 带有内置的 OAuth 服务器，其作用就像俱乐部的保镖:如果你不在名单上，你就进不去。内部 OAuth 服务器位于第一控制平面上。用户获得 OAuth 访问令牌，这样他们就可以对 OpenShift API 进行身份验证。它会检查您选择的身份提供者。

### **身份提供者**

身份提供者类似于内部 OAuth 服务器用来检查允许哪些用户访问的 VIP 列表。当您第一次安装集群时，只有 kubeadmin 用户，有时还有一个开发人员用户。首先，您需要设置您选择的身份提供者。OpenShift 支持九种不同的身份提供者在身份验证时使用。这里有一个列表:

*   **HTPasswd–**该身份提供者根据使用 HTPasswd 命令生成的平面文件来验证用户和密码。

*   **Keystone–**在 OpenStack 上安装 OpenShift 时使用该身份提供者，并使用 OpenStack Keystone 服务器将用户存储在 OpenStack 的内部数据库中以共享身份验证。

*   **LDAP—**该身份提供者根据 LDAP 版本 3 服务器验证用户和密码，并使用简单绑定身份验证。这包括活动目录身份验证。

*   **基本认证—**这个身份提供者是一个通用的后端集成。根据远程身份提供者验证用户凭据。

*   **请求标题—**该身份提供者根据请求标题值识别用户。这些值是像 X-Remote-User 这样的头。该身份提供者通常与身份验证代理结合使用。身份验证代理通常设置身份提供者将使用的请求标头值。

*   **GitHub—**该身份提供者根据 GitHub 或 GitHub Enterprise 的 OAuth 服务器验证用户和密码。

*   **GitLab–**该身份提供者根据 GitLab 或任何其他 git lab 实例验证用户和密码。

*   **Google–**该身份提供者根据 Google 的 OpenID Connect 集成来验证用户和密码。

*   **OpenID Connect–**该身份提供者使用授权代码流根据 OpenID Connect 身份提供者验证用户和密码。

### **一旦登录…**

然后，可以为用户分配对项目或集群范围内的资源具有权限的角色。这是使用 RBAC 完成的。

### **RBAC**

或基于角色的访问控制确定用户是否可以在项目中执行某项操作。有七种默认集群角色可用于绑定用户和组。这些角色可以在集群范围内使用，也可以在项目中本地使用。

以下是默认集群角色的列表:

*   **admin—**能够查看和修改项目中除配额以外的任何资源。

*   **集群管理员–**这是集群的超级用户。他们可以在任何项目中执行任何操作。建议创建一个集群管理员并禁用 kubeadmin 登录。

*   **cluster-status–**分配了此角色的用户可以查看基本的集群状态信息。适用于监控目的。

*   **自我置备者—**该角色允许用户创建自己的项目。

*   **基本用户–**被分配了该角色的用户将能够获得基本的项目和用户信息。

*   **查看–**被分配了该角色的用户可以查看项目中的大多数对象，但不能修改它们。

*   **编辑—**分配了此角色的用户将能够查看和修改除角色和绑定之外的大多数对象。

这些角色可以分配给用户、组和服务帐户，以允许他们执行特定的任务。让我们来看看每一个。

### **用户**

OpenShift 中的*用户*是请求访问 OpenShift API 的实体。被授予访问权限的用户可以被分配角色，以授予对项目或群集中的资源的特定访问权限。

### **组**

一个*组*是用户的集合。管理员通常将需要相同访问权限的用户分组，并授予该组访问资源所需的必要角色。这是将权限分配给资源的一种更有效的方式，因为您只需要将用户添加到一个组中，而不是为每个用户单独分配相同的角色。

### **服务账户**

一个*服务账户*是一个可以允许组件直接访问 API 的账户。它允许您在不使用普通用户的凭证的情况下控制 API 访问，考虑到普通用户的角色和访问的变化频率，这是一种更好的方法。

## 了解有关 OpenShift 4 的更多信息

在我的 [OpenShift 4 认证和用户管理课程](https://acloudguru.com/course/openshift-4-authentication-and-user-management)中，这些只是我将深入探讨的几个主题。如果您想了解更多关于身份验证、用户和组管理以及资源访问控制的信息，请加入我的 OpenShift 4 冒险之旅！