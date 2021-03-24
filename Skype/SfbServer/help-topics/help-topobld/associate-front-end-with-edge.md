---
title: フロント エンドとエッジの関連付け
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: 各フロントエンド プールには、エッジ サーバーまたはエッジ プールを 1 つしか関連付けできません。 サイトで外部ユーザーのアクセスを有効にする場合は、リモート ユーザーのサポートを提供できます。 また、特定のパブリック インスタント メッセージング (IM) 接続プロバイダー (Windows Live など) のユーザーのサポート、匿名ユーザーのサポートなど、フェデレーション ユーザーのサポートを有効にできます。
ms.openlocfilehash: dcef84fdf63dc03c35a33650cca7f0f7c5de5900
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103223"
---
# <a name="associate-front-end-with-edge"></a>フロント エンドとエッジの関連付け

各フロントエンド プールには、エッジ サーバーまたはエッジ プールを 1 つしか関連付けできません。 サイトで外部ユーザーのアクセスを有効にする場合は、リモート ユーザーのサポートを提供できます。 また、特定のパブリック インスタント メッセージング (IM) 接続プロバイダー (Windows Live など) のユーザーのサポート、匿名ユーザーのサポートなど、フェデレーション ユーザーのサポートを有効にできます。

使用がエッジ サーバーの容量を超えない場合は、サイト内のすべてのプールと複数の中央サイトのプールで同じエッジ サーバーを使用できます。 拡張を含む監視の詳細については、「計画」のドキュメントの「[Planning for External User Access (外部ユーザー アクセスの計画)](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)」を参照してください。 外部ユーザー アクセスをサポートするトポロジ設計の詳細については、「展開」のドキュメントの「[Define Your Edge Topology (エッジ トポロジの設計)](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)」を参照してください。