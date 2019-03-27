---
title: Skype のビジネス サーバー用の複数のトランク サポート
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバーの機能のための Skype では、ゲートウェイと仲介サーバーの間で複数のアソシエーションをサポートします。 これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コント ローラー (SBC)、または IP PBX との間の論理的な関連付けには、トランクを定義することによって行われます。 ゲートウェイを仲介サーバー (つまり、トランクなど) に関連付けるには、トポロジ ビルダーを使用します。
ms.openlocfilehash: 5d093bee56597474f0cefcf1053536774f2eb795
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896568"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Skype のビジネス サーバー用の複数のトランク サポート

ビジネス サーバーの機能のための Skype では、ゲートウェイと仲介サーバーの間で複数のアソシエーションをサポートします。 これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コント ローラー (SBC)、または IP PBX との間の論理的な関連付けには、トランクを定義することによって行われます。 ゲートウェイを仲介サーバー (つまり、トランクなど) に関連付けるには、トポロジ ビルダーを使用します。

- 割り当てまたはトランクを Skype のビジネス サーバーの削除、最初にトポロジ ビルダーでトランクを定義する必要があります。 トランクは、次の関連で構成されています: ドメイン名 (FQDN)、仲介サーバーのリッスン ポート、ゲートウェイの FQDN、およびゲートウェイ リッスン ポートを仲介サーバーの完全修飾します。
- 複数のトランクを構成するには、同じゲートウェイと仲介サーバーとの間の複数の関連付けを作成できます。 これは、構内交換 (機 PBX) の interoperational のシナリオで特に便利ですが、エンタープライズ VoIP インフラストラクチャに追加の復元機能を提供します。 

トランクを定義するときは、工順に関連付けられている場合があります。 ルートにトランクを関連付けるには、トポロジ ビルダーでは、トランクの簡易名を定義します。 この単純な名前は、ビジネス サーバーのコントロール パネル]、トランクできるルートに関連付けられているに、Skype でトランクの名前として使用されます。 トランクの単純な名前は、サーバー管理シェルのビジネスに、Skype からゲートウェイの名前として使用されます。

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

管理者は、仲介サーバーに関連付けられている既定のトランクを選択してください。 トポロジ ビルダーでは、関連付けられている仲介サーバーを右クリックし、し、[**プロパティ**] をクリックします。 仲介サーバーのデフォルト ゲートウェイを指定します。 

次の図は、仲介サーバーとゲートウェイごとに定義されている複数のトランクを示しています。 

![トランクの複数の割り当て](../../media/multiple-trunk-assignments.jpg)
