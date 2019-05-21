---
title: Microsoft Teams でネットワークを構成するための使用開始チェックリスト
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Teams 用にネットワークを構成するときに、このチェックリストでコア、to do、タスク、アクティビティに従います。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f25acc2bf5692d349d1526176fd43664a06838b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898834"
---
# <a name="configure-networking"></a>ネットワークを構成する

| いいえ | アクティビティまたはタスク | 説明 | 完了状態 | その他の情報 |
|----|--------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Teams のネットワーク要件を確認する | ネットワークの詳細に進む前に、ネットワーク要件の全体像を把握しておく必要があります。 | | [Microsoft Teams 用に組織のネットワークを準備する](https://docs.microsoft.com/microsoftteams/prepare-network)                                                               |
| 2  | ネットワーク準備ワークショップを実施する | MyAdvisor からネットワーク準備ワークショップを完了し、チームと協力して、改善努力の一環として懸念される問題の領域を特定します。 | | [MyAdvisor のネットワーク準備アセット](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| 3  | ネットワークプランナーを使用する | ネットワークプランナーを使用して、スコープ内のすべての場所とサイトに必要な帯域幅を計算します。 | | [MyAdvisor ネットワークプランナー](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)                                                                                   |
| 4  | ユーザー接続に必要な NAT プールサイズを検証する | ポートの枯渇を防ぐため、適切なパブリック IP アドレスが NAT プールに割り当てられていることを確認します。 ポートの枯渇は、社内ユーザーと、Office 365 サービスに接続できないデバイスに寄与します。 <br/><br/>接続の問題は、クラウドサービスに対するユーザーの認識の問題の主要な原因です。 | | [Office 365 での NAT のサポート](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) |
| 5  | Microsoft データセンターへの最も効率的なルーティングを実装する | ローカルまたは地域の出口ポイントを使用して、可能な限り効率的に Microsoft ネットワークに接続できる場所を特定します。 <br/><br/>[**追加情報**] 列の記事では、Office 365 の名前解決と IP ルーティングの機能をクライアントで利用して、最も近い地域のデータセンターに効率的に接続する方法について説明します。 | | [Office 365 クライアント接続](https://support.office.com/article/Client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b) |
| 6  | Teams への接続を要求するファイアウォールポートを構成する | オンプレミスのクライアントと365サーバー間の接続に必要なファイアウォールポートを特定してテストするには、office 365 の url と ip を確認します。 <br/><br/>サポートされている環境の場合は、ファイアウォール上のすべてのポートを開く必要があります。 一部のポートまたは範囲を開けなかった場合、ユーザーエクスペリエンスに悪影響があります。 [**追加情報**」列のガイダンスに基づいて、ファイアウォールでメディアポートを構成します。 | | [Office 365 の Url と IP アドレス– Microsoft Teams](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) |
| 7  | プロキシサーバーを構成する | お客様の環境を構成して、プロキシサーバーを使用しないようにすることができます。また、最適な音質を得るために、UDP を使って、ユーザーを直接 Office 365 に接続することもできます。 リアルタイムメディアでプロキシサーバーをスキャンする場合、Teams のメディアスタックは強制的に TCP にフェールバックします。これは、品質に悪影響を与えるためです。 <br/><br/>最高品質のユーザーエクスペリエンスを実現するには、常に TCP 経由の UDP を使用します。 | | [サービス管理と品質の計画](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) |
| 個  | 分割トンネル VPN を構成する | 一般に、*分割トンネル vpn*と呼ばれる vpn をバイパスするチームトラフィックに対しては、代替パスを指定することをお勧めします。 [トンネリングの分割を行うと、Office 365 のトラフィックは VPN を経由せず、直接 Office 365 に移動します。 この変更は、品質に良い影響をおよぼしますが、二次的な利点として、VPN デバイスおよび組織のネットワークの負荷を低減します。 | | 分離トンネル VPN を実装するには、VPN ベンダーに問い合わせて構成の詳細を確認してください。 |
| ファイブ  | QoS を使用してパケットの優先順位を設定する | QoS は、管理されたネットワークのすべてのセグメントに実装する必要があります。 ネットワークが帯域幅用に適切にプロビジョニングされている場合でも、予期しないネットワークイベントが発生した場合は、QoS によってリスクを軽減することができます。 QoS が実装されている場合は、予期しないイベントが品質に悪影響を与えないように、ボイストラフィックの優先順位が付けられます。 | | [サービス管理と品質の計画](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) <br/><br/>[Microsoft Teams でのサービスの品質 (QoS)](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| 常用 | 品質とパフォーマンスを向上させるための Wi-fi ネットワークを最適化する | Wi-fi ネットワークを最適化すると、いくつかの要因が再生されます。 <ul><li>QoS または Wi-fi マルチメディア (WMM) を実装して、Wi-fi ネットワーク経由でメディアトラフィックが優先されるようにします。</li><li>Wi-fi バンドとアクセスポイントの配置の計画と最適化。 2.4 GHz の範囲では、アクセスポイントの配置によって十分なパフォーマンスが得られる場合があります。</li></ul> 具体的なガイダンスについては、Wi-fi ベンダーにお問い合わせください。 | | [エンドポイント向けの Wi-Fi の推奨事項](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#wi-fi-recommendations-for-endpoints) |
| 折り | ネットワーク評価ツールを使用してネットワーク接続を検証する | Skype for Business および Teams のネットワーク評価ツールを使用して、Skype for Business Online および Teams の通話と会議で使用されているすべての IP アドレスとポートへの接続をテストします。 ツールをダウンロードして、ツールを使用してテスト結果を解釈する方法について詳しくは、「使用状況」を参照してください。 チームを使用する各場所で、クライアント PC からツールを実行することをお勧めします。 | | [Skype for Business および Teams のネットワーク評価ツール](https://go.microsoft.com/fwlink/?linkid=855799) |
