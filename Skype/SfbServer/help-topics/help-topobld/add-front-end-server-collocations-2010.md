---
title: フロントエンド サーバーの併置の追加 (2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Enterprise Edition の展開では、A/V 会議サービス、仲介サーバー、またはその両方を1つのフロントエンドプールで検索するか、スタンドアロンサーバーとして展開することができます。 Standard Edition server の展開では、会議が有効になっている場合、A/V 会議サービスは常に併置されます。
ms.openlocfilehash: 8a8191f29a30052fec837ee9136203eb5db1ee0d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275354"
---
# <a name="add-front-end-server-collocations-2010"></a>フロントエンド サーバーの併置の追加 (2010)

Enterprise Edition の展開では、A/V 会議サービス、仲介サーバー、またはその両方を1つのフロントエンドプールで検索するか、スタンドアロンサーバーとして展開することができます。 Standard Edition server の展開では、会議が有効になっている場合、A/V 会議サービスは常に併置されます。

> [!NOTE]
> **[機能の選択**] ページで**会議**が選択されている場合は、A/V 会議サービスが必要です。 Enterprise Edition のフロントエンドプールでは、併置された A/V 会議サービスまたはスタンドアロンの A/V 会議プールを使用できます。 会議が選択されていない場合は、A/V 会議サービスの Collocate は利用できません。

この仲介サーバーの役割は、Standard Edition のフロントエンドサーバーまたは Enterprise Edition のフロントエンドプールで検索できます。 メディアバイパスとドメインネームシステム (DNS) 負荷分散をサポートする、限定された公衆交換電話網 (PSTN) ゲートウェイに直接 SIP 接続を展開する場合、スタンドアロンの仲介サーバープールは必要ありません。 認定ゲートウェイは、仲介サーバーのプールに対する DNS 負荷分散をサポートし、プール内の任意の仲介サーバーからトラフィックを受信できるため、スタンドアロンの仲介サーバープールは必要ありません。 また、次の条件のいずれかが満たされている限り、IP Pbx を展開した場合、またはインターネットテレフォニーサーバープロバイダーのセッションボーダーコントローラー (SBC) に接続している場合は、仲介サーバーをフロントエンドプールで検索することをお勧めします。

- IP PBX または SBC は、プール内の任意の仲介サーバーからトラフィックを受信し、プール内のすべての仲介サーバーに一律にトラフィックをルーティングできるように構成されています。

- IP PBX または SBC は、プール内の任意の仲介サーバーからトラフィックを受信し、プール内のすべての仲介サーバーに一律にトラフィックをルーティングできるように構成されています。

Microsoft Lync Server 2013 の計画ツールを使用すると、仲介サーバーを配置するフロントエンドプールが負荷を処理できるかどうかを評価することができます。 環境がこれらの要件を満たしていない場合は、スタンドアロンの仲介サーバープールを展開する必要があります。

一般に、組織に高可用性とスケーラビリティがある場合は、Enterprise Edition のフロントエンドプールでこれらのサーバーの役割を検索することについて詳しくは、「Hyper-v 会議サーバーまたは仲介サーバーの collocation」をお勧めします。展開については、「展開ドキュメントで[フロントエンドプールを定義して構成](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)する」を参照してください。 A/V 会議機能とコンポーネントの詳細については、計画ドキュメントの「[会議の計画](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)」を参照してください。 仲介サーバーなどのエンタープライズ Voip 機能とコンポーネントの詳細については、計画ドキュメントの「 [Skype For Business Server 2015 でのエンタープライズ voip の計画](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)」を参照してください。


