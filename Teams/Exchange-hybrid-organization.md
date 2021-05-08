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
description: グループ メンバーシップが確実に同期Exchangeハイブリッド組織を構成し、Microsoft Teamsで使用する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90250b3d3f3593990d356843bebea324060d6f8b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094609"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する
======================================================================

一般に、アプリケーションで使用するExchange Online機能を構成する必要Microsoft Teams。 ただし、Exchange ハイブリッド シナリオでは、グループ メンバーシップが (オンプレミス) とグループの間で同期Exchange Server手順が必要Exchange Online。 これには、Azure AD Connect でのグループ ライトバック機能とさまざまな初期化スクリプトの有効化が含まれます。オンプレミスの Microsoft 365 グループをハイブリッド で構成Exchange[します](/exchange/hybrid-deployment/set-up-microsoft-365-groups)。