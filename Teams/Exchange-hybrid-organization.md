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
description: グループ メンバーシップを確実に同期するために、Microsoft Teams で使用する Exchange ハイブリッド組織を構成する方法について説明します。
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

一般に、Microsoft Teams で使用するために Exchange Online の機能を構成する必要は一切ない必要があります。 ただし、Exchange ハイブリッド のシナリオでは、グループ メンバーシップがオンプレミス (オンプレミス) と Exchange Online の間で同期Exchange Server手順が必要です。 これには、Azure AD Connect でのグループ ライトバック機能とさまざまな初期化スクリプトの有効化が含まれます。オンプレミスの Exchange ハイブリッド を使用して [Microsoft 365 グループを構成します](/exchange/hybrid-deployment/set-up-microsoft-365-groups)。