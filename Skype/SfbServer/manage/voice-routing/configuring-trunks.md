---
title: Skype for Business Server でのトランクの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: エンタープライズ VoIP 展開の一環として、仲介サーバーと 1 つ以上のピア間のトランクを構成して、組織内の エンタープライズ VoIP クライアントとデバイスに公衆交換電話網 (PSTN) 接続を提供できます。
ms.openlocfilehash: 57b8635d635c0fd0b8c41c95f92af768ff84dfd4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800117"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Skype for Business Server でのトランクの構成

エンタープライズ VoIP 展開の一環として、仲介サーバーと次の 1 つ以上のピア間のトランクを構成して、組織内の エンタープライズ VoIP クライアントおよびデバイスに公衆交換電話網 (PSTN) 接続を提供できます。

- インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続
- PSTN ゲートウェイ
- 構内交換機 (PBX)

詳細については [、「Skype for Business Server での PSTN 接続の計画」を参照してください](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。

> [!IMPORTANT]
> トランク構成を開始する前に、トポロジが既に作成済みであること、および仲介サーバーとそのピアが構成され、互いに関連付けられていることを確認します。 詳細については [、「Skype for Business Server のトポロジ ビルダーでのゲートウェイの定義」を参照してください](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。

> [!NOTE]
> トランク構成の一部として、Skype for Business Server メディア バイパス機能を有効にして、メディアで仲介サーバーをバイパスできます。 トランクは、メディア バイパスを有効にして構成できますが、有効にすることを強く推奨します。 詳細については [、「Skype for Business でメディア バイパスを計画する」を参照してください](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。
