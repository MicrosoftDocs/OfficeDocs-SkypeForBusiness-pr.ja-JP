---
title: フロントエンド サーバーの併置を追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Enterprise Edition 展開では、音声ビデオ会議サービスがフロントエンド プールに併置されます。仲介サーバーをフロントエンド プールに併置することも、スタンドアロンのサーバーとして仲介サーバーを展開することもできます。電話会議を有効にすると、音声ビデオ会議サービスは常に併置されます。
ms.openlocfilehash: 97f883f0d29f59961a0c396b57b14bbb9eb7f0cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119746"
---
# <a name="add-front-end-server-collocations"></a>フロント エンド サーバーの併置の追加

Enterprise Edition 展開では、音声ビデオ会議サービスがフロントエンド プールに併置されます。仲介サーバーをフロントエンド プールに併置することも、スタンドアロンのサーバーとして仲介サーバーを展開することもできます。電話会議を有効にすると、音声ビデオ会議サービスは常に併置されます。

> [!NOTE]
> [**機能の選択**] ページで [**電話会議**] を選択した場合には、音声ビデオ会議サービスが必要です。Enterprise Edition フロントエンド プールでは、併置された音声ビデオ会議サービスを使用します。[電話会議] を選択しなかった場合、[音声ビデオ会議サービスを併置する] は使用できません。

Standard Edition フロントエンド サーバーまたは Enterprise Edition フロントエンド プールに仲介サーバーの役割を併置できます。 メディア バイパスとドメイン ネーム システム (DNS) 負荷分散をサポートする認定公衆交換電話網 (PSTN) ゲートウェイへ直接 SIP 接続を展開する場合、スタンドアロンの仲介サーバー プールは必要ありません。 スタンドアロンの仲介サーバー プールが必要でないのは、認定ゲートウェイが仲介サーバーのプールへの DNS 負荷分散に対応しており、プール内のすべての仲介サーバーからトラフィックを受信できるからです。 また、次の条件が満たされている限り、IP-PBXs を展開した場合、またはインターネット テレフォニー サーバー プロバイダーのセッション ボーダー コントローラー (SBC) に接続する場合は、フロント エンド プールで仲介サーバーを照合することをお勧めします。

- IP-PBX または SBC は、プール内の任意の仲介サーバーからのトラフィックを受信するように構成されており、プール内のすべての仲介サーバーにトラフィックを均等にルーティングできる。

- IP-PBX または SBC は、プール内の任意の仲介サーバーからのトラフィックを受信するように構成されており、プール内のすべての仲介サーバーにトラフィックを均等にルーティングできる。

Microsoft Lync Server 2013 計画ツールを使用して、仲介サーバーを照合するフロントエンド プールが負荷を処理できるかどうかを評価できます。 これらの要件に適合しない環境では、スタンドアロン仲介サーバー プールを展開する必要があります。

一般に、組織の要件の中に高可用性と優れた拡張性が含まれる場合には、仲介サーバーの併置をお勧めしません。 Enterprise Edition 展開でフロントエンド プールにこれらのサーバー役割を併置する場合の詳細については、「展開」のドキュメントの「[Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)」を参照してください。 音声ビデオ会議の機能とコンポーネントの詳細については、「計画」のドキュメントの「[Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing)」を参照してください。 仲介サーバーなどのエンタープライズ VoIP機能とコンポーネントの詳細については、「計画」のドキュメントの「Plan for エンタープライズ VoIP in [Skype for Business Server 2015」](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) を参照してください。