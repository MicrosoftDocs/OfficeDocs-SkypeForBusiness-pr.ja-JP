---
title: 従来版のマージ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Web 会議外部 FQDN を使用すると、外部ユーザーはオンプレミス会議に参加できます。 従来のエッジ サーバーの Web 会議外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: 586a9022602de97526b262b612d3e87e0a174ccc12a728b57d0664d9d05317b3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342342"
---
# <a name="legacy-merge"></a>従来版のマージ

**Web 会議外部 FQDN を使用すると**、外部ユーザーはオンプレミス会議に参加できます。 従来のエッジ サーバーの Web 会議外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。

外部 **Web 会議外部** ポート値 **443** は、会議クライアント用に構成された既定の伝送制御プロトコル (TCP) セッション開始プロトコル (SIP) ポートです。 既定値が使用されていない場合は、外部 Web 会議の外部ポート **値を更新** します。

フェデレーションに **このエッジ サーバーを使用** する場合は、[このエッジ プールをフェデレーションとパブリック IM 接続に使用する] チェック ボックスをオンにします。 複数のエッジ サーバーを展開している場合、そのうちの 1 つだけがフェデレーションで有効になります。 このボックスをオンにしない場合、後でフェデレーションを有効にした場合は、トポロジ ビルダーのマージ ウィザードを再度実行し、トポロジを公開する必要があります。 詳細については、「[フェーズ 4:Merge Topologies (トポロジの結合)](/previous-versions/office/lync-server-2013/phase-4-merge-topologies)」を参照してください。