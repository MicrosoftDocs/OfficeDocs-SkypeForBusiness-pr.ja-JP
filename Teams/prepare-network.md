---
title: Microsoft Teams 用に組織のネットワークを準備する
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: ネットワーク要件、帯域幅要件、その他の考慮事項といった Microsoft Teams ネットワークの準備と管理について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 57f8ffc7d5cedeb6117deffb99ad48ccbe17b48f
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640731"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Microsoft Teams 用に組織のネットワークを準備する

> [!Tip]
> については、次のセッションを監視するチームをするための方法、ネットワークとの最適なネットワーク接続の最適な計画を立てる方法を活用:[チーム ネットワークの計画](https://aka.ms/teams-networking)


チームでは、トラフィックの 3 つのフォームを結合します。

-   データ トラフィックは、Office 365 のオンライン環境とクライアントの間のチーム (信号、プレゼンス、チャット、ファイルのアップロードとダウンロード、OneNote の同期)。

-   ピア ツー ピアのリアルタイム通信トラフィックが (オーディオ、ビデオ、デスクトップの共有)。

-   会議のリアルタイム通信トラフィックが (オーディオ、ビデオ、デスクトップの共有)。

これは、2 つのレベル上のネットワークに影響を与える: ピア ツー ピアのシナリオを直接マイクロソフトのチームのクライアント間でトラフィック フローし、トラフィックがマイクロソフト チーム クライアントと Office 365 環境の間のシナリオを満たすためです。 両方 (たとえば、WAN 経由でサイト) 間の内部ネットワークのセグメントの間に間でフローを許可するトラフィックに最適なトラフィックのフローを確認するには、ネットワーク サイトと Office 365。 正しいポートを開くか、積極的に特定のポートをブロックしないと、劣化した経験です。

> [!NOTE]
> 会議は、iOS および Android モバイル デバイスでサポートされています。 

マイクロソフトのチーム内でのリアルタイム メディアに最適なエクスペリエンスを得るには、ネットワークは、Office 365 のネットワーク要件を満たす必要があります。 詳細については、[メディアの品質とビジネス オンラインの Skype のネットワーク接続のパフォーマンス](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)を参照してください。

2 つ定義するネットワーク セグメント (マイクロソフトのエッジにクライアント) およびマイクロソフトのエッジにエッジを顧客、次の推奨事項を検討してください。


|値  |クライアントはマイクロソフトのエッジ  |マイクロソフトのエッジにエッジを顧客  |
|:--- |:--- |:--- |
|**待機時間 (1 つの方法)**\*  |_lt _ 往復          |_lt _ 30ms         |
|**RTT (ラウンドト リップ時間) の待機時間**\* |_lt _ 100 ミリ秒   |_lt _ 60 ミリ秒 |
|**バースト パケット ロス**    |200 ミリ秒間隔で <10%         |200 ミリ秒間隔で <1%         |
|**パケット損失**     |任意の 15 秒間 <1% の間隔          |<0.1%、15 秒間の間隔         |
|**パケット間到着ジッタ**    |<30ms、15 秒間の間隔         |<15ms、15 秒間の間隔         |
|**パケット順序の変更**    |<0.05% 不適切な順序のパケット         |<0.01% 不適切な順序のパケット         |

\*遅延のメトリック ターゲットは、会社のサイトまたはサイトを想定し、同じ大陸には、マイクロソフトのエッジ。

Microsoft ネットワークのエッジに、企業サイトの接続には、WiFi または他のワイヤレス技術は、最初のホップ ネットワーク アクセスが含まれています。

ネットワーク パフォーマンスの目標は、適切な帯域幅と[QoS の計画](QoS-in-Teams.md)と仮定します。 つまり、要件は、ピーク負荷の下では、ネットワーク接続とチーム リアルタイム メディアのトラフィックを直接適用されます。

両方のネットワーク セグメントをテストするには、[ネットワーク評価ツール](https://go.microsoft.com/fwlink/?linkid=855799)を使用できます。 直接およびお客様のネットワークのエッジに接続されている PC では、両方のクライアント コンピューターでこのツールを展開できます。 ツールには、制限付きのマニュアルが含まれていますが、ツールの使用方法をより深いレベルのマニュアルを参照してください:[ネットワーク対応の評価](https://go.microsoft.com/fwlink/?linkid=855800)。 このネットワーク対応の評価を実行すると、マイクロソフトのチームなどのリアルタイム メディアのアプリケーションを実行するのには、ネットワークの準備を検証できます。

> [!NOTE]
> これは、ビジネス用の Skype を正常に展開しているお客様向けの実行に推奨されている同じネットワーク対応の評価です。


## <a name="bandwidth-requirements"></a>帯域幅の要件

マイクロソフト チームの帯域幅の計算は複雑で、これを支援するため、電卓が作成されました。 計算機にアクセスするには、MyAdvisor では、[ネットワークの計画](https://aka.ms/bwcalc/)に移動します。

> [!NOTE]
> チームの帯域幅の処理が Skype でオンライン ビジネスの向上: チームの呼び出しや、会議の経験 (オーディオ、ビデオ、および共有) は、高品質でのみ 1.2 Mbps が必要です。 拡張性にも十分な帯域幅が利用可能な場合に非常に高品質の最大さらにします。 チームの要求には、低帯域幅の条件が検出されると、チームが迅速に再調整して、帯域幅の使用可能な帯域幅に適応します。

<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a>追加のネットワークに関する考慮事項
---------------

#### <a name="external-name-resolution"></a>外部の名前解決

チームのクライアントを実行するすべてのクライアント コンピューターで、Office 365 が提供するサービスを検出するのには外部の DNS クエリを解決できることと、ファイアウォールがアクセスを遮断していないことを確認します。 ファイアウォール ポートを構成する方法の詳細については、 [Office 365 の Url と IP の範囲](office-365-urls-ip-address-ranges.md)を参照してください。

#### <a name="nat-pool-size"></a>NAT プール サイズ

複数のユーザーとデバイスは、ネットワーク アドレス変換 (NAT) またはポート アドレス変換 (PAT) を使用して Office 365 にアクセスするときは、公的にルーティング可能な各 IP アドレスの背後にある非表示のデバイスがサポートされている数を超えていないことを確認する必要があります。

このリスクを軽減するには、ポートの枯渇を防ぐために適切なパブリック IP アドレスが NAT プールに割り当てられていることを確認します。 ポートの消費と、内部のエンド ・ ユーザーとデバイスは、Office 365 サービスに接続するときの問題に直面します。 詳細については、 [NAT は、Office 365 のサポート](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)を参照してください。

#### <a name="intrusion-detection-and-prevention-guidance"></a>**侵入検知と防止の手引き**

お客様の環境が、侵入検知および防止システム (IDS/IPS) の送信接続のセキュリティの追加レイヤーとして配置されている場合、Office 365 の Url へのリンク先をすべてのトラフィックが whitelisted ことを確認します。

<a name="network-health-determination"></a>ネットワーク正常性の決定
-----------------

マイクロソフト チームのネットワーク内での実装を計画するときことを必要な帯域幅がある場合、すべて必須の IP アドレスを開くと、適切なポートへのアクセスがあり、リアルタイム メディアのパフォーマンス要件を達成します。.

これらの条件に適合していない場合は、エンド ・ ユーザーは表示されません最適なエクスペリエンス チームから品質が悪いため通話や会議中に。

いないこれらの条件を満たす必要があります、これは、時間を続行する前に、条件を満たしていることを確認するプロジェクトを一時停止を検討してください。


|  |  |  |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |判断ポイント         |リアルタイム メディアをサポートするため、ネットワークの機能を評価するでしょうか。<br></br>ネットワークが適切に評価されていない、またはリアルタイム メディアができないことがわかって、無効にしてもビデオと画面の共有ネットワークへの影響とチーム エクスペリエンスの低下を軽減する機能ですか。         |
|![次のステップ アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |次のステップ         |ネットワーク品質不明: ネットワークのリアルタイム メディアの準備ができたかを判断するのには[ネットワーク対応の評価](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)の指示に従います。<br></br>ネットワークの品質が低下します。 は、高品質リアルタイム メディアの適切な環境を提供するネットワークの改善手順を実行します。<br></br>ネットワーク満足: は、すべての IP アドレスとポートが正しくアクセスできることを確認します。           |

## <a name="related-topics"></a>関連トピック

[ビデオ: ネットワークの計画](https://aka.ms/teams-networking)