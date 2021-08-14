---
title: 複数のトランクのサポート (Skype for Business Server
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
description: Skype for Business Server機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートします。 これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コントローラー (SBC)、または IP-PBX の間の論理的な関連付けであるトランクを定義することで行います。 トポロジ ビルダーを使用して、ゲートウェイを仲介サーバー (トランク) に関連付けます。
ms.openlocfilehash: 93d1dd00a2b60d7d346dcc6342ddefa9170308fb3ea5215b90460d17a78819b4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351477"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>複数のトランクのサポート (Skype for Business Server

Skype for Business Server機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートします。 これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コントローラー (SBC)、または IP-PBX の間の論理的な関連付けであるトランクを定義することで行います。 トポロジ ビルダーを使用して、ゲートウェイを仲介サーバー (トランク) に関連付けます。

- トポロジ ビルダーでトランクを割り当Skype for Business Server削除するには、まずトポロジ ビルダーでトランクを定義する必要があります。 トランクは、仲介サーバーの完全修飾ドメイン名 (FQDN)、仲介サーバーリスニング ポート、ゲートウェイ FQDN、ゲートウェイ リスニング ポートの関連付けで構成されます。
- 複数のトランクを構成するには、同じゲートウェイと仲介サーバーの間に複数の関連付けを作成できます。 これにより、プライベート ブランチ 交換 (PBX) エンタープライズ VoIPのシナリオで特に役立つ、インフラストラクチャに対する追加の復元性が提供されます。 

トランクが定義されている場合は、ルートに関連付けられている必要があります。 トランクをルートに関連付けるには、トポロジ ビルダーでトランクの単純な名前を定義します。 この単純な名前は、トランクをルートに関連付Skype for Business Serverコントロール パネルのトランク名として使用されます。 単純なトランク名は、管理シェルのゲートウェイ名Skype for Business Serverされます。

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

管理者は、仲介サーバーに関連付けられている既定のトランクを選択する必要があります。 トポロジ ビルダーで、関連付けられた仲介サーバーを右クリックし、[プロパティ] を **クリックします**。 仲介サーバーの既定のゲートウェイを指定します。 

次の図は、仲介サーバーとゲートウェイごとに定義されている複数のトランクを示しています。 

![複数のトランクの割り当て](../../media/multiple-trunk-assignments.jpg)
