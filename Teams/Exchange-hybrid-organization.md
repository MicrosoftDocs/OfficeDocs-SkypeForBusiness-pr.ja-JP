---
title: ハイブリッド組織Exchange構成する
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: グループ メンバーシップが確実に同期Exchangeハイブリッド組織で使用するMicrosoft Teams構成する方法について説明します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3ef36b7bc50d21131dd10294566549bb8b642600
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632651"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する
======================================================================

一般に、アプリケーションで使用するExchange Online機能を構成する必要Microsoft Teams。 ただし、Exchange ハイブリッド シナリオでは、グループ メンバーシップが (オンプレミス) とグループの間で同期Exchange Server手順が必要Exchange Online。 これには、Azure AD Connect でのグループ ライトバック機能とさまざまな初期化スクリプトの有効化が含まれます。オンプレミスの Microsoft 365 グループをハイブリッド で構成Exchange[します](/exchange/hybrid-deployment/set-up-microsoft-365-groups)。