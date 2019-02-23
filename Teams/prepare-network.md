---
title: Microsoft Teams 用に組織のネットワークを準備する
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: arachman
description: ネットワーク要件、帯域幅要件、その他の考慮事項といった Microsoft Teams ネットワークの準備と管理について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3af825b28f1c6c4abc202bb343c80b50176de16e
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "30205676"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Microsoft Teams 用に組織のネットワークを準備する

> [!Tip]
> については、次のセッションを監視するチームをするための方法、ネットワークとの最適なネットワーク接続の最適な計画を立てる方法を活用:[チーム ネットワークの計画](https://aka.ms/teams-networking)


Teams は 3 つの形態のトラフィックを組み合わせて使用します。

-   Office 365 オンライン環境と Teams クライアント間のデータ トラフィック (信号、プレゼンス、チャット、ファイルのアップロードとダウンロード、OneNote 同期)。

-   ピアツーピアのリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。

-   会議型のリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。

この組み合わせは 2 つのレベルにおけるネットワークに対して影響を及ぼします。ピアツーピアのシナリオの場合、トラフィックは Microsoft Teams クライアント間で直接にフローします。会議のシナリオの場合、トラフィックは Office 365 環境と Microsoft Teams クライアント間をフローします。最適なトラフィック フローを実現するには、内部ネットワーク セグメント間 (WAN 上でのサイト間) のフロー、さらにネットワーク サイトと Office 365 間のフローの両方を許可する必要があります。適切なポートを開かなかったり、特定のポートを自動的に遮断すると、ネットワーク エクスペリエンスの質が低下します。

> [!NOTE]
> 会議は、iOS および Android モバイル デバイスでサポートされています。 

Microsoft Teams でリアルタイム メディアの最適な操作性を実現するには、Office 365 のネットワーク要件を満たす必要があります  詳細については、「[Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)」をご覧ください。

2 つ定義するネットワーク セグメント (マイクロソフトのエッジにクライアント) およびマイクロソフトのエッジにエッジを顧客、次の推奨事項を検討してください。


|値  |クライアントから Microsoft Edge  |Customer Edge から Microsoft Edge  |
|:--- |:--- |:--- |
|**遅延 (一方向)** \*  |< 50 ミリ秒          |< 30 ミリ秒         |
|**遅延 (RTT または往復時間)** \* |< 100 ミリ秒   |< 60 ミリ秒 |
|**バースト パケット損失**    |< 任意の 200 ミリ秒間隔で 10%         |< 任意の 200 ミリ秒間隔で 1%         |
|**パケット損失**     |< 任意の 15 秒間隔で 1%          |< 任意の 15 秒間隔で 0.1%         |
|**パケット到着間ジッター**    |< 15 秒間隔で 30 ミリ秒         |< 任意の 15 秒間隔で 15 ミリ秒         |
|**パケットの並べ替え**    |< 順序が適切でないパケットが 0.05%         |< 順序が適切でないパケットが 0.01%         |

\*遅延のメトリック ターゲットは、会社のサイトまたはサイトを想定し、同じ大陸には、マイクロソフトのエッジ。

Microsoft ネットワークのエッジに、企業サイトの接続には、WiFi または他のワイヤレス技術は、最初のホップ ネットワーク アクセスが含まれています。

ネットワーク パフォーマンスの目標は、適切な帯域幅と[QoS の計画](QoS-in-Teams.md)と仮定します。 つまり、要件は、ピーク負荷の下では、ネットワーク接続とチーム リアルタイム メディアのトラフィックを直接適用されます。

両方のネットワーク セグメントをテストするために、[Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799) を使用することができます。 このツールは、クライアント PC に直接展開したり、Customer Network Edge に接続された PC に展開したりすることができます。 ツールに含まれているドキュメントは限定的ですが、ツールの使用についてのより詳細なドキュメントは「[Network Readiness Assessment (ネットワークの準備状況の評価)](https://go.microsoft.com/fwlink/?linkid=855800)」にあります。 この Network Readiness Assessment を実行することによって、Microsoft Teams などのリアルタイム メディア アプリケーションを実行するためのネットワークの準備状況を検証することができます。

> [!NOTE]
> これは Skype for Business を展開するカスタマ向けに推奨される Network Readiness Assessment と同じです。


## <a name="bandwidth-requirements"></a>帯域幅要件

Microsoft Teams の帯域幅の計算は複雑であるため、それを支援する計算ツールが用意されています。 計算機にアクセスするには、MyAdvisor では、[ネットワークの計画](https://aka.ms/bwcalc/)に移動します。

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

<a name="additional-network-considerations"></a>ネットワークに関する追加の考慮事項
---------------

#### <a name="external-name-resolution"></a>外部の名前解決

チームのクライアントを実行するすべてのクライアント コンピューターで、Office 365 が提供するサービスを検出するのには外部の DNS クエリを解決できることと、ファイアウォールがアクセスを遮断していないことを確認します。 ファイアウォール ポートを構成する方法の詳細については、 [Office 365 の Url と IP の範囲](office-365-urls-ip-address-ranges.md)を参照してください。

#### <a name="nat-pool-size"></a>NAT プール サイズ

複数のユーザーまたはデバイスがネットワーク アドレス変換 (NAT) またはポート アドレス変換 (PAT) を使用して Office 365 にアクセスする場合は、パブリック ルーティング可能な各 IP アドレスの後ろに隠れているデバイスが、サポートされる数値を超過していないことを確認する必要があります。

このリスクを軽減するには、適切なパブリック IP アドレスを NAT プールに割り当ててポート枯渇を回避します。 ポート枯渇は、Office 365 サービスに接続するときに発生するエンドユーザーやデバイスの問題の原因となります。 詳細については、「[Office 365 の NAT サポート](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)」ガイドをご覧ください。

#### <a name="intrusion-detection-and-prevention-guidance"></a>**侵入検知/防御のガイダンス**

送信接続の追加のセキュリティ レイヤとして環境に侵入検知/防御システム (IDS/IPS) が配備されている場合は、送信先から Office 365 URL へのトラフィックがホワイトリストに記載されていることを確認してください。

<a name="network-health-determination"></a>ネットワーク正常性の確認
-----------------

ネットワーク内で Microsoft Teams を実装する計画を行う場合は、必要とされる帯域幅とすべての必須 IP アドレスへのアクセスを確保していること、正しいポートが開かれていること、リアルタイム メディアのパフォーマンス要件を満たしていることを確認する必要があります。

これらの条件を満たすことができない場合は通話や会議中の品質が悪くなるため、エンドユーザーは Teams の最適なエクスペリエンスを得ることができません。

これらの要件を満たしていない場合は、先に進む前にプロジェクトを中断して、条件を満たすことをお勧めします。


|  |  |  |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |判断ポイント         |リアルタイム メディアをサポートするためにネットワーク能力を評価したことはありますか?<br></br>ネットワークが正しく評価されていない場合やリアルタイム メディアをサポートできないことが事前に分かっている場合は、ビデオや画面共有の機能を無効にして、ネットワークへの影響を軽減し、Teams エクスペリエンスの質を向上させることができます。         |
|![次のステップ アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |次のステップ         |ネットワークの品質が不明な場合: [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) のガイダンスに従って、お客様のネットワークでリアルタイム メディアに対する準備が整っているかどうかを判別してください。<br></br>ネットワークの品質が乏しい場合: ネットワーク改善の手順を実行して、高品質なリアルタイム メディアに適した環境を整えてください。<br></br>十分なネットワーク品質: すべての IP アドレスやポートに正しくアクセスできることを確認してください。           |

## <a name="related-topics"></a>関連トピック

[ビデオ: ネットワークの計画](https://aka.ms/teams-networking)