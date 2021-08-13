---
title: サーバーでのトランクのSkype for Business Server
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
description: エンタープライズ VoIP 展開の一環として、仲介サーバーと 1 つ以上のピア間のトランクを構成して、組織内の エンタープライズ VoIP クライアントおよびデバイスに公衆交換電話網 (PSTN) 接続を提供できます。
ms.openlocfilehash: 82491d566e36ce819456c3d2a8983f97dd6c4f17d4d7cece71a066342d48efea
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333459"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>サーバーでのトランクのSkype for Business Server

エンタープライズ VoIP 展開の一環として、仲介サーバーと 1 つ以上の次のピア間のトランクを構成して、組織内の エンタープライズ VoIP クライアントおよびデバイスに公衆交換電話網 (PSTN) 接続を提供できます。

- インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続
- PSTN ゲートウェイ
- 構内交換機 (PBX)

詳細については、「Plan [for PSTN connectivity in Skype for Business Server」 を参照してください](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。

> [!IMPORTANT]
> トランク構成を開始する前に、トポロジが既に作成済みであること、および仲介サーバーとそのピアが構成され、互いに関連付けられていることを確認します。 詳細については、「トポロジ[ビルダーでゲートウェイを定義する」を参照Skype for Business Server。](../../deploy/deploy-enterprise-voice/define-a-gateway.md)

> [!NOTE]
> トランク構成の一環として、メディア バイパス機能Skype for Business Serverメディアを有効にして、仲介サーバーをバイパスできます。 トランクは、メディア バイパスを有効にした場合と使用しない場合に構成できますが、有効にすることを強く推奨します。 詳細については、「Plan [for media bypass in Skype for Business」 を参照してください](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。
