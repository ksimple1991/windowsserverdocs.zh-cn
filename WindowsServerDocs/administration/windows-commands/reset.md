---
title: reset
description: 重置命令的参考文章，可将 DiskShadow.exe 重置为默认状态。
ms.topic: reference
ms.assetid: afbdab44-199c-4e11-884f-e96804965c21
ms.author: lizross
author: eross-msft
manager: mtillman
ms.date: 10/16/2017
ms.openlocfilehash: 84f4aedee746e642e59a09055c3994160f503afa
ms.sourcegitcommit: db2d46842c68813d043738d6523f13d8454fc972
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "89626884"
---
# <a name="reset"></a>reset

将 DiskShadow.exe 重置为默认状态。 此命令在分隔复合 DiskShadow 操作（如 **创建**、 **导入**、 **备份**或 **还原**）时特别有用。

> [!重要说明在运行此命令后，将丢失命令中的状态信息，如 **add**、 **set**、 **load**或 **writer**。 此命令还会释放 IVssBackupComponent 接口，并丢失非持久卷影副本。

## <a name="syntax"></a>语法

```
reset
```

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)

- [create 命令](create.md)

- [导入命令](import_1.md)

- [backup 命令](begin-backup.md)

- [restore 命令](begin-restore.md)

- [添加命令](add.md)

- [set 命令](set_2.md)

- [load 命令](reg-load.md)

- [编写器命令](writer.md)
