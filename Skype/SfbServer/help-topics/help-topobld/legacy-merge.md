---
title: 従来版のマージ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: Web 会議外部 FQDN を使用すると、外部ユーザーはオンプレミス会議に参加できます。 従来のエッジ サーバーの Web 会議外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: a6afcf9192a084839895c69f5db454e2f105309c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106703"
---
# <a name="legacy-merge"></a>従来版のマージ

**Web 会議外部 FQDN を使用すると**、外部ユーザーはオンプレミス会議に参加できます。 従来のエッジ サーバーの Web 会議外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。

外部 **Web 会議外部** ポート値 **443** は、会議クライアント用に構成された既定の伝送制御プロトコル (TCP) セッション開始プロトコル (SIP) ポートです。 既定値が使用されていない場合は、外部 Web 会議の外部ポート **値を更新** します。

フェデレーションに **このエッジ サーバーを使用** する場合は、[このエッジ プールをフェデレーションとパブリック IM 接続に使用する] チェック ボックスをオンにします。 複数のエッジ サーバーを展開している場合、そのうちの 1 つだけがフェデレーションで有効になります。 このボックスをオンにしない場合、後でフェデレーションを有効にした場合は、トポロジ ビルダーのマージ ウィザードを再度実行し、トポロジを公開する必要があります。 詳細については、「[フェーズ 4:Merge Topologies (トポロジの結合)](/previous-versions/office/lync-server-2013/phase-4-merge-topologies)」を参照してください。