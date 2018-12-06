---
title: メッセージを削除する
TOCTitle: メッセージを削除する
ms:assetid: 90fcb30d-4987-4e9c-afbc-4482644ce0e4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205081(v=OCS.15)
ms:contentKeyID: 48272846
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# メッセージを削除する

 

_**トピックの最終更新日:** 2012-04-04_

メッセージを削除するには

    Remove-CsPersistentChatMessage -Identity <string> [-UserUri <string>] [-StartDate <DateTime>] [-EndDate <DateTime>] [-Filter <string>] [-MatchClause <AndOr> {And | Or | Exact}] [-CaseSensitive <bool>] [-ReplaceMessage <string>] [-WhatIf] [-Confirm] [<CommonParameters>]

