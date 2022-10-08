---
title: Exchange ハイブリッド組織を構成する
author: JoanneHendrickson
ms.author: jhendr
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
description: グループ メンバーシップが同期されるように、Microsoft Teams で使用する Exchange ハイブリッド組織を構成する方法について説明します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cb2471a2680218a69daa74d20b27c4b7642fa1d7
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480677"
---
# <a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Microsoft Teams で使用する Exchange ハイブリッド展開の組織を構成する

一般に、Microsoft Teams で使用するためにExchange Online機能を構成する必要はありません。 ただし、Exchange ハイブリッドシナリオでは、グループ メンバーシップをExchange Server (オンプレミス) とExchange Onlineの間で確実に同期するために必要な手順があります。 これには、Azure AD Connect でのグループ ライトバック機能の有効化と、さまざまな初期化スクリプト ([オンプレミスの Exchange ハイブリッドを使用したMicrosoft 365 グループの構成](/exchange/hybrid-deployment/set-up-microsoft-365-groups)) が含まれます。