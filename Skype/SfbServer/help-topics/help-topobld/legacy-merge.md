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
description: Web 会議の外部 FQDN を使用すると、外部ユーザーはオンプレミスの会議に参加できます。 従来のエッジ サーバーの Web 会議外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: b49d8ed17bdc56050e00216c5506b85db2b1d3aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832997"
---
# <a name="legacy-merge"></a>従来版のマージ

**Web 会議の外部 FQDN を使用** すると、外部ユーザーはオンプレミスの会議に参加できます。 従来のエッジ サーバーの Web 会議外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。

外部 **Web 会議** の外部ポート値 **443** は、会議クライアント用に構成された既定の伝送制御プロトコル (TCP) セッション開始プロトコル (SIP) ポートです。 既定値を使用していない場合は、外部 Web 会議の外部 **ポート値を更新** します。

フェデレーションに **このエッジ サーバーを使用する場合は** 、[このエッジ プールをフェデレーションとパブリック IM 接続に使用する] チェック ボックスをオンにします。 複数のエッジ サーバーを展開している場合、そのうちの 1 つだけがフェデレーションで有効になります。 このチェック ボックスをオフにし、後でフェデレーションを有効にする場合は、トポロジ ビルダー結合ウィザードを再度実行し、トポロジを公開する必要があります。 詳細については、「[フェーズ 4:Merge Topologies (トポロジの結合)](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)」を参照してください。


