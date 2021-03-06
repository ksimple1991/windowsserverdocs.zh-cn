---
title: delete disk
description: 删除磁盘命令的参考文章，它从磁盘列表中删除丢失的动态磁盘。
ms.topic: reference
ms.assetid: 44079900-e4ed-49d0-81e4-d652c38cd636
ms.author: lizross
author: eross-msft
manager: mtillman
ms.date: 10/16/2017
ms.openlocfilehash: f26bd239c1248630da4ce684547961a239f96b8e
ms.sourcegitcommit: db2d46842c68813d043738d6523f13d8454fc972
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "89628864"
---
# <a name="delete-disk"></a>delete disk

从磁盘列表中删除丢失的动态磁盘。

> [!NOTE]
> 有关如何使用此命令的详细说明，请参阅 [删除丢失的动态磁盘](/previous-versions/windows/it-pro/windows-server-2008-r2-and-2008/cc753029(v=ws.11))。

## <a name="syntax"></a>语法

```
delete disk [noerr] [override]
```

### <a name="parameters"></a>参数

| 参数 | 说明 |
| --------- | ----------- |
| noerr | 仅用于脚本。 出现错误时，DiskPart 继续处理命令，就像未发生错误一样。 如果没有此参数，则错误会导致 DiskPart 退出并出现错误代码。 |
| override | 允许 DiskPart 删除磁盘上的所有简单卷。 如果磁盘上包含半个镜像卷，则磁盘上的这半个镜像将被删除。 如果磁盘是 RAID-5 卷的一个成员，则 delete disk override 命令无效。 |

## <a name="examples"></a>示例

若要从磁盘列表中删除丢失的动态磁盘，请键入：

```
delete disk
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)

- [删除命令](delete.md)
