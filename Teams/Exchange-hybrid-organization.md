---
title: Exchange ハイブリッド組織を構成する
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f1a59c01fa112294d771dc6f8d08f32a3c7a4f19
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136517"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する
======================================================================

通常、Microsoft Teams で使用するために Exchange Online 機能を構成する必要はありません。 ただし、Exchange ハイブリッドシナリオの場合、グループメンバーシップが Exchange Server (オンプレミス) と Exchange Online の間で同期されるようにするために、以下の手順を実行する必要があります。 これには、Azure AD Connect のグループ書き戻し機能と、さまざまな初期化スクリプトが含まれます。[オンプレミスの Exchange ハイブリッドを使用して Office 365 グループを構成](https://go.microsoft.com/fwlink/?linkid=854389)します。
