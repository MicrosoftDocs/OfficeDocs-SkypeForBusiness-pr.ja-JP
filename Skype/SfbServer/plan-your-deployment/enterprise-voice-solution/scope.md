---
title: Skype for Business Server での E9-1-1 展開のスコープの定義
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Skype for Business Server 2013 での E9-1-1 展開の計画に必要エンタープライズ VoIP。
ms.openlocfilehash: bec80e94c5bc2044359875f7c56f92a1348464c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813427"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Skype for Business Server での E9-1-1 展開のスコープの定義

Skype for Business Server 2013 での E9-1-1 展開の計画に必要エンタープライズ VoIP。

Skype for Business for E9-1-1 を構成する前に、E9-1-1 の展開を計画する必要があります。 次のような点を検討します。

 **E9-1-1 に関する組織のポリシーと法的義務について**

 PBX (E9-1-1 用語では複数回線電話システム (MLTS) と呼ばれます) 使用時の E9-1-1 の法的義務は州ごとに異なります。 法務チームに相談して、関連地域での Skype for Business の展開に適用される可能性がある義務を理解する必要があります。

 **エンタープライズ内のどの領域で E9-1-1 を有効にする必要があるか**

 E9-1-1 は、エンタープライズ全体で有効にすることも、特定の場所だけで有効にすることもできます。たとえば、オフィスの E9-1-1 の要件が州によって異なる場合や、米国以外のサイトを除外する必要がある場合があります。

 **E9-1-1 をブランチ サイトにどのように展開するか**

 E9-1-1 をブランチ サイトに展開するときは、音声の復元の概念を理解することが重要です。 E-9-1-1 SIP トランクを集中管理し、WAN の停止が発生した場合、サインインするクライアントは場所情報サービスから場所を取得したり、緊急サービス サービス プロバイダーに接続したりできない可能性があります。 Skype for Business は、ブランチ オフィスでの音声の復元に対応するためのいくつかの戦略を提供します。たとえば、回復力のあるデータ ネットワークの確保、各ブランチでの SIP トランクの展開、停止時のローカル ゲートウェイへの緊急通話のプッシュなどです。 詳細については、「[Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)」を参照してください。

 **ネットワーク外のユーザーに対し、E9-1-1 を有効にするかどうか**

 場所の自動取得は、組織のネットワーク内にあるクライアントでのみ利用できます。そのため、組織は、オフオンプレミスの間に Skype for Business クライアントから行われた E9-1-1 通話をサポートするかどうかを決定する必要があります。 たとえば、ユーザーが自宅や顧客のサイトから作業している場合に、緊急電話をかけ付け可能にしますか。 クライアントがエンタープライズ ネットワークの外部にある場合は、ユーザーに場所の入力を求めるメッセージを表示するようにクライアントを構成できます。 ただし、これらのユーザーが指定した場所は、マスター番地ガイド (MSAG) に対して事前に確認できないので、緊急サービス サービス プロバイダー ディスパッチャーは、緊急サービス サービス プロバイダーのディスパッチャーが、通話を公衆安全応答ポイント (PSAP) にルーティングする前に、発信者と言葉で場所の有効性を確認する必要があります。

> [!NOTE]
> VPN を使用して組織のネットワークに接続するユーザーの Skype for Business クライアントは内部 IP アドレス情報を取得できますが、これらのアドレスを使用してユーザーの実際の場所を識別できないので、VPN サブネットを場所情報サービスから除外する必要があります。

 **米国以外のサイトに緊急通話のルーティングを提供するかどうか**

 緊急サービスのサービス プロバイダーのサービス対象範囲外 (国外の場所など) にある会社の領域に緊急通話のルーティングを提供したい場合があります。この場合は、新しいサイトを作成し、ローカル PSTN ゲートウェイ経由で通話をルーティングする PSTN 使用法を参照する音声ポリシーをサイトに割り当てます。


