---
title: Microsoft Teams 用に組織のネットワークを準備する
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 03/25/2019
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
ms.openlocfilehash: 5d92e30617fb62000cd4b10dac29ec23eee1feaa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882963"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Microsoft Teams 用に組織のネットワークを準備する


Teams は 3 つの形態のトラフィックを組み合わせて使用します。

-   Office 365 オンライン環境と Teams クライアント間のデータ トラフィック (信号、プレゼンス、チャット、ファイルのアップロードとダウンロード、OneNote 同期)。

-   ピアツーピアのリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。

-   会議型のリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。

この組み合わせは 2 つのレベルにおけるネットワークに対して影響を及ぼします。ピアツーピアのシナリオの場合、トラフィックは Microsoft Teams クライアント間で直接にフローします。会議のシナリオの場合、トラフィックは Office 365 環境と Microsoft Teams クライアント間をフローします。最適なトラフィック フローを実現するには、内部ネットワーク セグメント間 (WAN 上でのサイト間) のフロー、さらにネットワーク サイトと Office 365 間のフローの両方を許可する必要があります。適切なポートを開かなかったり、特定のポートを自動的に遮断すると、ネットワーク エクスペリエンスの質が低下します。

> [!NOTE]
> 会議は、iOS および Android モバイル デバイスでサポートされています。 

マイクロソフトのチーム内でのリアルタイム メディアに最適なエクスペリエンスを得るには、ネットワークは、Office 365 のネットワーク要件を満たす必要があります。 詳細については、「[Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)」をご覧ください。

2 つの重要なネットワーク セグメント (クライアントから Microsoft Edge、Customer Edge から Microsoft Edge) については、以下の推奨事項を考慮してください。


|値  |クライアントから Microsoft Edge  |Customer Edge から Microsoft Edge  |
|:--- |:--- |:--- |
|**待機時間 (1 つの方法)**\*  |< 50 ミリ秒          |< 30 ミリ秒         |
|**RTT (ラウンドト リップ時間) の待機時間**\* |< 100 ミリ秒   |< 60 ミリ秒 |
|**バースト パケット損失**    |< 任意の 200 ミリ秒間隔で 10%         |< 任意の 200 ミリ秒間隔で 1%         |
|**パケット損失**     |< 任意の 15 秒間隔で 1%          |< 任意の 15 秒間隔で 0.1%         |
|**パケット到着間ジッター**    |< 15 秒間隔で 30 ミリ秒         |< 任意の 15 秒間隔で 15 ミリ秒         |
|**パケットの並べ替え**    |< 順序が適切でないパケットが 0.05%         |< 順序が適切でないパケットが 0.01%         |

\*遅延のメトリック ターゲットは、会社のサイトまたはサイトを想定し、同じ大陸には、マイクロソフトのエッジ。

Microsoft ネットワークのエッジに、企業サイトの接続には、WiFi または他のワイヤレス技術は、最初のホップ ネットワーク アクセスが含まれています。

ネットワーク パフォーマンスの目標は、適切な帯域幅と[QoS の計画](QoS-in-Teams.md)と仮定します。 つまり、要件は、ピーク負荷の下では、ネットワーク接続とチーム リアルタイム メディアのトラフィックを直接適用されます。

両方のネットワーク セグメントをテストするには、[ネットワーク評価ツール](https://go.microsoft.com/fwlink/?linkid=855799)を使用できます。 直接およびお客様のネットワークのエッジに接続されている PC では、両方のクライアント コンピューターでこのツールを展開できます。 ツールには、制限付きのマニュアルが含まれていますが、ツールの使用方法をより深いレベルのマニュアルを参照してください:[ネットワーク対応の評価](https://go.microsoft.com/fwlink/?linkid=855800)。 このネットワーク対応の評価を実行すると、マイクロソフトのチームなどのリアルタイム メディアのアプリケーションを実行するのには、ネットワークの準備を検証できます。

> [!NOTE]
> これは、ビジネス用の Skype を正常に展開しているお客様向けの実行に推奨されている同じネットワーク対応の評価です。


## <a name="bandwidth-requirements"></a>帯域幅の要件
マイクロソフトのチームでは、最高のオーディオ、ビデオ、およびネットワークの状態に関係なく経験を共有するコンテンツを示します。 変数のコーデックでは、限られた帯域幅の環境の影響を最小限にメディアをネゴシエートできます。 1080 p のビデオ解像度を含む、品質のエクスペリエンスを最適化できます帯域幅が問題ではない場合ですが、最大 30 fps のビデオ、コンテンツ、および信頼性の高いオーディオの 15 fps です。

この資料では、マイクロソフトのチームのリアルタイム オーディオ、ビデオ、およびデスクトップのさまざまな用途の様相を共有して帯域幅を利用する方法の簡単なバージョンについて説明します。 チームは常に帯域幅の使用に慎重であり、1.2Mbps での HD ビデオの品質を提供することができます。  各オーディオとビデオ通話や会議での実際の帯域幅の消費量が異なる、レイアウトのビデオ、ビデオの解像度、ビデオのフレーム数/秒など、いくつかの要因に基づいています。 多くの帯域幅が利用可能な品質と使用法が最適なエクスペリエンスを実現するのには増加します。


[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


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
