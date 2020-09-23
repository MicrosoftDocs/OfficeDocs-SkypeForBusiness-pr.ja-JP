---
title: フロントエンド サーバーの併置を追加する (2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Enterprise Edition 展開の場合は、音声ビデオ会議サービス、仲介サーバー、またはその両方をフロント エンド プールに併置するか、またはそれぞれをスタンドアロン サーバーとして展開できます。Standard Edition サーバー展開の場合は、会議が有効であれば、常に音声ビデオ会議サービスが併置されます。
ms.openlocfilehash: 86bef8bdcbdd36033e64912bdce2d9ea3469e45c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216518"
---
# <a name="add-front-end-server-collocations-2010"></a>フロントエンド サーバーの併置を追加する (2010)

Enterprise Edition 展開の場合は、音声ビデオ会議サービス、仲介サーバー、またはその両方をフロント エンド プールに併置するか、またはそれぞれをスタンドアロン サーバーとして展開できます。Standard Edition サーバー展開の場合は、会議が有効であれば、常に音声ビデオ会議サービスが併置されます。

> [!NOTE]
> [**機能の選択**] ページで [**電話会議**] を選択した場合には、音声ビデオ会議サービスが必要です。Enterprise Edition フロント エンド プールでは、併置された音声ビデオ会議サービスまたはスタンドアロン音声ビデオ会議プールを使用できます。[電話会議] を選択しなかった場合、[音声ビデオ会議サービスを併置する] は使用できません。

Standard Edition フロントエンド サーバーまたは Enterprise Edition フロントエンド プールに仲介サーバーの役割を併置できます。 メディア バイパスとドメイン ネーム システム (DNS) 負荷分散をサポートする認定公衆交換電話網 (PSTN) ゲートウェイへ直接 SIP 接続を展開する場合、スタンドアロンの仲介サーバー プールは必要ありません。 スタンドアロンの仲介サーバー プールが必要でないのは、認定ゲートウェイが仲介サーバーのプールへの DNS 負荷分散に対応しており、プール内のすべての仲介サーバーからトラフィックを受信できるからです。 また、次のいずれかの条件が満たされている場合は、IP-PBX をフロントエンドプールに併置するか、またはインターネットテレフォニーサーバープロバイダーのセッションボーダーコントローラー (SBC) に接続しているときに、仲介サーバーをフロントエンドプールに併置することをお勧めします。

- IP-PBX または SBC は、プール内の任意の仲介サーバーからのトラフィックを受信するように構成されており、プール内のすべての仲介サーバーにトラフィックを均等にルーティングできる。

- IP-PBX または SBC は、プール内の任意の仲介サーバーからのトラフィックを受信するように構成されており、プール内のすべての仲介サーバーにトラフィックを均等にルーティングできる。

Microsoft Lync Server 2013、計画ツールを使用して、仲介サーバーを併置するフロントエンドプールが負荷を処理できるかどうかを評価できます。 これらの要件に適合しない環境では、スタンドアロン仲介サーバー プールを展開する必要があります。

一般に、組織が高可用性とスケーラビリティを備えている場合、requirementsFor/V 会議サーバーまたは仲介サーバーの併置は推奨されません。これらのサーバーの役割を Enterprise Edition 展開のフロントエンドプールに配置する詳細については、「展開」のドキュメントの「 [Define And Configure A Front End pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 」を参照してください。 音声ビデオ会議の機能とコンポーネントの詳細については、「計画」のドキュメントの「[Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)」を参照してください。 仲介サーバーを含むエンタープライズ Voip の機能とコンポーネントの詳細については、「計画」のドキュメントの「 [Plan For Enterprise voice In Skype For Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 」を参照してください。


