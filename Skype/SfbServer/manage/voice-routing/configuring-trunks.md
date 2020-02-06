---
title: Skype for Business Server で trunks を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: エンタープライズ Voip の展開の一部として、仲介サーバーと1つ以上のピアの間でトランクを構成して、組織内のエンタープライズ Voip クライアントとデバイスの公衆交換電話網 (PSTN) 接続を提供できます。
ms.openlocfilehash: 41e92f994606ea2153359546d408335d13a21f88
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817017"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Skype for Business Server で trunks を構成する

エンタープライズ Voip の展開の一部として、仲介サーバーと次のピアの1つ以上にトランクを構成して、組織内のエンタープライズボイスクライアントとデバイスの公衆交換電話網 (PSTN) 接続を提供できます。

- インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続
- PSTN ゲートウェイ
- 構内交換機 (PBX)

詳細については、「 [Skype For Business Server での PSTN 接続の計画](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)」を参照してください。

> [!IMPORTANT]
> トランクの構成を開始する前に、トポロジが作成され、仲介サーバーとそのピアが構成されて互いに関連付けられていることを確認します。 詳細については、「 [Skype For Business Server のトポロジビルダーでゲートウェイを定義する](../../deploy/deploy-enterprise-voice/define-a-gateway.md)」を参照してください。

> [!NOTE]
> トランク構成の一部として、Skype for Business Server media バイパス機能を有効にすることで、メディアが仲介サーバーをバイパスすることを可能にすることができます。 Trunks は、メディアのバイパスを有効にするかどうかを指定して構成できますが、有効にすることを強くお勧めします。 詳細については、「 [Skype For business のメディアバイパスの計画](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)」を参照してください。
