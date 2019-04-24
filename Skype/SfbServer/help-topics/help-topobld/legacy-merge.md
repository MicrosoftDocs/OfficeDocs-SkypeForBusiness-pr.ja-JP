---
title: 従来版のマージ
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: Web 会議の外部 FQDN は、外部ユーザーがオンプレミス会議への参加を許可します。 従来のエッジ サーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: a6bb1ee83496e98f6097905fdf24c62d20d657ae
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200138"
---
# <a name="legacy-merge"></a>従来版のマージ

**Web カンファレンスの外部 FQDN**では、オンプレミス会議に参加する外部ユーザーを許可します。 従来のエッジ サーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。

会議クライアント用に構成された既定の伝送制御プロトコル (TCP) セッション開始プロトコル (SIP) ポートを**443**の**外部の Web 会議の外部ポート**の値には。 既定値が使用できない場合は、**外部の Web 会議の外部ポート**の値を更新します。

フェデレーションのこのエッジ サーバーを使用する場合は、[**このエッジ プールがフェデレーションとパブリック IM 接続の使用**] チェック ボックスを選択します。 展開される複数のエッジ サーバーがあれば、フェデレーションの 1 つだけ有効にします。 このボックスをオンにしないし、フェデレーションを有効にすることを決定後、する必要がありますトポロジ ビルダー結合ウィザードを再度実行すると、トポロジを公開します。 詳細については、「[フェーズ 4: トポロジを結合します](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).


