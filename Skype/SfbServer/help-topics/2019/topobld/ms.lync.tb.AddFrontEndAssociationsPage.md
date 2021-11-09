---
title: フロント エンドの関連付けの追加
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
ROBOTS: NOINDEX, NOFOLLOW
description: サーバーの役割をフロントエンド プールに関連付け、他のサーバーの展開を必要とする特定の機能のサポートを有効にできます。 後でサーバーの役割をフロントエンド プールに関連付けすることもできます。 フロントエンド プールに関連付けられるサーバーの役割は次のとおりです。
ms.openlocfilehash: a4a7806945a29b43a2acf9184c2a8f04e1af77eb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864124"
---
# <a name="add-front-end-associations"></a>フロント エンドの関連付けの追加

サーバーの役割をフロントエンド プールに関連付け、他のサーバーの展開を必要とする特定の機能のサポートを有効にできます。 後でサーバーの役割をフロントエンド プールに関連付けすることもできます。 フロントエンド プールに関連付けられるサーバーの役割は次のとおりです。

- A/V エッジ サーバー。 A/V エッジ サーバーの実装の詳細については、「計画」のドキュメントの「 [会議](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) の計画」を参照してください。

> [!IMPORTANT]
> これらの機能のサポートを有効にした場合、発行するトポロジ設計には、選択した各機能の実装に必要なサーバー コンポーネントが含まれます。 トポロジの発行がエラーなしで成功するには、物理コンピューターがドメインに参加している必要があります。 たとえば、今すぐアーカイブのサポートを有効にする場合は、組織のアーカイブ通信を開始する前に、アーカイブ サーバーを展開し、適切なアーカイブ オプションを構成する必要があります。