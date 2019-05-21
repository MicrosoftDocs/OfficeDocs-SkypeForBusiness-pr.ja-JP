---
title: Skype for Business Server での E9 展開のスコープを定義する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Skype for Business Server Enterprise Voice での E9 展開の計画に必要な決定。
ms.openlocfilehash: 648713ce3474779a588d638e3e81272fbd62e2f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276462"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Skype for Business Server での E9 展開のスコープを定義する

Skype for Business Server Enterprise Voice での E9 展開の計画に必要な決定。

Skype for Business for E9-1 を構成する前に、E9 の展開を計画する必要があります。 次のような点を検討します。

 **E9 に関連する組織のポリシーおよび法的義務は何ですか。**

 PBX (E9-1-1 用語では複数回線電話システム (MLTS) と呼ばれます) 使用時の E9-1-1 の法的義務は州ごとに異なります。 法務チームに相談して、関連する地域の Skype for Business の展開に適用される可能性がある義務について理解する必要があります。

 **エンタープライズ内のどの領域で E9-1-1 を有効にする必要があるか**

 E9-1-1 は、エンタープライズ全体で有効にすることも、特定の場所だけで有効にすることもできます。たとえば、オフィスの E9-1-1 の要件が州によって異なる場合や、米国以外のサイトを除外する必要がある場合があります。

 **E9-1-1 をブランチ サイトにどのように展開するか**

 E9-1-1 をブランチ サイトに展開するときは、音声の復元の概念を理解することが重要です。 一元化された電子 9-1-1 SIP trunks を使用していて、WAN の障害が発生した場合、クライアントは、場所情報サービスからの場所を取得できないか、緊急サービスサービスプロバイダに接続できない可能性があります。 Skype for Business には、回復可能なデータネットワークの使用、各ブランチへの SIP トランクの展開、停止中のローカルゲートウェイへの緊急通話の配信など、支店での音声回復性を処理するためのいくつかの戦略が用意されています。 詳細については、「[Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)」を参照してください。

 **ネットワーク外のユーザーに対し、E9-1-1 を有効にするかどうか**

 自動的な場所の取得は、組織のネットワーク内にあるクライアントに対してのみ利用できます。そのため、組織は、Skype for Business クライアントから発信された E9 の通話をオフプレミスでサポートするかどうかを決定する必要があります。 たとえば、ユーザーが自宅で作業している場合や顧客サイトから作業している場合に、緊急電話をかけることができますか。 クライアントがエンタープライズネットワークの外部に配置されている場合は、ユーザーに位置情報の入力を求めるようにクライアントを構成できます。 ただし、ユーザーが指定した場所は、マスター番地の住所ガイド (MSAG) に対して prevalidated できないため、緊急サービスサービスプロバイダーディスパッチャーは、ルーティング前に発信者による場所の有効性を確認する必要があります。公衆安全応答ポイント (PSAP) への通話。

> [!NOTE]
> VPN を使用して組織のネットワークに接続しているユーザーの Skype for Business クライアントは、内部の IP アドレス情報を取得できますが、これらのアドレスを使ってユーザーの実際の場所を特定することはできないため、VPN サブネットを除外することが重要です。場所情報サービスから。

 **米国以外のサイトに緊急通話のルーティングを提供するかどうか**

 緊急サービスのサービス プロバイダーのサービス対象範囲外 (国外の場所など) にある会社の領域に緊急通話のルーティングを提供したい場合があります。この場合は、新しいサイトを作成し、ローカル PSTN ゲートウェイ経由で通話をルーティングする PSTN 使用法を参照する音声ポリシーをサイトに割り当てます。


