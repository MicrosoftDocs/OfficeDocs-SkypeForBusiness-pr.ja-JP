---
title: ダイレクト ルーティング用にリングバック ボットをセットアップする
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: 呼び出しが確立されているときに発生する可能性がある予期しない無音を防ぐために、直接ルーティングにリングバック ボットを使用する方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ec53f1d4f9cd21d3b28c87c07c1bc91d48b9b58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098423"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>ダイレクト ルーティング用にリングバック ボットをセットアップする

この記事では、呼び出しの確立に長い時間がかかる場合に発生する可能性がある予期しない無音を回避するために使用できるリングバック ボットについて説明します。 リングバック ボットは、メディア以外のバイパス モードのダイレクト ルーティングで利用できます。

公衆交換電話網 (PSTN) から Teams クライアントへの着信通話は、確立が想定以上に長くなる場合があります。 これは、さまざまな理由で発生する可能性があります。 この場合、発信者は何も聞こえない、Teams クライアントが呼び出されない、一部の通信プロバイダーが通話をキャンセルする場合があります。

リングバック ボットは、このシナリオで発生する可能性がある予期しない無音を回避するのに役立ちます。 PSTN から Teams クライアントへの着信通話の場合、リングバック ボットは呼び出し元に対して独自の音声信号を再生し、Teams が通話を確立中を示します。

> [!NOTE]
> リングバック ボットは、Teams バックエンドから初期メディアを生成します。 一部の国と地域では、メディアの流れを開始するときに通話料金が請求される場合があります。

## <a name="configure-the-ringback-bot"></a>リングバック ボットを構成する

[Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway)コマンドレットを使用して、以前に定義されたセッション ボーダー コントローラー (SBC) 構成または [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway)コマンドレットを変更し **、GenerateRingingWhileLocatingUser** パラメーターと共に新しい SBC 構成を作成し、リングバック ボットを構成します。

- リングバック ボットを有効にする場合は **、GenerateRingingWhileLocatingUser** パラメーターを次に **$True。** これが既定値です。 

- リングバック ボットをオフにする場合は **、GenerateRingingWhileLocatingUser** パラメーターを **$False。** 

## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)