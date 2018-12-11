---
title: ビジネス サーバーの Skype でトランクを構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: エンタープライズ VoIP 展開の一部として、エンタープライズ VoIP クライアントと、組織内のデバイスの公衆交換電話網 (PSTN) 接続を提供するには、仲介サーバーと 1 つまたは複数のピア間のトランクを構成できます。
ms.openlocfilehash: 34391e09bb87144252634b572bf0eac6a10fe1d9
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222864"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>ビジネス サーバーの Skype でトランクを構成します。

エンタープライズ VoIP 展開の一部として、仲介サーバーと 1 つ以上のエンタープライズ VoIP クライアントと、組織内のデバイスの公衆交換電話網 (PSTN) 接続を提供する次のピア間のトランクを構成できます。

- インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続
- PSTN ゲートウェイ
- 構内交換機 (PBX)

詳細については、 [Skype のビジネス サーバーの PSTN への接続の計画](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)を参照してください。

> [!IMPORTANT]
> トランク構成を開始する前に、トポロジが作成されたことと、仲介サーバーとそのピアを構成および相互に関連付けられているを確認します。 詳細については、 [Skype のビジネス サーバーで、トポロジ ビルダーでゲートウェイを定義する](../../deploy/deploy-enterprise-voice/define-a-gateway.md)を参照してください。

> [!NOTE]
> 、トランクの構成の一部として、Skype ビジネス サーバー メディア バイパス機能は、仲介サーバーをバイパスするメディアを有効にするを有効にできます。 またはメディアのバイパスを有効にせず、トランクを構成することができますが、それを有効にすることを強くお勧めします。 詳細については、[ビジネスの Skype で使用しないメディアの計画](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)を参照してください。