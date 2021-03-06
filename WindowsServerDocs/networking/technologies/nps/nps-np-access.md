---
title: 访问权限
description: 本主题概述了 Windows Server 2016 中网络策略服务器的网络策略访问权限。
manager: brianlic
ms.topic: article
ms.assetid: d6d1ca5e-bde0-4509-9e14-dc3fa9ff447e
ms.author: lizross
author: eross-msft
ms.openlocfilehash: 7def3b69ca638525f53a8286c5cfdf235b2531e3
ms.sourcegitcommit: dfa48f77b751dbc34409aced628eb2f17c912f08
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2020
ms.locfileid: "87952072"
---
# <a name="access-permission"></a>访问权限

>适用于：Windows Server（半年频道）、Windows Server 2016

访问权限在网络策略服务器中的每个网络策略的 "**概述**" 选项卡上配置 (NPS) 。

此设置允许您将策略配置为允许或拒绝用户访问，前提是连接请求与网络策略的条件和约束匹配。

访问权限设置具有以下作用：

- **授予访问权限**。 如果连接请求匹配策略中配置的条件和约束，则授予访问权限。
- **拒绝访问**。 如果连接请求匹配策略中配置的条件和约束，则拒绝访问。

还可以根据每个用户帐户的拨入属性配置来授予或拒绝访问权限。

>[!NOTE]
>用户帐户及其属性（如拨入属性）是在 Active Directory 用户和计算机或本地用户和组 Microsoft 管理控制台 \( mmc 管理单元中配置的 \) ，具体取决于是否 &reg; 安装了 Active Directory 域服务 (AD DS) 。

用户帐户设置**网络访问权限**（在用户帐户的拨入属性上配置）替代网络策略访问权限设置。 如果将用户帐户上的网络访问权限设置为 "**通过 NPS 网络策略控制访问**" 选项，则 "网络策略访问权限" 设置将确定是允许还是拒绝用户访问。

>[!NOTE]
>在 Windows Server 2016 中，AD DS 用户帐户拨入属性中的 "**网络访问权限**" 的默认值为 "**通过 NPS 网络策略控制访问**"。

当 NPS 针对配置的网络策略评估连接请求时，它将执行以下操作：

- 如果不匹配第一个策略的条件，则 NPS 将评估下一个策略，并继续执行此过程，直至找到一个匹配，或已为一个匹配评估所有策略。
- 如果匹配策略的条件和约束，则 NPS 授予或拒绝访问权限，具体取决于策略中的 "访问权限" 设置的值。
- 如果策略的条件匹配，而策略中的约束不匹配，则 NPS 拒绝连接请求。
- 如果所有策略的条件都不匹配，则 NPS 拒绝连接请求。

## <a name="ignore-user-account-dial-in-properties"></a>忽略用户帐户的拨入属性

通过选中或清除网络策略的 "**概述**" 选项卡上的 "**忽略用户帐户拨入属性**" 复选框，可以将 NPS 网络策略配置为忽略用户帐户的拨入属性。

通常，当 NPS 执行连接请求的授权时，它会检查用户帐户的拨入属性，其中网络访问权限设置值会影响是否授权用户连接到网络。 授权期间，如果将 NPS 配置为忽略用户帐户的拨入属性，则网络策略设置将确定是否授予用户访问网络的权限。

用户帐户的拨入属性包含以下内容：

- 网络访问权限
- 呼叫方 ID
- 回拨选项
- 静态 IP 地址
- 静态路由

若要支持 NPS 为之提供身份验证和授权的多种类型的连接，可能需要禁止对用户帐户拨入属性的处理。 这样做可以支持不需要特定拨入属性的方案。

例如，呼叫方 ID、回拨、静态 IP 地址和静态路由属性是为拨入到网络访问服务器 NAS 的客户端设计的，而不是针对 \( \) 连接到无线访问点的客户端。 从 NPS 接收 RADIUS 消息中的这些设置的无线访问点可能无法处理它们，这可能会导致无线客户端断开连接。

当 NPS 为通过无线访问点拨入和访问你的组织网络的用户提供身份验证和授权时，你必须通过设置拨入属性或无线连接来配置拨入属性，以支持拨入连接， \( \) \( 而不是设置拨入属性 \) 。

在某些情况下（如拨入），可以使用 NPS 为用户帐户启用拨入属性处理 \( \) ，并在其他方案 \( （如 802.1 x 无线和身份验证交换机）中禁用拨入属性处理 \) 。

你还可以使用 "**忽略用户帐户拨入属性**" 通过网络策略上的组和访问权限设置来管理网络访问控制。 选中 "**忽略用户帐户拨入属性**" 复选框时，将忽略用户帐户上的网络访问权限。

此配置的唯一缺点是您不能使用用户帐户的其他拨入属性，如呼叫方 ID、回拨、静态 IP 地址和静态路由。

有关 NPS 的详细信息，请参阅[网络策略服务器 (nps) ](nps-top.md)。
