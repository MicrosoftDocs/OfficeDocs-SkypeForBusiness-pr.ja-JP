---
title: Skype for Business Server での複数のトランクのサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートしています。 これらの関連付けは、仲介サーバープールと公衆交換電話網 (PSTN) ゲートウェイ、セッション境界コントローラー (SBC)、または ip-pbx との間の論理的な関連付けであるトランクを定義することによって行われます。 トポロジビルダーを使用して、ゲートウェイを仲介サーバーに関連付けます (つまり、trunks)。
ms.openlocfilehash: a6a0134ee04d939a10aaf9e36c81124d085af5aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274913"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Skype for Business Server での複数のトランクのサポート

Skype for Business Server 機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートしています。 これらの関連付けは、仲介サーバープールと公衆交換電話網 (PSTN) ゲートウェイ、セッション境界コントローラー (SBC)、または ip-pbx との間の論理的な関連付けであるトランクを定義することによって行われます。 トポロジビルダーを使用して、ゲートウェイを仲介サーバーに関連付けます (つまり、trunks)。

- Skype for Business Server でトランクを割り当てまたは削除するには、まず、トポロジビルダーで樹幹を定義する必要があります。 トランクは、仲介サーバーの完全修飾ドメイン名 (FQDN)、仲介サーバーのリッスンポート、ゲートウェイの FQDN、ゲートウェイのリスニングポートで構成されます。
- 複数の trunks を構成するために、同じゲートウェイと仲介サーバー間に複数の関連付けを作成することができます。 これにより、エンタープライズ Voip インフラストラクチャのさらなる弾力性が提供されます。これは、プライベート支店交換 (PBX) 間の運用シナリオで特に便利です。 

トランクが定義されている場合は、ルートに関連付ける必要があります。 トランクをルートに関連付けるには、トポロジビルダーでトランクの単純な名前を定義します。 この簡易名は、Skype for Business Server コントロールパネルでトランク名として使用されます。ここでは、trunks をルートに関連付けることができます。 簡単なトランク名は、Skype for Business Server 管理シェルのゲートウェイ名として使用されます。

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

管理者は、仲介サーバーに関連付けられている既定のトランクを選択する必要があります。 トポロジビルダーで、関連する仲介サーバーを右クリックし、[**プロパティ**] をクリックします。 仲介サーバーの既定のゲートウェイを指定します。 

次の図は、各仲介サーバーとゲートウェイに対して定義されている複数の trunks を示しています。 

![複数のトランクの割り当て](../../media/multiple-trunk-assignments.jpg)
