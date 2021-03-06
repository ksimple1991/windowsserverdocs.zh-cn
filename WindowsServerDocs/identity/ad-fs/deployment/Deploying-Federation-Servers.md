---
ms.assetid: c4d83dd3-2846-4658-8b9c-93901ee69766
title: 部署联合服务器
author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.author: billmath
ms.openlocfilehash: e648f77593f90e976389601d8db5504f6693ce0d
ms.sourcegitcommit: dfa48f77b751dbc34409aced628eb2f17c912f08
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2020
ms.locfileid: "87962841"
---
# <a name="deploying-federation-servers"></a>部署联合服务器

若要在 Active Directory 联合身份验证服务 AD FS 中部署联合服务器 \( \) ，请完成清单中的每个任务[：设置联合服务器](Checklist--Setting-Up-a-Federation-Server.md)。

> [!NOTE]
> 使用此清单时，建议您先阅读[Windows server 2012 的 "AD FS 设计指南](../design/ad-fs-design-guide-in-windows-server-2012.md)" 中的联合服务器规划的引用，然后再开始配置服务器的过程。 按照此方法检查清单，可以更好地了解联合服务器的设计和部署过程。

## <a name="about-federation-servers"></a>关于联合服务器
联合服务器是运行 Windows Server 2008 的计算机，其中安装的 AD FS 软件已配置为充当联合服务器角色。 联合服务器对来自其他组织中用户帐户的请求进行身份验证或路由，以及从 Internet 上的任何位置访问的客户端计算机。

在计算机上安装 AD FS 软件并使用 AD FS 联合服务器配置向导为联合服务器角色配置该软件的操作使该计算机成为联合服务器。 它还使 "AD FS 管理" 管理单元在 \- 该计算机的 "**启动 \\ 管理工具 \\ ** " 菜单中可用，以便你可以指定以下内容：

-   合作伙伴组织和应用程序将在其中发送令牌请求和响应的 AD FS 主机名

-   合作伙伴组织和应用程序将用于标识组织的唯一名称或位置的 AD FS 标识符

-   \-服务器场中的所有联合服务器将用于颁发和签名令牌的令牌签名证书

-   自定义的 ASP.NET 网页的位置，用于客户端登录、注销和将提高客户端体验的帐户伙伴发现

    > [!NOTE]
    > 大多数核心用户界面 \( UI \) 设置都包含在每个联合服务器上的 web.config 文件中。 web.config 文件中未指定 AD FS 主机名和 AD FS 标识符值。

联合服务器托管声明颁发引擎，该引擎根据凭据 \( （例如，提供给它的用户名和密码）颁发令牌 \) 。 安全令牌是一个表示一个或多个声明的经过加密签名的数据单元。 声明是服务器生成的一种语句， \( 例如，名称、标识、密钥、组、权限或 \) 有关客户端的功能。 在联合服务器上 \( 通过用户登录过程验证凭据后 \) ，将通过检查存储在指定属性存储中的用户属性来收集用户的声明。

在联合 Web 单一 \- 登录 \- \( SSO \) 设计 \( 中，AD FS 涉及两个或多个组织的设计 \) ，可以通过特定信赖方的声明规则修改声明。 声明内置于发送到资源伙伴组织中的联合服务器的令牌中。 资源伙伴中的联合服务器接收声明作为传入声明后，它将执行声明发出引擎，以运行一组声明规则来筛选、传递或转换这些声明。 然后将声明内置于发送到资源伙伴中的 Web 服务器的新令牌中。

在 Web SSO 中设计 \( 一个只涉及一个组织的 AD FS 设计时 \) ，可以使用单个联合服务器，以便员工可以登录一次，并且仍可访问多个应用程序。

