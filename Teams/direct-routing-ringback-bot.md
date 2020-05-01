---
title: 直接ルーティング用に Ringback ボットを設定する
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Ringback bot を直接ルーティング用に使用して、通話が確立されているときに発生する可能性のある予期しない silences を防ぐ方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1db113a610c153f821a0d92187744e6ca34e3ce3
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951192"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>直接ルーティング用に Ringback ボットを設定する

この記事では、Ringback ボットについて説明します。これは、通話の発信に時間がかかる場合に発生する可能性のある予期しない silences を回避するために使用できます。 Ringback bot は、メディア以外のバイパスモードで直接ルーティングすることができます。

公衆交換電話網 (PSTN) から Teams への着信通話は、確立に予想以上に時間がかかることがあります。 これはさまざまな理由で発生する可能性があります。 この問題が発生すると、呼び出し元は何も聞こえないため、Teams クライアントは呼び出しを行わず、通信プロバイダーによって通話がキャンセルされる可能性があります。

Ringback ボットは、このシナリオで発生する可能性のある予期しない silences を回避するのに役立ちます。 PSTN から Teams クライアントへの着信通話については、Ringback bot は、呼び出し元に対して特徴的な音声信号を再生し、チームが通話の確立プロセス中であることを示します。

> [!NOTE]
> Ringback ボットは、Teams バックエンドから早期メディアを生成します。 一部の国と地域では、メディアの流れを開始したときに、通話料金がかかる場合があります。

## <a name="configure-the-ringback-bot"></a>Ringback ボットを構成する

**GenerateRingingWhileLocatingUser**パラメーターと共に[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)コマンド[レットを使用して](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway)、Ringback ボットを構成します。

Ringback bot を有効にするには、 **GenerateRingingWhileLocatingUser**パラメーターを [ **$True**] に設定します。 これは既定の値です。 

Ringback bot をオフにするには、 **GenerateRingingWhileLocatingUser**パラメーターを [ **$False**] に設定します。 

## <a name="related-topics"></a>関連項目

- [Teams での PowerShell の概要](teams-powershell-overview.md)