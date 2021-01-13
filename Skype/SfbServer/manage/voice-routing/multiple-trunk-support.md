---
title: Skype for Business Server での複数トランクのサポート
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
description: Skype for Business Server の機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートします。 これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コントローラー (SBC)、または IP-PBX の間の論理的な関連付けであるトランクを定義することで行います。 トポロジ ビルダーを使用して、ゲートウェイを仲介サーバー (トランク) に関連付けます。
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826227"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Skype for Business Server での複数トランクのサポート

Skype for Business Server の機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートします。 これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コントローラー (SBC)、または IP-PBX の間の論理的な関連付けであるトランクを定義することで行います。 トポロジ ビルダーを使用して、ゲートウェイを仲介サーバー (トランク) に関連付けます。

- Skype for Business Server でトランクを割り当てるまたは削除するには、最初にトポロジ ビルダーでトランクを定義する必要があります。 トランクは、仲介サーバーの完全修飾ドメイン名 (FQDN)、仲介サーバーリッスン ポート、ゲートウェイ FQDN、およびゲートウェイ リッスン ポートの関連付けで構成されます。
- 複数のトランクを構成するには、同じゲートウェイと仲介サーバーの間に複数の関連付けを作成できます。 これにより、PBX (エンタープライズ VoIP) の相互運用シナリオで特に役立つ、ネットワーク インフラストラクチャの回復性が向上します。 

トランクが定義されている場合は、ルートに関連付けられている必要があります。 トランクをルートに関連付ける場合は、トポロジ ビルダーでトランクの簡単な名前を定義します。 この簡単な名前は、トランクをルートに関連付けできる Skype for Business Server コントロール パネルのトランク名として使用されます。 単純なトランク名は、Skype for Business Server 管理シェルからのゲートウェイ名として使用されます。

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

管理者は、仲介サーバーに関連付けられている既定のトランクを選択する必要があります。 トポロジ ビルダーで、関連付けられた仲介サーバーを右クリックし、[プロパティ] をクリック **します**。 仲介サーバーの既定のゲートウェイを指定します。 

次の図は、仲介サーバーとゲートウェイごとに定義されている複数のトランクを示しています。 

![複数トランク割り当て](../../media/multiple-trunk-assignments.jpg)
