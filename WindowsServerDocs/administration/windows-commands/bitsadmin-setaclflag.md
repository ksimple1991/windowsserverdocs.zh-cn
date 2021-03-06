---
title: bitsadmin setaclflag
description: Bitsadmin setaclflag 命令的参考文章，用于设置访问控制列表 (ACL) 传播标志。
ms.topic: reference
ms.assetid: 6e3bcda0-827d-4dfd-8384-d1da018f3e10
ms.author: lizross
author: eross-msft
manager: mtillman
ms.date: 10/16/2017
ms.openlocfilehash: 0cc0dac9027bd76735592620f89118318548dbdb
ms.sourcegitcommit: db2d46842c68813d043738d6523f13d8454fc972
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "89631057"
---
# <a name="bitsadmin-setaclflag"></a>bitsadmin setaclflag

为作业设置访问控制列表 (ACL) 传播标志。 标志指示你希望在要下载的文件中维护所有者和 ACL 信息。 例如，若要维护文件的所有者和组，请将 **flags** 参数设置为 `og` 。

## <a name="syntax"></a>语法

```
bitsadmin /setaclflag <job> <flags>
```

### <a name="parameters"></a>参数

| 参数 | 说明 |
| --------- | ----------- |
| 作业 (job) | 作业的显示名称或 GUID。 |
| flags | 指定一个或多个值，包括：<ul><li>**o** -将所有者信息复制到文件。</li><li>**g** -复制组信息和文件。</li><li>**d** -复制任意访问控制列表 (DACL) 包含文件的信息。</li><li>**s** -复制系统访问控制列表 (SACL) 包含文件的信息。</li></ul> |

## <a name="examples"></a>示例

若要设置名为 *myDownloadJob*的作业的访问控制列表传播标志，使其与下载的文件一起维护所有者和组信息。

```
bitsadmin /setaclflags myDownloadJob og
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)

- [bitsadmin 命令](bitsadmin.md)
