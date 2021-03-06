---
title: bitsadmin complete
description: Bitsadmin complete 命令的参考文章，用于完成作业。
ms.topic: reference
ms.assetid: a5e86677-8f7b-43b3-929e-97706c57e7f1
ms.author: lizross
author: eross-msft
manager: mtillman
ms.date: 10/16/2017
ms.openlocfilehash: 88e8ac3920adb80dcc453317fbffe5fd661811fb
ms.sourcegitcommit: db2d46842c68813d043738d6523f13d8454fc972
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "89632387"
---
# <a name="bitsadmin-complete"></a>bitsadmin complete

完成作业。 作业转到已转移的状态后，请使用此开关。 否则，只会提供已成功传输的文件。

## <a name="syntax"></a>语法

```
bitsadmin /complete <job>
```

### <a name="parameters"></a>参数

| 参数 | 说明 |
| --------- | ----------- |
| 作业 (job) | 作业的显示名称或 GUID。 |

## <a name="example"></a>示例

若要完成 *myDownloadJob* 作业，请在达到 `TRANSFERRED` 以下状态后：

```
bitsadmin /complete myDownloadJob
```

如果有多个作业使用 *myDownloadJob* 作为其名称，则必须使用作业的 GUID 来唯一地标识该作业才能完成。

## <a name="additional-references"></a>其他参考

- [命令行语法项](command-line-syntax-key.md)

- [bitsadmin 命令](bitsadmin.md)
