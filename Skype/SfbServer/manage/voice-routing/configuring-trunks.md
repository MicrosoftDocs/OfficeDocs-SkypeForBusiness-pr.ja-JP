---
title: サーバーでのトランクのSkype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: エンタープライズ VoIP 展開の一環として、仲介サーバーと 1 つ以上のピア間のトランクを構成して、組織内の エンタープライズ VoIP クライアントおよびデバイスに公衆交換電話網 (PSTN) 接続を提供できます。
ms.openlocfilehash: 080678192326af1933996ef36ad953c3eff90f50
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391089"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>サーバーでのトランクのSkype for Business Server

エンタープライズ VoIP 展開の一環として、仲介サーバーと 1 つ以上の次のピア間のトランクを構成して、組織内の エンタープライズ VoIP クライアントおよびデバイスに公衆交換電話網 (PSTN) 接続を提供できます。

- インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続
- PSTN ゲートウェイ
- 構内交換機 (PBX)

詳細については、「Plan [for PSTN connectivity in Skype for Business Server」 を参照してください](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。

> [!IMPORTANT]
> トランク構成を開始する前に、トポロジが既に作成済みであること、および仲介サーバーとそのピアが構成され、互いに関連付けられていることを確認します。 詳細については、「トポロジ [ビルダーでゲートウェイ](../../deploy/deploy-enterprise-voice/define-a-gateway.md)を定義する」を参照Skype for Business Server。

> [!NOTE]
> トランク構成の一環として、メディア バイパス機能Skype for Business Serverメディアを有効にして、仲介サーバーをバイパスできます。 トランクは、メディア バイパスを有効にした場合と使用しない場合に構成できますが、有効にすることを強く推奨します。 詳細については、「Plan [for media bypass in Skype for Business」を参照してください](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。
