---
title: Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd18381a8d889a1cebad04234e56bf11def9197e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563896"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する
======================================================================

通常、Microsoft Teams で使用するために Exchange Online 機能を構成する必要はありません。 ただし、Exchange ハイブリッドシナリオの場合、グループメンバーシップが Exchange Server (オンプレミス) と Exchange Online の間で同期されるようにするために、以下の手順を実行する必要があります。 これには、Azure AD Connect のグループ書き戻し機能と、さまざまな初期化スクリプトが含まれます。[オンプレミスの Exchange ハイブリッドを使用して Office 365 グループを構成](https://go.microsoft.com/fwlink/?linkid=854389)します。
