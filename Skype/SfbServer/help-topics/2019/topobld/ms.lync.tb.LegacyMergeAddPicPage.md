---
title: 従来版のマージ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Web 会議の外部 FQDN を使うと、外部ユーザーはオンプレミスの会議に参加できます。 従来のエッジサーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: 1f2a1e9ca3d3ca20b7b0fe6832a0e394d7fac5ce
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688340"
---
# <a name="legacy-merge"></a>従来版のマージ

**Web 会議の外部 FQDN**を使うと、外部ユーザーはオンプレミスの会議に参加できます。 従来のエッジサーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。

**外部 Web 会議の外部ポート**値は、 **443**の既定の伝送制御プロトコル (TCP) セッション開始プロトコル (SIP) ポートで、会議クライアント用に構成されています。 既定値を使用しなかった場合は、**外部 Web 会議の外部ポート**の値を更新します。

このエッジサーバーをフェデレーション用に使用する場合は、[**このエッジプールをフェデレーションとパブリック IM 接続に使用**する] チェックボックスをオンにします。 複数のエッジサーバーが展開されている場合は、そのうちの1つのみがフェデレーション対象として有効になります。 このチェックボックスをオフにして、後でフェデレーションを有効にすることにした場合は、トポロジの公開に加えて、トポロジビルダーのマージウィザードをもう一度実行する必要があります。 詳しくは、「[フェーズ 4: マージトポロジ](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)」をご覧ください。


