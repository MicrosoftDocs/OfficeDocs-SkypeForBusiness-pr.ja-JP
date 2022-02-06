---
title: フロントエンド サーバーの併置を追加する (2010)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Enterprise Edition 展開の場合は、音声ビデオ会議サービス、仲介サーバー、またはその両方をフロント エンド プールに併置するか、またはそれぞれをスタンドアロン サーバーとして展開できます。Standard Edition サーバー展開の場合は、会議が有効であれば、常に音声ビデオ会議サービスが併置されます。
---

# <a name="add-front-end-server-collocations-2010"></a>フロント エンド サーバーの併置の追加 (2010)

Enterprise Edition 展開の場合は、音声ビデオ会議サービス、仲介サーバー、またはその両方をフロント エンド プールに併置するか、またはそれぞれをスタンドアロン サーバーとして展開できます。Standard Edition サーバー展開の場合は、会議が有効であれば、常に音声ビデオ会議サービスが併置されます。

> [!NOTE]
> [**機能の選択**] ページで [**電話会議**] を選択した場合には、音声ビデオ会議サービスが必要です。Enterprise Edition フロント エンド プールでは、併置された音声ビデオ会議サービスまたはスタンドアロン音声ビデオ会議プールを使用できます。[電話会議] を選択しなかった場合、[音声ビデオ会議サービスを併置する] は使用できません。

Standard Edition フロントエンド サーバーまたは Enterprise Edition フロントエンド プールに仲介サーバーの役割を併置できます。 メディア バイパスとドメイン ネーム システム (DNS) 負荷分散をサポートする認定公衆交換電話網 (PSTN) ゲートウェイへ直接 SIP 接続を展開する場合、スタンドアロンの仲介サーバー プールは必要ありません。 スタンドアロンの仲介サーバー プールが必要でないのは、認定ゲートウェイが仲介サーバーのプールへの DNS 負荷分散に対応しており、プール内のすべての仲介サーバーからトラフィックを受信できるからです。 また、次の条件が満たされている限り、IP-PBXs を展開した場合、またはインターネット テレフォニー サーバー プロバイダーのセッション ボーダー コントローラー (SBC) に接続する場合は、フロント エンド プールで仲介サーバーを照合することをお勧めします。

- IP-PBX または SBC は、プール内の任意の仲介サーバーからのトラフィックを受信するように構成されており、プール内のすべての仲介サーバーにトラフィックを均等にルーティングできる。

- IP-PBX または SBC は、プール内の任意の仲介サーバーからのトラフィックを受信するように構成されており、プール内のすべての仲介サーバーにトラフィックを均等にルーティングできる。

Microsoft Lync Server 2013 計画ツールを使用して、仲介サーバーを照合するフロントエンド プールが負荷を処理できるかどうかを評価できます。 これらの要件に適合しない環境では、スタンドアロン仲介サーバー プールを展開する必要があります。

一般に、組織に高可用性とスケーラビリティの要件がある場合は、A/V 会議サーバーまたは仲介サーバーのコロケーションはお勧めしません。Enterprise Edition 展開のフロント エンド プールでこれらのサーバーの役割を照合する方法の詳細については、「展開」のドキュメントの「Define and [Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)」を参照してください。 音声ビデオ会議の機能とコンポーネントの詳細については、「計画」のドキュメントの「[Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing)」を参照してください。 仲介サーバーなどのエンタープライズ VoIP機能とコンポーネントの詳細については、「計画」のドキュメントの「エンタープライズ VoIP [2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) Skype for Business Server計画」を参照してください。