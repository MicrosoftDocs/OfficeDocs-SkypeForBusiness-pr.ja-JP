---
title: E9-1-1 展開のスコープを定義するSkype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: E9-1-1 の展開を計画するために必要な決定は、Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 8ad07897732251dbc38f0e69c7def54d62396e80
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389089"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>E9-1-1 展開のスコープを定義するSkype for Business Server

E9-1-1 の展開を計画するために必要な決定は、Skype for Business Server エンタープライズ VoIP。

E9-1-1 Skype for Businessを構成する前に、E9-1-1 展開を計画する必要があります。 次のような点を検討します。

 **E9-1-1 に関する組織のポリシーと法的義務は何ですか?**

 PBX (E9-1-1 用語では複数回線電話システム (MLTS) と呼ばれます) 使用時の E9-1-1 の法的義務は州ごとに異なります。 法務チームに相談して、関連する地域でのサービスの展開に適用される可能性のあるSkype for Businessを理解する必要があります。

 **エンタープライズ内のどの領域で E9-1-1 を有効にする必要があるか**

 E9-1-1 は、エンタープライズ全体で有効にすることも、特定の場所だけで有効にすることもできます。たとえば、オフィスの E9-1-1 の要件が州によって異なる場合や、米国以外のサイトを除外する必要がある場合があります。

 **E9-1-1 をブランチ サイトにどのように展開するか**

 E9-1-1 をブランチ サイトに展開するときは、音声の復元の概念を理解することが重要です。 E-9-1-1 SIP トランクを集中管理し、WAN の停止が発生した場合、サインインしているクライアントは、位置情報サービスから場所を取得したり、緊急サービス サービス プロバイダーに接続したりできない場合があります。 Skype for Businessでは、回復力のあるデータ ネットワークの構築、各ブランチでの SIP トランクの展開、停止中のローカル ゲートウェイへの緊急通話のプッシュなど、ブランチ オフィスでの音声復元を処理するためのいくつかの戦略が用意されています。 詳細については、「[Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency)」を参照してください。

 **ネットワーク外のユーザーに対し、E9-1-1 を有効にするかどうか**

 場所の自動取得は、組織のネットワーク内にあるクライアントでのみ使用できます。そのため、組織は、オフオンプレミスの間に Skype for Business クライアントから行われた E9-1-1 通話をサポートするかどうかを決定する必要があります。 たとえば、ユーザーが自宅や顧客サイトから作業している場合に、緊急電話を出すのを有効にしますか? クライアントがエンタープライズ ネットワークの外部にある場合、クライアントはユーザーに場所を求めるメッセージを表示するように構成できます。 ただし、これらのユーザーが指定した場所はマスター ストリート アドレス ガイド (MSAG) に対して事前に評価できないので、緊急サービス サービス プロバイダーのディスパッチャーは、呼び出しを公衆安全応答ポイント (PSAP) にルーティングする前に、その場所の有効性を発信者と口頭で確認する必要があります。

> [!NOTE]
> Skype for Business VPN を使用して組織のネットワークに接続するユーザーのクライアントは、内部 IP アドレス情報を取得できますが、これらのアドレスを使用してユーザーの実際の場所を識別することはできませんので、VPN サブネットを位置情報サービスから除外する必要があります。

 **米国以外のサイトに緊急通話のルーティングを提供するかどうか**

 緊急サービスのサービス プロバイダーのサービス対象範囲外 (国外の場所など) にある会社の領域に緊急通話のルーティングを提供したい場合があります。この場合は、新しいサイトを作成し、ローカル PSTN ゲートウェイ経由で通話をルーティングする PSTN 使用法を参照する音声ポリシーをサイトに割り当てます。