---
title: Exchangeハイブリッド組織を構成する
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Microsoft Teamsで使用するExchangeハイブリッド組織を構成して、グループ メンバーシップが確実に同期されるようにする方法について説明します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d1b5cb89f28a334b24aecf982dd3913dfce079ac
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014873"
---
# <a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する

一般に、Microsoft Teamsで使用するためにExchange Online機能を構成する必要はありません。 ただし、Exchange ハイブリッドシナリオでは、グループ メンバーシップがExchange Server (オンプレミス) とExchange Onlineの間で同期されるようにするために必要な手順があります。 これには、Azure AD Connectでのグループ ライトバック機能の有効化と、さまざまな初期化スクリプト ([オンプレミス Exchange ハイブリッドを使用したMicrosoft 365 グループの構成) が含まれます](/exchange/hybrid-deployment/set-up-microsoft-365-groups)。