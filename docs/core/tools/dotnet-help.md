---
title: "dotnet help 命令 - .NET Core CLI"
description: "dotnet help 命令會顯示指定命令更詳細的線上文件。"
author: mairaw
ms.author: mairaw
ms.date: 08/17/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: ca7c88675d54d99fdb3526244daaeffe32f32d45
ms.openlocfilehash: 0d43db0bb0a62bb598f7db50c3b8e37936451550
ms.contentlocale: zh-tw
ms.lasthandoff: 08/18/2017

---
# <a name="dotnet-help-reference"></a>dotnet help reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>name

`dotnet help` - 顯示指定命令更詳細的線上文件。

## <a name="synopsis"></a>概要

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>說明

`dotnet help` 命令會在 docs.microsoft.com 開啟參考頁面，提供指定命令的更詳細資訊。

## <a name="arguments"></a>引數

`COMMAND_NAME`

.NET Core CLI 命令的名稱。 如需有效 CLI 命令的清單，請參閱 [CLI 命令](index.md#cli-commands)。

## <a name="options"></a>選項

`-h|--help`

印出命令的簡短說明。

## <a name="examples"></a>範例

開啟 [dotnet new](dotnet-new.md) 命令的文件頁面：

`dotnet help new`

