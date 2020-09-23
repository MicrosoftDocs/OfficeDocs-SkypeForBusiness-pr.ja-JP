---
title: 従来版のマージ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Web 会議の外部 FQDN を使うと、外部ユーザーはオンプレミスの会議に参加できます。 従来のエッジサーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: 984d40f8797a974a5865cca37ba1057dc638d886
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217998"
---
# <a name="legacy-merge"></a>従来版のマージ

**Web 会議の外部 FQDN**を使うと、外部ユーザーはオンプレミスの会議に参加できます。 従来のエッジサーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。

**外部 Web 会議の外部ポート**の値は**443**で、会議クライアントに対して構成されている既定の伝送制御プロトコル (TCP) セッション開始プロトコル (SIP) ポートです。 既定値が使用されていない場合は、 **外部 Web 会議の外部ポート** 値を更新します。

このエッジサーバーをフェデレーション用に使用する場合は、[ **このエッジプールをフェデレーションとパブリック IM 接続に使用** する] チェックボックスをオンにします。 複数のエッジ サーバーを展開している場合、そのうちの 1 つだけがフェデレーションで有効になります。 このボックスをチェックせずに、後でフェデレーションを有効にする場合は、トポロジビルダーマージウィザードをもう一度実行して、トポロジを公開する必要があります。 詳細については、「[フェーズ 4:Merge Topologies (トポロジの結合)](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)」を参照してください。


